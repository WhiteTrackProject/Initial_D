INITIAL D · TOUGE NAVIGATOR v5

INCLUYE
- Intro preparada para vídeo real o imagen (editable desde site-config.js)
- Hero/banner grande arriba con 'seguir viendo'
- Banners por stage (rutas configurables en site-config.js)
- Sinopsis configurables por episodio (site-config.js)
- Títulos bonitos en manifest.js
- Vista stages + cronológica
- Modal con navegación
- Seguir viendo / continuar siguiente

INSTALACIÓN
1) Copia todo esto en la carpeta raíz de tu serie Initial D.
2) Deja ahí también 'Orden Cronologico.txt'.
3) Ejecuta en PowerShell:
   powershell -ExecutionPolicy Bypass -File .\generate-manifest.ps1
4) Abre index.html

INTRO REAL
- Pon tu vídeo en assets/intro/intro.mp4
- O una imagen en assets/intro/intro-poster.jpg
- Ajusta site-config.js:
  intro.mode = "video" | "image" | "auto" | "none"

BANNERS
- Mete imágenes en assets/banners/
- Cambia las rutas en site-config.js

SINOPSIS
- Edita site-config.js
- Clave ejemplo: "First Stage::1"

CARÁTULAS
- Pon imágenes en assets/covers con el mismo nombre base que el vídeo

NOTA
- Si renombras o añades archivos, vuelve a ejecutar el .ps1


---

PORTADAS AUTOMÁTICAS DESDE LOS VÍDEOS

Este pack incluye:
- generate-covers-from-videos.ps1

Qué hace
- Recorre todos los vídeos de la carpeta de la serie
- Saca 1 fotograma de cada archivo
- Lo guarda en assets/covers con el mismo nombre base del vídeo
- El menú lo usa automáticamente como imagen de cada capítulo

Requisitos
- Tener ffmpeg y ffprobe instalados y accesibles desde PowerShell

Uso básico
  powershell -ExecutionPolicy Bypass -File .\generate-covers-from-videos.ps1

Opciones útiles
- Elegir qué porcentaje del vídeo capturar:
  powershell -ExecutionPolicy Bypass -File .\generate-covers-from-videos.ps1 -CaptureRatio 0.35

- Regenerar todas las imágenes aunque ya existan:
  powershell -ExecutionPolicy Bypass -File .\generate-covers-from-videos.ps1 -Overwrite

- Sacarlas más pequeñas o grandes:
  powershell -ExecutionPolicy Bypass -File .\generate-covers-from-videos.ps1 -Width 640

Consejo
- 0.35 suele dar una imagen bastante decente
- Si algún capítulo sale con una imagen mala, luego puedes reemplazar solo esa JPG a mano
