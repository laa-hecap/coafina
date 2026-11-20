# Sitio de acción de CoAfina (GitHub Pages)

Sitio estático, sin build: `index.html` (español), `en.html` (inglés) y unos pocos archivos de datos. No sustituye al sitio de la edición en laconga.redclara.net: es la puerta de entrada que manda a cada persona a donde tiene que ir (retos, inscripción, patrocinio) y, sobre todo, a Discord.

## Qué archivo cambia qué

En la siguiente tabla está cada cosa que suele cambiar y el archivo donde se cambia.

| Quiero… | Archivo |
|---|---|
| Abrir o cerrar la convocatoria de retos o la de hackers | `convocatorias.json` |
| Mostrar los retos a partir de una fecha | `convocatorias.json` (`retosVisiblesDesde`) |
| Actualizar el cronograma | `cronograma.json` y `cronograma.en.json` |
| Añadir o corregir un reto | `retos.json` y `retos.en.json` |
| Añadir un recurso para hackers | `README.md` y `README.en.md` |
| Cambiar fechas, formularios, Discord o redes | Bloque de configuración al final de `index.html` y `en.html` |
| Cambiar las diapositivas del taller | `charla-recursos.html` |

## El interruptor de las convocatorias

Las convocatorias de retos y de hackers se abren y se cierran desde un solo archivo: `convocatorias.json`, en la raíz del repositorio. Tiene dos valores, uno por convocatoria:

```json
{
  "retos": false,
  "hackers": false
}
```

`true` significa abierta y `false` significa cerrada. El cambio vale para la página en español y para la página en inglés al mismo tiempo. El archivo trae además una línea `_ayuda` con una nota para quien lo edite; esa línea se queda como está.

### Cambiarlo en tres pasos

Se puede hacer desde el navegador, en GitHub:

1. Abre [`convocatorias.json`](convocatorias.json) y pulsa el lápiz («Edit this file»).
2. Cambia `false` por `true`, o `true` por `false`, en la línea de la convocatoria que quieras.
3. Pulsa «Commit changes». El sitio se actualiza solo en uno o dos minutos.

Por ejemplo, para abrir la convocatoria de retos y dejar cerrada la de hackers, el archivo queda así:

```json
{
  "retos": true,
  "hackers": false
}
```

Quien prefiera la terminal puede hacer lo mismo de esta forma:

```bash
git pull
# edita convocatorias.json
git add convocatorias.json
git commit -m "Abre la convocatoria de retos"
git push
```

### Qué cambia en el sitio

En la siguiente tabla se ve qué muestra el sitio con cada valor.

| Valor | Parte del sitio | Abierta (`true`) | Cerrada (`false`) |
|---|---|---|---|
| `retos` | Primera puerta | «Propón un reto», que lleva a cómo proponerlo | «Conoce los retos», que lleva a los retos de la edición |
| `retos` | Franja bajo las puertas | Banner de la convocatoria con su plazo | Oculta |
| `retos` | Columna «Retadores» | Botón «Proponer un reto», plazo, nota de dudas y afiche | Nota de convocatoria cerrada |
| `retos` | Bajo las tarjetas de retos | Botón «Enviar mi reto» | Oculto |
| `hackers` | Segunda puerta | «Participa como hacker», que lleva a cómo inscribirse | «Prepárate para el hackathon», que lleva al cronograma |
| `hackers` | Columna «Hackers» | Botón «Inscribirme», plazo y nota del comprobante | Nota de inscripción cerrada |
| Los dos | «Cómo funciona» | Línea con los plazos, si alguna convocatoria está abierta | Aviso de convocatorias cerradas, si las dos lo están |

La puerta «Apoya la edición» y la columna «Patrocinadores» están siempre visibles, porque los patrocinios se reciben todo el año.

### Antes de abrir una convocatoria nueva

El interruptor muestra u oculta lo que ya está en las páginas. Los textos y enlaces de una convocatoria abierta salen de otros lugares, así que conviene revisarlos antes de poner `true`:

- **Fechas límite:** `deadlines.challenges` y `deadlines.hackers`, en el bloque de configuración al final de `index.html` y de `en.html`.
- **Formularios:** `links.formChallenge` y `links.formHacker`, en ese mismo bloque.
- **Imágenes:** `banner-retos-2026.jpg` (el banner) y `llamado-retos-2026.jpg` (el afiche de la columna «Retadores»).
- **Aviso sobre el banner:** el texto «Plazo ampliado hasta el…» está en el script de cada página; búscalo por esas palabras.
- **Notas de cierre:** mencionan el año («…de 2026 ya cerró. Volverá en la edición 2027»). Están en `index.html` y `en.html`; búscalas por `data-closed`.

### Si algo sale distinto de lo esperado

- **Pusiste `true` y el sitio sigue mostrando la convocatoria cerrada.** Casi siempre es un detalle de escritura en el archivo: `true` y `false` van en minúsculas y sin comillas, cada línea termina en coma salvo la última, y las llaves `{ }` abren y cierran el archivo. Cuando el archivo tiene un error, el sitio muestra las dos convocatorias cerradas, que es la opción segura.
- **Todavía ves la versión anterior.** Espera un par de minutos y recarga la página sin caché (Cmd+Shift+R en Mac, Ctrl+F5 en Windows).
- **Dudas sobre qué página editar.** Basta con cambiar `convocatorias.json`: las dos páginas leen ese archivo.

## Mostrar los retos a partir de una fecha

En `convocatorias.json` hay una tercera línea, `retosVisiblesDesde`, con la fecha y la hora a partir de las cuales el sitio muestra los retos:

