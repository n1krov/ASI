# compilar.sh — Apuntes en Markdown a PDF

Script para convertir apuntes `.md` (de Obsidian / Notion) a PDF usando **pandoc + XeLaTeX**, pensado para estudiar.

Hace todo automáticamente:

- Le pone una cabecera YAML (tomada de tu `header.yaml`) con el título igual al nombre del `.md`.
- Convierte las imágenes de Obsidian `![[Pasted image X.png]]` en imágenes normales apuntando a tu carpeta de imágenes.
- Convierte los wikilinks `[[nota]]` / `[[nota|alias]]` en texto plano.
- Reemplaza o elimina emojis (XeLaTeX no los renderiza con las fuentes de texto).
- Genera el PDF con el mismo nombre que el `.md`.

## Estructura esperada

```
2026/
├── LaTeX/
│   ├── compilar.sh
│   ├── header.yaml          <- cabecera base (o header.yml)
│   └── UNIDAD 3 - Seguridad y Auditoria.md
└── ...
assets/                      <- carpeta de imágenes
```

El script busca `header.yaml` / `header.yml` junto al script y, si no está, junto al `.md`.

## Dependencias

### Arch Linux

```bash
# Pandoc y TeX Live
sudo pacman -S pandoc-cli texlive-xetex texlive-latexextra texlive-fontsextra \
               texlive-fontsrecommended texlive-plaingeneric texlive-langspanish

# Fuentes usadas en el header
sudo pacman -S ttf-libertinus inter-font ttf-jetbrains-mono

# Herramientas que usa el script (normalmente ya vienen instaladas)
sudo pacman -S perl gawk
```

Alternativa más simple pero pesada (varios GB): instalar `texlive-meta` en lugar de la lista de TeX Live de arriba.

Refrescá la caché de fuentes y verificá los nombres:

```bash
fc-cache -fv
fc-list | grep -iE "libertinus|inter|jetbrains"
```

Los nombres que aparecen ahí (`Libertinus Serif`, `Inter`, `JetBrains Mono`) son los que van en `mainfont`, `sansfont` y `monofont` del header.

### Otras distros

Los nombres de los paquetes cambian y no los verifiqué, así que tomalos como orientación. Necesitás los equivalentes de:

- `pandoc`
- XeLaTeX (`texlive-xetex`)
- paquetes extra de LaTeX (`texlive-latex-extra` en Debian/Ubuntu)
- soporte de español para babel (`texlive-lang-spanish` en Debian/Ubuntu)
- las fuentes Libertinus, Inter y JetBrains Mono
- `perl` y `awk`

Si falta algún archivo, `pacman -F nombre.sty` (Arch) o `apt-file search nombre.sty` (Debian/Ubuntu) te dice qué paquete lo trae.

## Uso

```bash
chmod +x compilar.sh    # solo la primera vez

./compilar.sh apunte.md [carpeta_imagenes] [salida.pdf]
```

Ejemplos:

```bash
./compilar.sh "UNIDAD 3 - Seguridad y Auditoria.md" ../../assets
./compilar.sh "UNIDAD 5 - Subsitema de Aplicacion.md" ../../assets
./compilar.sh apunte.md ../../assets resumen.pdf
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
| `Missing character: There is no X` | Un símbolo no existe en la fuente | Quitarlo del `.md`, o agregar un reemplazo en la sección de emojis del script |
| `xdvipdfmx:fatal: Page number 65536 too large` | LaTeX entró en un bucle | Suele ser un paquete conflictivo en el header (por ejemplo `fvextra`) o TeX Live a medias. Probar `sudo pacman -Syu` y simplificar el header |
| `Could not fetch resource` | Pandoc no encuentra una imagen | Verificar la ruta de imágenes |

## Notas

- Los archivos intermedios se crean en una carpeta temporal que se borra al terminar. Tu `.md` original no se modifica.
- Usa XeLaTeX (no pdflatex) para poder usar fuentes del sistema y manejar bien acentos y la ñ.
- Los emojis no se renderizan: 📌 pasa a `»`, ✅ a una tilde, ❌ a una cruz, y el resto se elimina.
- Las imágenes se incluyen con `\floatplacement{figure}{H}` en el header, para que queden donde las pusiste en vez de moverse a otra página.
