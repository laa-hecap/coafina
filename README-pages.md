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
- `datesLong` y `deadlines`: fechas de la edición 2026 ya cargadas (retos hasta el 31 de octubre, inscripciones hasta el 14 de noviembre, hackathon 27–29 de noviembre). Las prórrogas al 31 de octubre y al 114 de noviembre se cambian aquí cuando se anuncien.



## Retos 2026

La sección "Retos 2026" se genera desde `retos.json`. Cada reto lleva título, organización, resumen, entregable, perfiles buscados, fuente de datos con licencia, ilustración y plano (en la carpeta `retos/`). Para añadir un reto seleccionado, copie un bloque del archivo, cambie los textos y suba sus dos imágenes a `retos/`. El enlace al formulario de retos está en el bloque de configuración de `index.html` (`formChallenge`).

Las piezas gráficas conservan los plazos originales. El aviso sobre el banner y la nota de la secuencia muestran las fechas ampliadas desde la configuración.

## Idiomas y diseño

`index.html` es la versión en español y `en.html` la versión en inglés. Ambas conservan el diseño original, con fondo marfil (`#FFFCF5`) y enlaces Español / English en la cabecera. Los textos de las piezas gráficas originales permanecen en español; los textos HTML y alternativos de la versión inglesa están traducidos.

La versión inglesa carga `retos.en.json` y `README.en.md`; comparten las mismas imágenes, planos y destinos de los formularios. Al actualizar un reto, un enlace, una fecha o un recurso, actualiza ambas versiones. Las fechas de cada HTML usan cadenas del idioma correspondiente; no hay traducción automática ni cierre por reloj de la convocatoria de retos.
