# 🚀 Bienvenidos al Hackathon CoAfina 2024 🚀

¡Hola, hackers! 🎉 Hemos reunido una lista de recursos y herramientas que harán tu vida más fácil durante el hackathon.

Aquí encontrarás de todo: desde plataformas para alojar tu proyecto hasta herramientas de visualización de datos y APIs de IA. ¡Explora los enlaces y empieza a crear algo increíble!

---

## 🌐 Alojamiento Web y Nube
- [Infomaniak](https://www.infomaniak.com/en): Soluciones pro para hosting y nube.
- [Proton](https://proton.me/): Email seguro, calendario y almacenamiento de archivos.
- [GitHub Pages](https://pages.github.com/): Alojamiento gratuito para tus repos en GitHub.
- [Netlify](https://www.netlify.com/): Despliega proyectos web modernos con facilidad.
- [GitLab](https://gitlab.com/): Plataforma DevOps para desarrolladores.

## 💻 Computación Interactiva y Notebooks
- [Jupyter](https://jupyter.org/): App web de código abierto para computación interactiva.
- [PAWS (Wikimedia)](https://wikitech.wikimedia.org/wiki/PAWS): Notebooks Jupyter para Wikimedia.
- [Google Colab](https://colab.google/): Notebooks Jupyter en la nube con GPU gratuita.
- [NBViewer](https://nbviewer.org/): Visualiza notebooks Jupyter en línea.
- [MyBinder](https://mybinder.org/): Servidor de notebooks Jupyter mono-usuario.

## 📊 Visualización de Datos y Dashboards
- [Streamlit](https://streamlit.io/#install): Convierte scripts de Python en apps interactivas.
- [Dash (Plotly)](https://dash.plotly.com/): Crea dashboards con Python.
- [Panel (HoloViz)](https://panel.holoviz.org/): Solución de alto nivel para apps y dashboards en Python.
- [Google Charts](https://developers.google.com/chart): Herramientas simples de gráficos.
- [D3.js](https://d3js.org/): Librería JS para visualizaciones de datos dinámicas e interactivas.

## 🤖 IA y Aprendizaje Automático
- [OpenAI](https://openai.com/): Investigación y despliegue avanzado de IA.
- [Mistral AI](https://mistral.ai/): Herramientas y modelos de IA.
- [Hugging Face](https://huggingface.co/): Librería open-source para procesamiento de lenguaje natural.
- [Ollama](https://ollama.com/): Despliegue de modelos de IA.
- [Gradio](https://www.gradio.app/): Construye y comparte modelos de machine learning con interfaces fáciles de usar.

## 🚀 Despliegue y Desarrollo de Aplicaciones
- [Anvil](https://anvil.works/): Construye apps web solo con Python.
- [Docker](https://www.docker.com/): Plataforma para desarrollar, enviar y ejecutar apps.
- [DockerHub](https://hub.docker.com/): Plataforma para desarrollar, enviar y ejecutar dockers.

## 🏛️ Recursos Educativos y Ejemplos
- [Wikimedia](https://www.wikimedia.org/): Proyectos de conocimiento libre.
- [Zenodo](https://zenodo.org/): Repositorio de datos de investigación.
- [Academic Torrents](https://academictorrents.com/): Distribuye datos de investigación.
- [GitHub Gobierno](https://github.com/github/government.github.com): Proyectos open-source en el gobierno.
- [Square Open Source](https://github.com/square/square.github.io): Proyectos open-source de Square.
- [Netflix Open Source](https://netflix.github.io/): Proyectos open-source de Netflix.

## 🔌 API e Integración
- [Twitter API](https://developer.x.com/en/docs/twitter-api/getting-started/about-twitter-api): Accede e integra datos de Twitter.
- [Reglas y Políticas de la API de X](https://help.x.com/en/rules-and-policies/x-api): Guías para usar la API de Twitter.

## 📚 Artículos y Guías
- [Hackathon LACONGA](https://laconga.redclara.net/hackathon-coc/): Hackathon para colaboración e innovación en América Latina.
- [Sitios para Desplegar Cualquier Aplicación](https://dev.to/joselatines/sites-to-deploy-any-application-paidfree-alternatives-3em8): Alternativas pagas y gratuitas para desplegar apps.
- [15 Alojamientos Gratuitos para Desarrolladores Front-End](https://blog.bitsrc.io/15-free-hosting-for-front-end-developers-9224bc34e14a): Guía de opciones de hosting gratuito para desarrolladores front-end.

## 📝 Documentos y Colaboración
- [Google Docs](https://www.google.com/docs/about/): Herramienta para crear, editar y compartir documentos en línea.

---

Cada enlace te proporciona herramientas y servicios valiosos para diferentes aspectos de la tecnología y la innovación. ¡Buena suerte y diviértete creando! 🚀



---

# Sitio de acción de CoAfina (GitHub Pages)

Un solo archivo, `index.html`, sin build. No sustituye al sitio de la edición en laconga.redclara.net: es la puerta de entrada que manda a cada persona a donde tiene que ir (retos, inscripción, patrocinio) y, sobre todo, a Discord.

## Publicar

1. Copie `index.html` y `logo.png` a la raíz del repositorio.
2. Settings → Pages → Deploy from a branch → `main`, carpeta `/`.
3. En unos minutos queda en `https://laa-hecap.github.io/<repo>/`.

## Actualizar

Todo lo que cambia está en el bloque `<script id="config" type="application/json">` al final de `index.html`:

- `discord`: enlace de invitación permanente al servidor. Es el enlace más importante del sitio; aparece en la cabecera, en la franja azul y en redes.
- `formChallenge`, `formHacker`: formularios de retos e inscripción.
- El contacto es Discord en todo el sitio (retadores, hackers, patrocinadores, pie); no hay correo.
- `x`, `instagram`, `linkedin`, `facebook`, `youtube`, `github`, `website`: redes. Las que queden en `""` no se muestran.
- `datesLong` y `deadlines`: fechas de la edición 2026 ya cargadas (retos hasta el 23 de octubre, inscripciones hasta el 4 de noviembre, hackathon 27–29 de noviembre). Las prórrogas al 31 de octubre y al 14 de noviembre se cambian aquí cuando se anuncien.