```json
"retosVisiblesDesde": "2026-11-27T12:00:00Z"
```

Antes de ese momento, la sección «Retos 2026» muestra un aviso de que los retos se revelan el viernes 27, la primera puerta dice «Los retos, el viernes 27» y el segundo botón del encabezado dice «Retos: el viernes 27». Al llegar la hora, el sitio muestra los retos por sí solo, también en las páginas que ya estén abiertas, sin publicar nada ese día.

La hora se escribe en UTC, con el formato `AAAA-MM-DDTHH:MM:SSZ`. En la siguiente tabla está la hora local de `2026-11-27T12:00:00Z` en varias ciudades.

| Lugar | Hora local |
|---|---|
| Ciudad de México | viernes 27, 06:00 |
| Bogotá, Lima y Quito | viernes 27, 07:00 |
| Caracas y La Paz | viernes 27, 08:00 |
| Buenos Aires, Santiago y São Paulo | viernes 27, 09:00 |
| Ginebra | viernes 27, 13:00 |

- **Para revelarlos en otro momento,** cambia la fecha. Por ejemplo, `2026-11-27T14:00:00Z` es el viernes a las 09:00 en Bogotá, la hora de la bienvenida.
- **Para mostrarlos ya,** deja el valor vacío: `"retosVisiblesDesde": ""`.
- **Las diapositivas del taller** (`charla-recursos.html`) llevan la misma fecha en la diapositiva «Los datos de los once retos», en el atributo `data-desde`. Si cambias la fecha del sitio, cámbiala también allí.

Esto oculta los retos en el sitio. Los archivos `retos.json`, `retos.en.json` y la carpeta `retos/` siguen en el repositorio, que es público, y la hora se toma del reloj de cada visitante.

## Publicar

1. Copie a la raíz del repositorio las páginas (`index.html`, `en.html`, `charla-recursos.html`), los archivos de datos (`convocatorias.json`, `cronograma.json`, `cronograma.en.json`, `retos.json`, `retos.en.json`), la carpeta `retos/`, `logo.png` y los recursos gráficos (`hackathon-2026.webm/.mp4/.png`, `banner-retos-2026.jpg`, `fases-2026.jpg`, `llamado-retos-2026.jpg`, `patrocinadores-2026.png`, `wikimedia-ch.png`).
2. Settings → Pages → Deploy from a branch → `main`, carpeta `/`.
3. En unos minutos queda en `https://laa-hecap.github.io/<repo>/`.

## Actualizar

Todo lo que cambia está en el bloque `<script id="config" type="application/json">` al final de `index.html`:

- `discord`: enlace de invitación permanente al servidor. Es el enlace más importante del sitio; aparece en la cabecera, en la franja azul y en redes.
- `formChallenge`, `formHacker`: formularios de retos e inscripción.
- El contacto es Discord en todo el sitio (retadores, hackers, patrocinadores, pie); no hay correo.
- `x`, `instagram`, `linkedin`, `facebook`, `youtube`, `github`, `website`: redes. Las que queden en `""` no se muestran.
- `datesLong` y `deadlines`: fechas de la edición 2026 ya cargadas (retos hasta el 31 de octubre, inscripciones hasta el 14 de noviembre, hackathon 27–29 de noviembre). Las prórrogas al 31 de octubre y al 14 de noviembre se cambian aquí cuando se anuncien.



## Retos 2026

La sección "Retos 2026" se genera desde `retos.json`. Cada reto lleva título, organización, resumen, entregable, perfiles buscados, fuente de datos con licencia, ilustración y plano (en la carpeta `retos/`). Para añadir un reto seleccionado, copie un bloque del archivo, cambie los textos y suba sus dos imágenes a `retos/`. El enlace al formulario de retos está en el bloque de configuración de `index.html` (`formChallenge`).

Las piezas gráficas conservan los plazos originales. El aviso sobre el banner y la nota de la secuencia muestran las fechas ampliadas desde la configuración.

## Idiomas y diseño

`index.html` es la versión en español y `en.html` la versión en inglés. Ambas conservan el diseño original, con fondo marfil (`#FFFCF5`) y enlaces Español / English en la cabecera. Los textos de las piezas gráficas originales permanecen en español; los textos HTML y alternativos de la versión inglesa están traducidos.

La versión inglesa carga `retos.en.json` y `README.en.md`; comparten las mismas imágenes, planos y destinos de los formularios. Al actualizar un reto, un enlace, una fecha o un recurso, actualiza ambas versiones. Las fechas de cada HTML usan cadenas del idioma correspondiente; no hay traducción automática ni cierre por reloj de la convocatoria de retos.

## Cronograma

La sección «Cronograma» se dibuja desde `cronograma.json` (español) y `cronograma.en.json` (inglés): una cuadrícula semanal en pantallas anchas y una lista por día en móviles. Cada evento lleva `fecha`, `inicio` y `fin` (horas enteras en GMT-5), `tipo` (`hack`, `talk`, `orient`, `social`, `dead`, `pend` o `fin`), `titulo` y, si hace falta, `etiqueta` y `detalle`. Con `"preliminar": true` aparece el aviso de versión preliminar. `cronograma-2026.pdf` y `cronograma-2026.png` son copias fijas para descargar: hay que regenerarlas cuando cambie el cronograma.

## Diapositivas del taller

`charla-recursos.html` contiene las diapositivas del taller «Herramientas y recursos útiles para el hackathon (y tu carrera)». Se abre desde el bloque al final de «Recursos para hackers» y no aparece en el menú. Es una sola página: se avanza con las flechas, y al imprimirla se obtiene un PDF con una diapositiva por hoja.
