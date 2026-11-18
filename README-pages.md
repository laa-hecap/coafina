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

## Convocatorias abiertas o cerradas

El archivo `convocatorias.json` decide qué convocatorias se muestran abiertas, en español y en inglés a la vez:

```json
{ "retos": false, "hackers": false }
```

- `"retos": true` vuelve a mostrar la puerta «Propón un reto», el banner de la convocatoria, el botón «Proponer un reto» con su afiche y el botón «Enviar mi reto».
- `"hackers": true` vuelve a mostrar la puerta «Participa como hacker» y el botón «Inscribirme» con sus notas.
- Con `false`, cada puerta lleva a los retos o al cronograma, y las columnas muestran una nota de convocatoria cerrada.

Al reabrir, actualiza también las fechas (`deadlines`) y los formularios (`links`) en el bloque de configuración de `index.html` y `en.html`. Los patrocinios están siempre abiertos y no dependen de este archivo.

## Cronograma

La sección «Cronograma» se dibuja desde `cronograma.json` (español) y `cronograma.en.json` (inglés): una cuadrícula semanal en pantallas anchas y una lista por día en móviles. Cada evento lleva `fecha`, `inicio` y `fin` (horas enteras en GMT-5), `tipo` (`hack`, `talk`, `orient`, `social`, `dead`, `pend` o `fin`), `titulo` y, si hace falta, `etiqueta` y `detalle`. Con `"preliminar": true` aparece el aviso de versión preliminar. `cronograma-2026.pdf` y `cronograma-2026.png` son copias fijas para descargar: hay que regenerarlas cuando cambie el cronograma.

## Diapositivas del taller

`charla-recursos.html` contiene las diapositivas del taller «Herramientas y recursos útiles para el hackathon (y tu carrera)». Se abre desde el bloque al final de «Recursos para hackers» y no aparece en el menú. Es una sola página: se avanza con las flechas, y al imprimirla se obtiene un PDF con una diapositiva por hoja.
