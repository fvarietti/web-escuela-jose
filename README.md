# Escuela del Maestro José Montevideo

Sitio web estático de la Escuela de Crecimiento Espiritual. Es una sola página (`index.html`) con las secciones Inicio, Sobre la escuela, Audios, Actividades, Recursos y Contacto. No necesita instalar nada ni compilar.

## Estructura

```
web-escuela-jose/
├── index.html        # Toda la página (HTML y CSS)
├── img/              # Imágenes del sitio
│   ├── loto.jpg
│   └── meditacion.jpg
├── audios/           # Audios en MP3 (reproducir y descargar)
└── README.md
```

## Ver el sitio en tu computadora

Abre `index.html` con el navegador (doble clic). No hace falta un servidor.

## Publicar con GitHub Pages

1. Sube el contenido de esta carpeta al repositorio (rama `main`).
2. En GitHub: **Settings → Pages**.
3. En **Build and deployment**, elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`.
4. Guarda. En uno o dos minutos el sitio queda disponible en:
   `https://fvarietti.github.io/web-escuela-jose/`

Cada vez que hagas *commit* de un cambio en `main`, el sitio se actualiza solo.

## Cómo editar el contenido

Todo el texto está en `index.html`. Busca cada sección por su `id`:

| Sección | Dónde buscar |
|---|---|
| Inicio | `<section id="inicio">` |
| Sobre la escuela | `<section id="escuela">` |
| Audios | `<section id="audios">` |
| Actividades | `<section id="actividades">` |
| Recursos | `<section id="recursos">` |
| Contacto | `<section id="contacto">` |

Los colores y la tipografía se cambian al inicio del archivo, en el bloque `:root` dentro de `<style>`.

### Agregar un audio

1. Guarda el MP3 en la carpeta `audios/` (por ejemplo `audios/charla-04.mp3`).
2. Copia una fila `<li class="fila">…</li>` de la sección Audios y cambia el título, la duración, el peso y las dos rutas del archivo (en `<audio src>` y en el enlace de descarga).

Para que los archivos pesen poco, conviene exportar la voz en MP3 mono a 64 kbps (15 min ≈ 7 MB, 45 min ≈ 22 MB). Con `ffmpeg`:

```
ffmpeg -i original.wav -ac 1 -b:a 64k charla-04.mp3
```

GitHub Pages recomienda sitios de hasta 1 GB aproximadamente; si la colección de audios crece mucho, conviene alojarlos en otro servicio (por ejemplo Internet Archive) y enlazarlos desde la página.

### Agregar una actividad

Copia una fila `<li class="fila">` de la sección Actividades y cambia el día, el mes, el título, el horario y el lugar.

### Cambiar las imágenes

Reemplaza los archivos de `img/` por los nuevos (con el mismo nombre) o cambia las rutas en `index.html`. Recomendado: JPG de unos 1000 px de ancho y menos de 150 KB.

### Mapa de ubicación

En la sección Contacto hay un espacio reservado. Para incrustar un mapa: en Google Maps, **Compartir → Insertar un mapa**, copia el `<iframe>` y reemplaza el `<div class="mapa">…</div>`.

## Créditos

Fotografías de [Unsplash](https://unsplash.com): flor de loto de Cheng Feng y persona meditando de Vitaly Gariev.
