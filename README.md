# Plantillas de ePubs

Base EPUB 3 que usamos en ZeePubs para maquetar novelas ligeras con Sigil entre
2021 y 2023. Hoy las plantillas se generan con ZeeTools (EPUB 3.4); esta base se
conserva como referencia y para mantener los EPUB que se hicieron con ella.

## Estructura

- [`template/`](template): archivos de la base (`mimetype`, `META-INF/` y `OEBPS/`).
  - [`style.css`](template/OEBPS/Styles/style.css)
- [`CHANGELOG.md`](CHANGELOG.md): qué cambió en cada versión y cuándo.

## Descargar

Al etiquetar una versión se publica su EPUB en
[Releases](https://github.com/zeedif/epub-templates/releases). El EPUB solo lleva
el contenido de `template/`.

## Vista previa de Markdown

La hoja de estilos se publica en GitHub Pages, así que sirve como estilo de la
vista previa de Markdown en VS Code:

```json
"markdown.styles": ["https://zeedif.github.io/epub-templates/template/OEBPS/Styles/style.css"]
```

## Licencia

Este proyecto está bajo la [Licencia MIT](LICENSE).
