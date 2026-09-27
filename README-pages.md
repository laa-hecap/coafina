# Sitio de acción de CoAfina (GitHub Pages)

Un solo archivo, `index.html`, sin build. No sustituye al sitio de la edición en laconga.redclara.net: es la puerta de entrada que manda a cada persona a donde tiene que ir (retos, inscripción, patrocinio) y, sobre todo, a Discord.

## Publicar

1. Copie `index.html`, `logo.png` y los recursos gráficos (`hackathon-2026.webm/.mp4/.png`, `banner-retos-2026.jpg`, `fases-2026.jpg`, `llamado-retos-2026.jpg`, `patrocinadores-2026.png`, `wikimedia-ch.png`) a la raíz del repositorio.
2. Settings → Pages → Deploy from a branch → `main`, carpeta `/`.
3. En unos minutos queda en `https://laa-hecap.github.io/<repo>/`.

## Actualizar

Todo lo que cambia está en el bloque `<script id="config" type="application/json">` al final de `index.html`:

- `discord`: enlace de invitación permanente al servidor. Es el enlace más importante del sitio; aparece en la cabecera, en la franja azul y en redes.
- `formChallenge`, `formHacker`: formularios de retos e inscripción.
- El contacto es Discord en todo el sitio (retadores, hackers, patrocinadores, pie); no hay correo.
- `x`, `instagram`, `linkedin`, `facebook`, `youtube`, `github`, `website`: redes. Las que queden en `""` no se muestran.
- `datesLong` y `deadlines`: fechas de la edición 2026 ya cargadas (retos hasta el 23 de octubre, inscripciones hasta el 4 de noviembre, hackathon 27–29 de noviembre). Las prórrogas al 31 de octubre y al 14 de noviembre se cambian aquí cuando se anuncien.


