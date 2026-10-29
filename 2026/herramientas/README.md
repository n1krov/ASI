# compilar.sh — Apuntes en Markdown a PDF

Script para convertir apuntes `.md` (de Obsidian / Notion) a PDF usando **pandoc + XeLaTeX**, pensado para estudiar.

Hace todo automáticamente:

- Le pone una cabecera YAML (tomada de tu `header.yaml`) con el título igual al nombre del `.md` (si el archivo ya tenía un front matter `--- ... ---`, lo reemplaza).
- Convierte las imágenes de Obsidian `![[Pasted image X.png]]` (con o sin tamaño `|400`) en imágenes normales apuntando a tu carpeta de imágenes.
- Convierte los wikilinks `[[nota]]` / `[[nota|alias]]` en texto plano.
- Normaliza letras matemáticas Unicode (`𝐴`, `𝑓`, `𝛼`, etc.) y reemplaza o elimina emojis (XeLaTeX no los renderiza con las fuentes de texto).
- Genera el PDF con el mismo nombre que el `.md`.

## Estructura esperada

```
ASI/
├── 2026/
│   ├── LaTeX/
│   │   ├── compilar.sh
│   │   ├── header.yaml                             <- cabecera base (o header.yml)
│   │   ├── Unidad III - Subsistema de Aplicación.md
│   │   └── Unidad VI - Seguridad y Auditoría.md
│   └── ...
└── assets/                                         <- carpeta de imágenes (../../assets desde LaTeX/)
```

El script busca `header.yaml` / `header.yml` junto al script y, si no está, junto al `.md`.

## Dependencias

### Arch Linux

```bash
# Pandoc y TeX Live
sudo pacman -S pandoc-cli texlive-xetex texlive-latexextra texlive-fontsextra \
               texlive-fontsrecommended texlive-plaingeneric texlive-langspanish

# Fuentes usadas en el header (texto, títulos, código y símbolos Unicode)
sudo pacman -S ttf-libertinus inter-font ttf-jetbrains-mono ttf-dejavu

# Herramientas que usa el script (normalmente ya vienen instaladas)
sudo pacman -S perl gawk
```

Alternativa más simple pero pesada (varios GB): instalar `texlive-meta` en lugar de la lista de TeX Live de arriba.

Refrescá la caché de fuentes y verificá los nombres:

```bash
fc-cache -fv
fc-list | grep -iE "libertinus|inter|jetbrains|dejavu sans"
```

Los nombres que aparecen ahí son los que usa `header.yaml`:
- `Libertinus Serif` (`mainfont`, texto principal)
- `Inter` (`sansfont`, títulos y encabezados)
- `JetBrains Mono` (`monofont`, bloques de código)
- `DejaVu Sans` (`\symfont`, símbolos Unicode como `►` y `✓`)

### Otras distros

Los nombres de los paquetes cambian y no los verifiqué, así que tomalos como orientación. Necesitás los equivalentes de:

- `pandoc`
- XeLaTeX (`texlive-xetex`)
- paquetes extra de LaTeX (`texlive-latex-extra` en Debian/Ubuntu)
- soporte de español para babel (`texlive-lang-spanish` en Debian/Ubuntu)
- las fuentes Libertinus, Inter, JetBrains Mono y DejaVu Sans (`fonts-dejavu-core` en Debian/Ubuntu)
- `perl` y `awk`

Si falta algún archivo, `pacman -F nombre.sty` (Arch) o `apt-file search nombre.sty` (Debian/Ubuntu) te dice qué paquete lo trae.

## Uso

Parado dentro de `2026/LaTeX/`:

```bash
chmod +x compilar.sh    # solo la primera vez

./compilar.sh apunte.md [carpeta_imagenes] [salida.pdf]
```

Ejemplos:

```bash
./compilar.sh "Unidad III - Subsistema de Aplicación.md" ../../assets
./compilar.sh "Unidad VI - Seguridad y Auditoría.md" ../../assets
./compilar.sh "Unidad VI - Seguridad y Auditoría.md" ../../assets resumen-u6.pdf
```

| Argumento | Descripción | Por defecto |
|---|---|---|
| `apunte.md` | Archivo a convertir | (obligatorio) |
| `carpeta_imagenes` | Carpeta donde están las imágenes | `.` (carpeta actual) |
| `salida.pdf` | Nombre del PDF | mismo nombre que el `.md` |

### Variables opcionales

```bash
HEADER=/otra/ruta/header.yaml ./compilar.sh apunte.md ../../assets   # usar otra cabecera
AUTOR="Otro nombre" ./compilar.sh apunte.md ../../assets             # cambiar el author:
```

## Qué hacer si algo falla

| Error | Causa probable | Solución |
|---|---|---|
| `Package babel Error: Unknown option 'spanish'` | Falta el soporte de español de TeX | Instalar `texlive-langspanish`. Si ya está instalado, reinstalarlo para que se regeneren los formatos, o correr `sudo mktexlsr && sudo fmtutil-sys --all` |
| `The font "X" cannot be found` | El nombre de la fuente en el header no coincide con el del sistema | Mirar `fc-list` y ajustar `mainfont`/`sansfont`/`monofont` |
| `AVISO: no se encuentra la imagen: ...` | La carpeta de imágenes es incorrecta o la imagen no existe | Revisar el segundo argumento y el nombre del archivo |
| `Missing character: There is no X` | Un símbolo no existe en la fuente principal | Agregar `\newunicodechar{X}{{\symfont X}}` en `header.yaml` (si está en `DejaVu Sans`), o un reemplazo en la sección de emojis de `compilar.sh` |
| `xdvipdfmx:fatal: Page number 65536 too large` | LaTeX entró en un bucle | Suele pasar por paquetes incompatibles en el header o una actualización de TeX Live a medias. Probar `sudo pacman -Syu` y revisar los paquetes de `header-includes` en `header.yaml` |
| `Could not fetch resource` | Pandoc no encuentra una imagen | Verificar la ruta de imágenes |

## Notas

- Los archivos intermedios se crean en una carpeta temporal que se borra al terminar. Tu `.md` original no se modifica.
- Usa XeLaTeX (no pdflatex) para poder usar fuentes del sistema y manejar bien acentos y la ñ.
- Los emojis no se renderizan con las fuentes normales: 📌 pasa a `»`, ✅ / ✓ / ✔ pasan a `$\checkmark$`, ❌ / ✖ pasan a `$\times$`, y el resto de emojis se elimina.
- Las imágenes se incluyen con `\floatplacement{figure}{H}` en el header, para que queden donde las pusiste en vez de moverse a otra página.
- Los bloques de código usan `fvextra` con `breaklines` en el header para que las líneas largas hagan salto de línea automático en vez de salirse del margen.
