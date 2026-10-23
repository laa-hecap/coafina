# Sitio de acción de CoAfina (GitHub Pages)

Sitio estático sin build: `index.html`, `retos.json`, `README.md` y los recursos gráficos. Complementa el [sitio oficial](https://laconga.redclara.net/hackathon/): permite explorar retos, encontrar la inscripción y entrar a la comunidad de Discord.

## Publicar

En GitHub, Settings → Pages → Deploy from a branch → `main`, carpeta `/`. Publica el repositorio completo para conservar los datos y las imágenes. La dirección es `https://laa-hecap.github.io/coafina/`.

Para revisar localmente, ejecuta `python3 -m http.server 8000` en la raíz y abre `http://localhost:8000`. Los retos y recursos necesitan HTTP; abrir `index.html` directamente como archivo no permite cargarlos.

## Actualizar la edición

El bloque `<script id="config" type="application/json">` de `index.html` contiene:

- `edition` y `datesLong`: año y texto principal de las fechas.
- `deadlines`: fechas ISO `YYYY-MM-DD`. Cada fase tiene `start` y, cuando corresponda, `end`. La publicación de retos solo tiene `start`.
- `links.discord`: invitación al servidor, usada en toda la página.
- `links.formChallenge` y `links.formHacker`: formularios oficiales.
- `links.website`, `links.repo` y las redes sociales. Una red con valor `""` se oculta.

Las notas de convocatoria, las fechas de la secuencia y las etiquetas «En curso» se generan desde `deadlines`. Los intervalos incluyen ambos días y se comparan en UTC para mostrar el mismo estado a todas las personas. Son indicaciones de calendario, no una hora límite oficial: los formularios siguen bajo control del comité. Fuera del intervalo de inscripción, el botón dice «Consultar inscripción» y conserva el enlace al formulario.

Los enlaces de acción y la fecha de inscripción también tienen un respaldo en HTML para quienes no ejecutan JavaScript. Cuando cambies enlaces o fechas, actualiza esos respaldos en la misma edición. Los afiches originales se conservan como archivos, pero las piezas con plazos antiguos ya no se muestran en la página.

Fechas y enlaces contrastados con el sitio oficial el 23 de octubre de 2026: retos hasta el 31 de octubre, inscripciones hasta el 14 de noviembre, taller el 23 de noviembre y hackathon del 27 al 29 de noviembre.

## Retos 2026

La galería se genera desde `retos.json`. Cada reto incluye `nombre` (título breve), `bajada` (descripción de la tarjeta), `titulo` (título completo), organización, resumen, entregable, perfiles, fuente y licencia de datos, ilustración y plano. El título completo y la ficha permanecen disponibles en «Explorar reto»; el plano se abre en un diálogo que se cierra con el botón o Escape.

Para añadir un reto, copia un bloque del JSON, asigna un número único y sube su ilustración y plano a `retos/`. Comprueba las rutas y el texto alternativo de ambas imágenes.

## Recursos

La lista de herramientas se mantiene en las secciones `##` de `README.md`. Cada recurso usa `- [Nombre](https://…)` seguido de una descripción. Un encabezado de nivel uno termina la lista, separándola de las instrucciones de mantenimiento. Comprueba las condiciones actuales de cada herramienta antes de recomendarla como gratuita.

## Comprobación antes de publicar

- Revisar escritorio y móvil, sin desplazamiento horizontal.
- Abrir las cinco fichas y sus planos; comprobar Escape y navegación con teclado.
- Comprobar enlaces de inscripción, retos, sitio oficial y Discord.
- Verificar las fechas y estados antes, durante y después de las convocatorias.
- Comprobar la página con movimiento reducido y JavaScript desactivado.
