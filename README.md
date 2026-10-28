# Avista Beach Villas & Resort — Landing de preventa

Sitio estático (HTML + Tailwind CSS por CDN). No necesita instalación ni compilación: basta con publicar esta carpeta tal cual.

## Estructura

```
index.html       Página principal (villas, avances, master plan, inversión RWAXI)
datos.html       Política de Tratamiento de Datos Personales
terminos.html    Términos y Condiciones de Uso
cookies.html     Política de Cookies y Almacenamiento Local
assets/          Imágenes, logos y favicon
```

## Publicar con GitHub Pages

1. Sube el contenido de esta carpeta a la raíz del repositorio (rama `main`).
2. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. En uno o dos minutos el sitio queda en `https://<usuario>.github.io/<repositorio>/`.

## Configuración pendiente (al inicio del `<script>` de `index.html`)

| Constante | Qué es | Valor actual |
|---|---|---|
| `WHATSAPP_NUMBER` | Número oficial, formato internacional sin `+` ni espacios | `573018048806` (línea provisional, 301 804 8806) |
| `WEBHOOK_URL` | Webhook de Make/Zapier que registra los consentimientos | vacío (no se envía nada) |
| `POLICY_VERSION` | Versión de las políticas que se registra con cada consentimiento | `v1.0-Oct2026` |

Cada consentimiento envía al webhook: `nombre`, `acepta_terminos`, `acepta_datos`, `acepta_cookies`, `fecha_hora`, `lote_o_origen` y `version_politicas` (formato de formulario, `application/x-www-form-urlencoded`).

## Mantenimiento habitual

- **Disponibilidad de lotes** (`index.html`): listas `AVAILABLE_LOT` (sin casa) y `WITH_HOUSE` (con casa). Los lotes que no figuran en ninguna se muestran como "No disponible".
- **Cambios en las políticas**: si se modifica el texto de `datos.html`, `terminos.html` o `cookies.html`, actualiza también `POLICY_VERSION` (por ejemplo `v1.1-Nov2026`) y la versión que aparece en cada página.
