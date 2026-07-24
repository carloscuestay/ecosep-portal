# Portal ECOSEP — Frontend

Sitio web del portal de la **Empresa Colombiana de Servicios Públicos S.A.S. E.S.P. (ECOSEP)**.

Incluye: hero con collage y emulador de app, deslizador horizontal de servicios/ambientes,
modales por subservicio, menús desplegables, sección de Oficina Virtual con QR, video
institucional, servicios complementarios (incl. Analítica de datos del sector), chatbot
asistente y pie con redes sociales.

## Estructura
- `index.html` — sitio completo y autocontenido (imágenes, ilustraciones y video embebidos).
- `ECOSEP_institucional.mp4` — video institucional (también va embebido).

## Publicar en Hostinger
**Opción estática (recomendada para este sitio):** sube el contenido de esta carpeta a
`public_html/` (hosting) o a `/var/www/ecosep/` (VPS). No requiere compilación.

## Conexión con el backend (API Django)
El backend `ecosep-backend` expone una API en `/api/` y un panel en `/admin/` para
administrar contenidos (servicios, subservicios, PQR, textos de menú, video, contacto).
Para alimentar el portal desde la API, reemplaza los datos de ejemplo por llamadas fetch,
por ejemplo:

```js
const API = 'https://ecosep.com.co/api';
const servicios = await (await fetch(`${API}/servicios/`)).json();
const config    = await (await fetch(`${API}/config/`)).json();
```

Consulta el **Manual de Despliegue** para publicar frontend + backend en producción.

© 2026 ECOSEP S.A.S. E.S.P.
