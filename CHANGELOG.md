# Historial de cambios

Todos los cambios de la base EPUB 3 de ZeePubs (`template/`). El formato sigue
[Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/) y las versiones usan
[versionado semántico](https://semver.org/lang/es/).

Las fechas salen del `dcterms:modified` que Sigil escribió en el `content.opf` de
cada base. Las marcadas como *aprox.* no tienen registro propio y se dedujeron de
las versiones vecinas. Las versiones `-test` fueron pruebas que se compartieron
pero no se adoptaron tal cual.

## [1.14.2] - 2023-09-03 *(aprox.)*

### Cambiado

- `cubierta.xhtml` reformateado (espaciado y cierre de etiquetas), sin cambios en
  el resultado.

## [1.14.1] - 2023-09-03

### Corregido

- Comentario de la regla de sangría francesa en `style.css`: no sangra la primera
  línea y sirve para bibliografías.

## [1.14.0] - 2023-07-03

### Cambiado

- En `notas.xhtml` el `id` de cada nota pasa del enlace al párrafo
  (`<p id="nt1"><a href="…#rf1">`), así el destino de la llamada es la nota
  completa.

## [1.13.5] - 2022-12-17

### Cambiado

- La sección de notas usa `epub:type="endnotes"` en lugar de `rearnotes`, que
  EPUBCheck marca como obsoleto. Los EPUB anteriores no necesitan cambiarse a mano.

## [1.13.4] - 2022-10-26

### Cambiado

- Los números de nota llevan los signos `❮❯` y dos dígitos (`❮01❯`) para que sean
  fáciles de pulsar en pantallas pequeñas. Es obligatorio mantenerlos.
- Más ejemplos de géneros literarios en los metadatos.

## [1.13.3] - 2022-10-13

### Corregido

- El atributo `title` del capítulo va en el `h1.oculto` y no en el título visible.

### Eliminado

- Separador `hr.sigil_split_marker` entre los logotipos.

## [1.13.2] - 2022-10-01

### Cambiado

- Imágenes de ejemplo optimizadas.
- Separadores `hr.sigil_split_marker` para dividir el contenido con Sigil.
- La sangría de párrafo queda como regla comentada en `style.css`.
- El `uuid` se genera con el complemento Template3 de Sigil.

## [1.13.1] - 2022-09-26

### Cambiado

- `sigil_not_in_toc` en la sinopsis y en el título que sigue a una imagen de
  título, para que no se dupliquen en el índice.
- Ejemplo de texto grande centrado (`p.grande.centrado`).

## [1.13.0] - 2022-09-22

### Añadido

- Sección `logos.xhtml` y logotipo de ZeePubs.
- `META-INF/com.apple.ibooks.display-options.xml` para que Apple Books use las
  fuentes incrustadas.
- Comentarios en cada sección que explican qué va en ella.

### Cambiado

- El `uuid` se movió al inicio de los metadatos para ubicarlo y saber si ya se
  reemplazó.
- `big` y la nueva clase `.grande` comparten estilo.

### Eliminado

- La etiqueta `big` en la página de título.

## [1.12.0] - 2022-03-20

### Añadido

- Secciones de sinopsis (`sinopsis.xhtml`) y palabras iniciales (`perfil.xhtml`).

### Cambiado

- «Palabras del autor» pasa a llamarse «Palabras finales».

## [1.11.1] - 2022-03-16

### Cambiado

- Los títulos `h1` y las entradas del índice usan mayúscula solo al inicio
  (*sentence case*), y es obligatorio a partir de esta versión.
- Entrada de «Contenido» en el índice.

## [1.11.0] - 2022-02-12

### Cambiado

- Ejemplos de la base y de los metadatos corregidos: título, nombre de la serie y
  géneros literarios, con un ejemplo de dos demografías.
- `.identar` y `.noidentar` también se aplican a los párrafos dentro de un bloque.
- Nueva sección de ejemplo `Section0002.xhtml`.

## [1.11.0-test] - 2022-02-12

Prueba de títulos alternativos en el OPF (`main`, `subtitle`, `collection`,
`short` y `expanded`) para ver cómo los muestra cada lector. No se adoptó. Se
distribuyó como «1.11.1 (prueba)» y como `Base3_v1.11.2-test.epub`.

## [1.10.0] - 2022-01-31

### Cambiado

- `nav.xhtml` pasa a llamarse `toc.xhtml` y concentra el índice; el antiguo
  `toc.xhtml` pasa a ser `contenido.xhtml`.
- En el nav oculto (`<h2>Guías</h2>`) el `href` va antes que `epub:type`, para
  facilitar reemplazos masivos (por ejemplo para Kavita).
- Nuevo estilo para listas anidadas en `nav-style.css`.

### Añadido

- Sección `contracubierta.xhtml`.

### Eliminado

- `toc-style.css` y la lista manual del índice antiguo.

## [1.9.0] - 2022-01-30 *(aprox.)*

### Cambiado

- Sección de listas de `style.css`: las listas tienen su propio margen y dentro de
  un bloque (`div`) se pegan como los párrafos.

### Corregido

- La regla de `@media amzn-mobi` del `h3` estaba escrita como `h2`.

## [1.8.0] - 2022-01-30 *(aprox.)*

### Añadido

- Ejemplos de cómo poner el título (`h1`) de un capítulo que empieza con o sin
  imagen.

### Cambiado

- Se descartaron los cambios de la prueba 1.7.1.

## [1.7.1-test] - 2022-01-30

Prueba de notas e índice para mejorar la compatibilidad con Kavita. Se descartó en
la 1.8.0, aunque la 1.10.0 retomó su índice.

## [1.7.0] - 2021-11-20

### Eliminado

- `<h1 class="oculto" title="Créditos" id="sigil_toc_id_1">` en la página de
  título: al convertir a KFX la referencia apunta a un elemento oculto y falla.
  Usar `class="oculto"` solo en el `h1` o `h2` que sea el título principal del
  documento. Para comprobar conversiones:
  [Kindle Previewer](https://www.amazon.com/Kindle-Previewer/b?node=21381691011)
  o el [complemento KFX Output de calibre](https://www.mobileread.com/forums/showthread.php?t=272407).

### Cambiado

- El nav lleva `role="doc-toc"` y un ejemplo de subnivel.

## [1.6.0] - 2021-07-31

### Cambiado

- `h2.subtitulo` usa `font-family: sans-serif`.

### Corregido

- `<title>` de epígrafe y prefacio.

## [1.5.0] - 2021-04-26

### Cambiado

- `h2.subtitulo` en negrita.

## [1.4.0] - 2021-04-04

### Añadido

- Los títulos van dentro de `<header>`.

### Cambiado

- Margen superior de `h1.titulo`.
- Marcadores genéricos en la página de título (título principal, volumen 01).

## [1.3.0] - 2021-03-31

### Añadido

- Serie en los metadatos (`belongs-to-collection`, `collection-type` y
  `group-position`).

## [1.2.0] - 2021-03-29

### Cambiado

- Las clases `sepag-ant` y `sepag-sig` pasan a llamarse `santes` y `ssigue`.

### Añadido

- Clase `span.separador` para forzar un salto de página.

## [1.1.0] - 2021-03-27

### Cambiado

- Las imágenes ya no usan unidades `vh` ni `vw`.
- `toc-style.css` incrusta la fuente y define los títulos.

### Añadido

- Clases `figure.banner`, `img.entexto` y `.listar`.

## [1.0.0] - 2021-03-23

### Cambiado

- La clase de imagen `pagina` pasa a llamarse `dimg`.
- Ejemplos de contenido en prólogo, epígrafe, prefacio y resumen.
- La página de título también es la de créditos (`copyright-page`).

## [0.4.0] - 2021-03-18

Primera versión pública.

## Antes de 0.4.0

Antes de la base completa solo existía la hoja de estilos, que se copiaba a cada
EPUB. Sus fechas son aproximadas.

- **2021-01-07**: imágenes a página completa (`div.dimg`, `div.pagina`,
  `div.seguida`), logos y separadores (`div.logo`, `div.hr`), subrayado y tachado
  (`ins`, `del`), y sin sangría por defecto.
- **2020-12 *(aprox.)***: márgenes explícitos en los párrafos, clase `.izquierda`
  y estilo de `h4`.
- **2020-12 *(aprox.)***: primera hoja de estilos (reinicio, párrafos, notas,
  imágenes, tipografía, alineación y encabezados).

[1.14.2]: https://github.com/zeedif/epub-templates/releases/tag/v1.14.2
[1.14.1]: https://github.com/zeedif/epub-templates/releases/tag/v1.14.1
[1.14.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.14.0
[1.13.5]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.5
[1.13.4]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.4
[1.13.3]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.3
[1.13.2]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.2
[1.13.1]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.1
[1.13.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.13.0
[1.12.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.12.0
[1.11.1]: https://github.com/zeedif/epub-templates/releases/tag/v1.11.1
[1.11.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.11.0
[1.11.0-test]: https://github.com/zeedif/epub-templates/releases/tag/v1.11.0-test
[1.10.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.10.0
[1.9.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.9.0
[1.8.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.8.0
[1.7.1-test]: https://github.com/zeedif/epub-templates/releases/tag/v1.7.1-test
[1.7.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.7.0
[1.6.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.6.0
[1.5.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.5.0
[1.4.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.4.0
[1.3.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.3.0
[1.2.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.2.0
[1.1.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.1.0
[1.0.0]: https://github.com/zeedif/epub-templates/releases/tag/v1.0.0
[0.4.0]: https://github.com/zeedif/epub-templates/releases/tag/v0.4.0
