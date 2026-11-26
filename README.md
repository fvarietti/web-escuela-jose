# Escuela del Maestro José Montevideo

Sitio web estático de la Escuela de Crecimiento Espiritual. HTML y CSS puros: no necesita instalar nada ni compilar.

## Estructura

```
web-escuela-jose/
├── index.html              # Inicio: presentación, resumen de la escuela, actividades, últimos audios y contacto
├── sobre-la-escuela.html   # Texto completo sobre la escuela
├── audios.html             # Todos los audios (reproducir y descargar)
├── recursos.html           # Materiales (vacía por ahora)
├── styles.css              # Estilos de todo el sitio (colores y tipografía en el bloque :root)
├── img/                    # Imágenes de fondo (cielo y montañas)
├── audios/                 # Archivos MP3
└── README.md
```

## Ver el sitio en tu computadora

Abre `index.html` con el navegador (doble clic).

## Publicar con GitHub Pages

1. Sube todo el contenido de esta carpeta al repositorio (rama `main`).
2. En GitHub: **Settings → Pages → Deploy from a branch → main / (root) → Save**.
3. El sitio queda en `https://fvarietti.github.io/web-escuela-jose/` en uno o dos minutos.

Cada cambio guardado en `main` actualiza el sitio automáticamente.

## Cómo editar

- **Textos de la escuela**: `sobre-la-escuela.html`. El resumen del inicio está en `index.html`, en `<section id="escuela">`.
- **Actividades y contacto**: `index.html`, en `<section id="actividades">` y `<section id="contacto">`. Para una actividad nueva, copia una fila `<li class="fila">` y cambia el título (`<h3>`), el día y horario (`<small>`) y la descripción (`<p>`).
- **Colores y tipografía**: `styles.css`.
- **Menú**: está repetido en cada página `.html`; si lo cambias, hazlo en todas.

### Agregar un audio

1. Guarda el MP3 en `audios/` (por ejemplo `audios/charla-04.mp3`, sin espacios ni tildes).
2. En `audios.html`, copia una fila `<li class="fila">…</li>` y cambia el título, la duración, el peso y la ruta del archivo (en `<audio src>` y en el enlace de descarga).
3. Si quieres que aparezca entre los últimos audios del inicio, copia también la fila en `index.html`, en `<section id="audios">`.

Para que pesen poco, exporta la voz en MP3 mono a 64 kbps (15 min ≈ 7 MB, 45 min ≈ 22 MB):

```
ffmpeg -i original.wav -ac 1 -b:a 64k charla-04.mp3
```

Desde la web de GitHub se pueden subir archivos de hasta 25 MB; para más, usa GitHub Desktop o la terminal. GitHub Pages recomienda sitios de hasta 1 GB aproximadamente; si la colección crece mucho, conviene alojar los audios en otro servicio (por ejemplo Internet Archive) y enlazarlos.

### Agregar recursos

Edita `recursos.html`: reemplaza el mensaje `<p class="vacio">` por los contenidos.

### Google Maps e Instagram

En Contacto (en `index.html`) hay dos datos de ejemplo para reemplazar:

- **Enlace "Ver en Google Maps"**: cambia el texto después de `query=` por la dirección real, con `+` en lugar de espacios.
- **Instagram**: cambia `usuario_escuela` por el usuario real, en el enlace y en el texto.

## Créditos

Fotografías de [Unsplash](https://unsplash.com): Susur He y Oma Chawhte.
