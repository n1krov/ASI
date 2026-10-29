# Administración de Sistemas de Información (ASI)

Repositorio colaborativo de apuntes, trabajos prácticos y material de estudio de la materia **Administración de Sistemas de Información**, mantenido como bóveda de Obsidian.

## Dónde está lo interesante y qué se está desarrollando ahora

El desarrollo activo está en [`2026/`](2026/):

- **Apuntes consolidados en Markdown (`2026/`):** resúmenes completos por unidad, revisados en redacción y formato (actualmente listos los de Unidad III y Unidad VI, más la carpeta de Unidad I con su TP y material).
- **PDFs y EPUBs listos para leer ([`2026/build/`](2026/build/)):** versiones ya compiladas de los apuntes para descargar, imprimir o pasar directo al celular/e-reader sin necesidad de compilar nada localmente.
- **Compilador a PDF y EPUB ([`2026/herramientas/`](2026/herramientas/)):** scripts automatizados (`compilar.sh` y `compilar-epub.sh`) que toman las notas de Obsidian/Notion, resuelven imágenes y sintaxis propia (`![[...]]`, wikilinks, bloques matemáticos), aplican plantillas tipográficas y generan por defecto en `2026/build/` los documentos en PDF (Pandoc + XeLaTeX) y EPUB.

## Estructura del repositorio

```
ASI/
├── 2026/                   <- Cursada actual: apuntes activos y herramientas PDF/EPUB
├── 2025/                   <- Archivo de la cursada 2025 (unidades, parciales y recuperatorio)
├── assets/                 <- Imágenes y capturas compartidas por las notas de Obsidian
├── Otros/                  <- Actividades, laboratorios, talleres y diagramas (.drawio)
├── plantillas/             <- Plantillas de Markdown y criterios para redactar apuntes
└── APUNTE 2 parcial.md     <- Compilado previo de estudio del segundo parcial
```

## Cómo usar este repositorio

- **En Obsidian:** abrí la raíz del repositorio como bóveda (*vault*) para que las imágenes de `assets/` se resuelvan automáticamente. Tema sugerido: *Blue Topaz*.
- **Para generar PDFs o EPUBs:** entrá a [`2026/herramientas/README.md`](2026/herramientas/README.md), donde están documentadas las dependencias y los comandos de compilación.
