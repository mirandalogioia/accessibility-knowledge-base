---
title: "WCAG 2.2 Techniques — HTML"
status: in_progress
last_updated: 2026-10-13
---

# Técnicas HTML (52)

> Ejemplos de formas de cumplir WCAG 2.2 usando HTML. No son obligatorias: el contenido puede cumplir WCAG sin usar exactamente estas técnicas. Fuente: [W3C WAI — Techniques/html](https://www.w3.org/WAI/WCAG22/Techniques/html/).

### H2: Combinar enlaces de imagen y texto adyacentes para el mismo recurso
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente); 2.4.4 Propósito del enlace en contexto y 2.4.9 Propósito del enlace solo enlace (Consultivo)
**Qué hace:** Evita enlaces duplicados cuando una imagen y un texto adyacentes apuntan al mismo recurso: ambos se unen dentro de un único `<a>` y la imagen recibe `alt` vacío.
**Ejemplo:**
```html
<a href="products.html"><img src="icon.gif" alt="">Products page</a>
```
**Cómo testearlo:** Verificar que toda imagen dentro del `<a>` tenga `alt` nulo y que el enlace combinado describa correctamente el destino.

### H24: Proporcionar alternativas de texto para elementos area en mapas de imagen
**Se relaciona con:** 1.1.1 Contenido no textual; 2.4.4 y 2.4.9 Propósito del enlace (Suficiente)
**Qué hace:** Añade el atributo `alt` a cada `<area>` de un mapa de imagen para describir la función de cada región seleccionable.
**Ejemplo:**
```html
<img src="welcome.gif" usemap="#map1" alt="Areas in the library">
<map id="map1" name="map1">
  <area shape="rect" coords="0,0,30,30" href="reference.html" alt="Reference">
</map>
```
**Cómo testearlo:** Verificar que cada `area` tenga `alt` y que el texto cumpla la misma función que el área visual.

### H25: Proporcionar un título mediante el elemento title
**Se relaciona con:** 2.4.2 Título de página (Suficiente, junto con G88)
**Qué hace:** Incluye un `<title>` no vacío en el `<head>` que describa claramente el propósito del documento.
**Ejemplo:**
```html
<head><title>The World Wide Web Consortium</title></head>
```
**Cómo testearlo:** Confirmar que existe un `<title>` no vacío y que describe adecuadamente el documento.

### H28: Proporcionar definiciones para abreviaturas usando el elemento abbr
**Se relaciona con:** 3.1.4 Abreviaturas (Consultivo)
**Qué hace:** Usa `<abbr title="...">` para dar la expansión de abreviaturas, acrónimos e inicialismos; se bajó a Advisory porque el atributo `title` no siempre es accesible (p. ej. solo teclado o táctil).
**Ejemplo:**
```html
<p>Welcome to the <abbr title="World Wide Web">WWW</abbr>!</p>
```
**Cómo testearlo:** Verificar que cada abreviatura tenga su expansión/definición provista vía `abbr`.

### H30: Proporcionar texto de enlace que describe el propósito del enlace
**Se relaciona con:** 1.1.1 Contenido no textual; 2.4.4 y 2.4.9 Propósito del enlace (Suficiente)
**Qué hace:** El contenido del `<a>` (texto o alternativa de imagen) debe describir por sí mismo el propósito del enlace.
**Ejemplo:**
```html
<a href="routes.html">Current routes at Boulders Climbing Gym</a>
```
**Cómo testearlo:** Confirmar que el texto o alternativa del enlace describe claramente su propósito, ya sea solo texto, solo imagen, o ambos.

### H32: Proporcionar botones de envío
**Se relaciona con:** 3.2.2 Al recibir entradas (Suficiente, junto con G80)
**Qué hace:** Incluye un control explícito de envío para que los cambios de contexto (envío de formulario) ocurran solo cuando el usuario lo solicita.
**Ejemplo:**
```html
<form action="/subscribe" method="post">
 <input type="submit" value="Subscribe">
</form>
```
**Cómo testearlo:** Verificar que cada formulario incluya un botón de envío (`input type="submit"`, `type="image"` o `button type="submit"`).

### H33: Complementar el texto de enlace con el atributo title
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente); 2.4.9 Propósito del enlace solo enlace (Consultivo)
**Qué hace:** Usa el atributo `title` para aclarar o ampliar el propósito de un enlace; se recomienda cautela por soporte limitado en navegadores (preferir C7 o H30).
**Ejemplo:**
```html
<a href="kenya.elephants.html" title="Read more about failed elephant evacuation">
  Evacuation Crumbles Under Jumbo Load
</a>
```
**Cómo testearlo:** Para cada `a` con `title`, verificar que el atributo junto con el texto del enlace describa adecuadamente su propósito.

### H34: Uso de marcas Unicode de dirección de texto (RLM/LRM)
**Se relaciona con:** 1.3.2 Secuencia significativa (Suficiente, junto con G57)
**Qué hace:** Inserta caracteres Unicode invisibles (`&lrm;`/`&rlm;`) para corregir la posición visual de caracteres neutros (espacios, puntuación) cuando se mezclan textos de dirección izquierda-derecha y derecha-izquierda.
**Ejemplo:** Insertar una marca RLM tras un signo de exclamación dentro de una frase árabe incrustada para que se posicione correctamente.
**Cómo testearlo:** Identificar cambios de dirección de texto y verificar que los caracteres neutros adyacentes incluyan la marca Unicode adecuada.

### H36: Uso de atributos alt en imágenes usadas como botones de envío
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Da a `<input type="image">` un `alt` que describa la función del botón, no su apariencia, clave cuando hay varios botones de envío distintos.
**Ejemplo:**
```html
<input alt="Search" src="button.gif" type="image">
```
**Cómo testearlo:** Verificar que todo `input type="image"` tenga `alt` y que este describa la función del botón.

### H37: Uso de atributos alt en elementos img
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Proporciona texto alternativo en imágenes que transmita el mismo significado que la imagen, no solo su descripción visual.
**Ejemplo:**
```html
<img src="newsletter.gif" alt="Free newsletter. Get free recipes, news, and more. Learn more.">
```
**Cómo testearlo:** Verificar que cada imagen con significado tenga `alt` y que incluya las palabras clave que la imagen transmite.

### H39: Uso de elementos caption para asociar títulos a tablas de datos
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Asocia programáticamente el título de una tabla con `<caption>`, manteniendo el vínculo visual y de código, y permitiendo navegación directa con lectores de pantalla.
**Ejemplo:**
```html
<table><caption>Schedule for the week of March 6</caption>...</table>
```
**Cómo testearlo:** Verificar que toda tabla con título use `caption` y que el texto del título esté contenido en ese elemento.

### H40: Uso de listas de descripción
**Se relaciona con:** 3.1.3 Palabras inusuales (Suficiente, junto con G55)
**Qué hace:** Marca pares término-descripción con `dl`/`dt`/`dd`, manteniendo la relación semántica entre términos y sus definiciones.
**Ejemplo:**
```html
<dl><dt>Knot</dt><dd>A knot is a unit of speed...</dd></dl>
```
**Cómo testearlo:** Verificar estructura `dl > dt/dd`, que términos compartidos tengan `dt` consecutivos y que cada `dd` siga inmediatamente a su `dt`.

### H42: Identificar encabezados con h1-h6
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Usa marcado semántico `h1`-`h6` para encabezados, permitiendo que las tecnologías asistivas anuncien el nivel y faciliten la navegación.
**Ejemplo:**
```html
<h1>Plant Foods that Humans Eat</h1>
<h2>Fruit</h2>
<h3>Apple</h3>
```
**Cómo testearlo:** Verificar que todo contenido que funcione como encabezado use el nivel de marcado correspondiente, y que no se use marcado de encabezado en contenido que no lo es.

### H43: Asociación de celdas de datos con celdas de encabezado mediante id y headers
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Vincula cada celda de datos con sus encabezados correspondientes en tablas complejas, añadiendo el atributo `headers` (que referencia los `id` de los encabezados) cuando una celda se relaciona con múltiples encabezados de fila y/o columna.
**Ejemplo:** Tabla con encabezados múltiples donde cada celda de datos usa `headers="id1 id2"` apuntando a los `id` de sus `th` correspondientes.
**Cómo testearlo:** Verificar que las celdas asociadas a varios encabezados tengan `headers` válido y que los `id` referenciados existan y sean únicos en la página.

### H44: Uso del elemento label para asociar etiquetas de texto con controles de formulario
**Se relaciona con:** 1.1.1 Contenido no textual, 1.3.1 Información y relaciones, 3.3.2 Etiquetas o instrucciones, 4.1.2 Nombre, rol, valor (Suficiente)
**Qué hace:** Vincula explícitamente una etiqueta de texto con su control de formulario mediante el atributo `for`, cuyo valor debe coincidir con el `id` del control.
**Ejemplo:** `<label for="firstname">First name:</label> <input id="firstname" name="firstname" type="text">`
**Cómo testearlo:** Confirmar que cada control tenga un `label` con `for` que coincida con su `id`, y que la etiqueta sea visible.

### H48: Uso de ol, ul y dl para listas o grupos de enlaces
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Marca listas semánticamente con `<ol>` (ordenadas), `<ul>` (no ordenadas) o `<dl>` (pares término-definición), permitiendo que las tecnologías asistivas naveguen entre elementos de lista.
**Ejemplo:** `<ol><li>Mix flour, eggs, milk...</li><li>Whisk until smooth.</li></ol>`
**Cómo testearlo:** Verificar que contenido con apariencia visual de lista (numerada, con viñetas, o pares nombre-valor) use el elemento HTML de lista correspondiente.

### H49: Uso de marcado semántico para texto enfatizado o especial
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente, junto con G115)
**Qué hace:** Usa elementos semánticos (`em`, `strong`, `cite`, `blockquote`, `sub`, `sup`) para que el énfasis o carácter especial del texto sea programáticamente determinable, no solo visual.
**Ejemplo:** `What she <em>really</em> meant to say was, "This is <strong>excellent</strong>"!`
**Cómo testearlo:** Identificar texto cuya presentación visual comunica información y verificar que tenga el marcado semántico apropiado.

### H51: Uso de marcado de tabla para presentar información tabular
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Usa elementos `table`, `tr`, `th` y `td` para datos con relaciones lógicas de filas y columnas, manteniendo las conexiones perceptibles para lectores de pantalla.
**Ejemplo:** Tabla de horario semanal con `th` para días (columnas) y horarios (`scope="row"`), y `td` para los datos.
**Cómo testearlo:** Verificar que la información tabular use efectivamente `table`/`tr`/`th`/`td` en lugar de otros elementos (como listas o divs).

### H53: Uso del cuerpo del elemento object
**Se relaciona con:** 1.1.1 Contenido no textual, 1.2.3 Descripción de audio o alternativa (grabado), 1.2.8 Alternativa a medios (grabado) (Suficiente)
**Qué hace:** Proporciona una alternativa textual dentro del cuerpo de un elemento `object`, que se muestra cuando el navegador no soporta ese contenido o el usuario lo deshabilitó.
**Ejemplo:** `<object data="companylogo.gif" type="image/gif"><p>Company Name</p></object>`
**Cómo testearlo:** Verificar que el cuerpo de cada `object` contenga una alternativa de texto adecuada.

### H54: Uso del elemento dfn para identificar la instancia definitoria de una palabra o frase
**Se relaciona con:** 3.1.3 Palabras inusuales (Suficiente, con G112)
**Qué hace:** Marca con `<dfn>` el término (no la definición completa) en el punto donde se define por primera vez en el texto.
**Ejemplo:** `Non-text content requires alternatives. <dfn>Non-text content</dfn> is content that is not a sequence of characters...`
**Cómo testearlo:** Identificar términos definidos en línea y verificar que cada uno esté envuelto en un elemento `dfn`.

### H56: Uso del atributo dir en elementos inline
**Se relaciona con:** 1.3.2 Secuencia significativa (Suficiente, junto con G57)
**Qué hace:** Resuelve problemas de dirección de texto en contenido bidireccional usando `dir` en elementos inline (ej. `span`), para casos que el algoritmo bidireccional Unicode no maneja bien (espacios/puntuación en texto mixto).
**Ejemplo:** `<span lang="he" dir="rtl">פעילות הבינאום, W3C</span>` corrige la posición de "W3C" dentro del texto hebreo.
**Cómo testearlo:** Verificar que el texto RTL tenga un ancestro con `dir="rtl"` y el texto LTR no tenga `dir` o tenga `dir="ltr"`.

### H57: Uso del atributo lang en el elemento html
**Se relaciona con:** 3.1.1 Idioma de la página (Suficiente)
**Qué hace:** Identifica el idioma predeterminado del documento mediante `lang` en `<html>`, beneficiando lectores braille, sintetizadores de voz y traducción automática.
**Ejemplo:** `<html lang="fr"><head>...<title>document écrit en français</title></head>...</html>`
**Cómo testearlo:** Verificar que `html` tenga atributo `lang` válido según BCP 47 y que refleje el idioma principal del sitio.

### H58: Uso de atributos de idioma para identificar cambios en el lenguaje humano
**Se relaciona con:** 3.1.2 Idioma de las partes (Suficiente)
**Qué hace:** Usa el atributo `lang` (con subcódigos opcionales como "en-GB") para marcar cambios de idioma dentro de la página respecto al idioma principal.
**Ejemplo:** `<blockquote lang="de"><p>Da dachte der Herr daran...</p></blockquote>`
**Cómo testearlo:** Para cada elemento, confirmar que el idioma del contenido coincide con el especificado en `lang`/`xml:lang` y que el código cumple BCP 47.

### H62: Uso del elemento ruby
**Se relaciona con:** 3.1.6 Pronunciación (Suficiente)
**Qué hace:** Proporciona anotaciones de pronunciación mediante `rb` (texto base), `rt` (anotación) y `rp` (paréntesis de respaldo), útil en idiomas donde el significado depende de la pronunciación.
**Ejemplo:** `<ruby><rb>WCAG</rb><rp>(</rp><rt>Wuh-KAG</rt><rp>)</rp></ruby>`
**Cómo testearlo:** Verificar que cada `rt` tenga la pronunciación correspondiente y que `rp` esté presente para navegadores sin soporte ruby.

### H63: Uso del atributo scope para asociar celdas de encabezado con celdas de datos
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Usa `scope="row"/"col"/"rowgroup"/"colgroup"` en `th` para tablas simples donde los encabezados no están en la primera fila/columna.
**Ejemplo:** `<th scope="col">Name</th>` en el encabezado de columna y `<th scope="row">Charlotte Smith</th>` en el de fila.
**Cómo testearlo:** Verificar que todos los `th` tengan `scope` con un valor válido (row, col, rowgroup o colgroup).

### H64: Uso del atributo title en elementos iframe
**Se relaciona con:** 2.4.1 Evitar bloques (Suficiente), 4.1.2 Nombre, rol, valor (Suficiente, con G108)
**Qué hace:** Describe el contenido de un `iframe` mediante su atributo `title`, dándole una etiqueta accesible distinta del `title` del documento que carga.
**Ejemplo:** `<iframe src="banner-ad.html" name="ad-iframe" title="Advertisement"></iframe>`
**Cómo testearlo:** Verificar que cada `iframe` tenga atributo `title` y que su contenido describa adecuadamente lo que hay dentro del marco.

### H65: Uso del atributo title para identificar controles de formulario
**Se relaciona con:** 1.1.1 Contenido no textual, 1.3.1 Información y relaciones, 4.1.2 Nombre, rol, valor (Suficiente, con condiciones)
**Qué hace:** Da nombre accesible a un control de formulario mediante el atributo `title` cuando no es posible usar un `label` visible asociado.
**Ejemplo:** `<select title="Search in" id="scope">...</select>` junto a un campo con `label` visible.
**Cómo testearlo:** Verificar que los controles sin `label` tengan `title`, que su propósito sea claro visualmente y que el texto coincida con ese propósito.

### H67: Uso de alt vacío y sin atributo title en imágenes decorativas
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Marca imágenes decorativas o redundantes para que las tecnologías de asistencia las ignoren, usando `alt=""` y sin `title`.
**Ejemplo:** `<img alt="" src="squiggle.gif" height="20" width="20">`
**Cómo testearlo:** Comprobar que el atributo `title` esté ausente o vacío y que `alt` esté presente y vacío.

### H69: Encabezados al inicio de cada sección de contenido
**Se relaciona con:** 2.4.1 Evitar bloques, 2.4.10 Encabezados de sección (Suficiente)
**Qué hace:** Usa elementos de encabezado (`h1`-`h6`) jerárquicos al comienzo de cada sección para estructurar el contenido y permitir navegación directa.
**Ejemplo:** `<h1>Técnicas de cocina</h1> ... <h2>Cocinar con aceite</h2> ... <h2>Cocinar con mantequilla</h2>`
**Cómo testearlo:** Verificar que el contenido esté dividido en secciones y que cada una comience con un encabezado.

### H71: Fieldset y legend para agrupar controles de formulario
**Se relaciona con:** 1.3.1 Información y relaciones, 3.3.2 Etiquetas o instrucciones (Suficiente)
**Qué hace:** Agrupa controles relacionados (radios, checkboxes) dentro de `fieldset` con un `legend` que describe el grupo.
**Ejemplo:** `<fieldset><legend>Intereses:</legend><input type="checkbox" id="photo" name="interests"><label for="photo">Fotografía</label></fieldset>`
**Cómo testearlo:** Confirmar que los grupos de controles estén dentro de `fieldset` y que cada uno tenga un `legend` como primer hijo.

### H76: Redirección instantánea del lado del cliente con meta refresh
**Se relaciona con:** 3.2.5 Cambios a petición del usuario (Suficiente, junto con G110)
**Qué hace:** Redirige al usuario de forma instantánea mediante `<meta http-equiv="refresh">` con tiempo 0, en lugar de una redirección retardada o del servidor.
**Ejemplo:** `<meta http-equiv="refresh" content="0; URL=https://ejemplo.com">`
**Cómo testearlo:** Verificar que el atributo `content` tenga valor numérico `0` seguido de `;URL=` con el destino.

### H77: Propósito de un enlace mediante el ítem de lista que lo contiene
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente)
**Qué hace:** Aclara el destino de un enlace combinando su texto con el contenido del `<li>` que lo envuelve.
**Ejemplo:** `<li>Mirá el video del año pasado del <a href="festival.html">Festival Nacional de Folclore</a>.</li>`
**Cómo testearlo:** Verificar que el enlace esté dentro de un `li` y que el texto del enlace más el del ítem describan su propósito.

### H78: Propósito de un enlace mediante el párrafo que lo contiene
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente)
**Qué hace:** Aclara el destino de un enlace combinando su texto con el párrafo que lo envuelve.
**Ejemplo:** `<p>Artistas reciben premios. <a href="national-heritage.html">Leer más</a></p>`
**Cómo testearlo:** Verificar que el enlace esté dentro de un párrafo y que el texto combinado describa adecuadamente su propósito.

### H79: Propósito de un enlace en tablas de datos
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente)
**Qué hace:** Aclara el destino de un enlace usando su celda de tabla y los encabezados de fila/columna asociados.
**Ejemplo:** En una tabla de precios, `<a href="econ-ala.html">$67</a>` se entiende como "precio Alamo, auto económico" gracias a los encabezados.
**Cómo testearlo:** Verificar que el enlace esté en una celda de tabla y que, junto con sus encabezados asociados, describa su propósito.

### H80: Propósito de un enlace mediante el encabezado precedente
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Advisory)
**Qué hace:** Aclara enlaces ambiguos usando el encabezado que los precede como contexto.
**Ejemplo:** `<h2><a href="royal_palm_hotel.html">Royal Palm Hotel</a></h2>` seguido de enlaces como "Mapa", "Fotos".
**Cómo testearlo:** Ubicar el encabezado previo a cada enlace y verificar que, combinado con el texto del enlace, describa su propósito.

### H81: Propósito de un enlace en una lista anidada
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente)
**Qué hace:** Aclara enlaces de una lista anidada usando el texto del ítem padre bajo el cual está anidada la lista.
**Ejemplo:** `<li>Informe Anual 2021<ul><li><a href="ar-2021.html">HTML</a></li><li><a href="ar-2021.pdf">PDF</a></li></ul></li>`
**Cómo testearlo:** Verificar que la lista anidada sea descendiente de un `li` y que su texto combinado con el del enlace describa el propósito.

### H83: Indicar en el texto del enlace que se abrirá una ventana nueva
**Se relaciona con:** 3.2.5 Cambios a petición del usuario (Suficiente)
**Qué hace:** Usa el atributo `target` para abrir ventanas nuevas, advirtiendo en el propio texto del enlace que esto ocurrirá.
**Ejemplo:** `<a href="help.html" target="_blank">Mostrar ayuda (abre ventana nueva)</a>`
**Cómo testearlo:** Activar el enlace y comprobar que usa `target`, y que su texto indica que abrirá una ventana nueva.

### H84: Usar un botón junto a un select para ejecutar una acción
**Se relaciona con:** 3.2.2 Al recibir el foco / entrada (Suficiente, junto con G80)
**Qué hace:** Evita que cambiar la opción de un `select` dispare una acción automática; el usuario confirma con un botón explícito.
**Ejemplo:** `<select id="quarter">...</select> <button type="button">Mostrar</button>`
**Cómo testearlo:** Verificar que navegar las opciones del `select` no dispare acciones y que la acción solo ocurra al pulsar el botón.

### H85: Uso de optgroup para agrupar opciones de un select
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Agrupa jerárquicamente opciones relacionadas dentro de un `select` mediante `optgroup`, en vez de usar separadores visuales ficticios.
**Ejemplo:** `<select><optgroup label="Frutas"><option>Manzanas</option></optgroup><optgroup label="Verduras"><option>Brócoli</option></optgroup></select>`
**Cómo testearlo:** Identificar grupos de opciones relacionadas y verificar que estén envueltos en `optgroup` con atributo `label` descriptivo.

### H86: Proporcionar alternativas de texto para emojis, emoticones, arte ASCII y leetspeak
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Da alternativas textuales a emojis, emoticones, arte ASCII y leetspeak, cuyos nombres predefinidos suelen no coincidir con la intención comunicativa del autor y confunden a usuarios de lectores de pantalla.
**Ejemplo:** `<span aria-label="rock" role="img">🤘🏾</span>` usa `role="img"` + `aria-label` para dar un nombre accesible personalizado al emoji.
**Cómo testearlo:** Verificar que cada emoji, arte ASCII o leetspeak tenga una alternativa textual equivalente o esté marcado como imagen con alternativa.

### H88: Usar HTML según la especificación
**Se relaciona con:** 4.1.2 Nombre, Rol, Valor (Suficiente, junto con G108)
**Qué hace:** Usar solo elementos, atributos y valores definidos en la especificación HTML, aplicados según lo prescrito, y asegurar que el documento se parsee correctamente, para que navegadores y tecnologías asistivas lo interpreten de forma coherente.
**Ejemplo:** No incluye ejemplo de código específico en la página.
**Cómo testearlo:** Comprobar que la página usa solo elementos/atributos/valores definidos en la especificación, que se usan correctamente, y que el documento parsea sin errores estructurales.

### H89: Usar el atributo title para proporcionar ayuda contextual
**Se relaciona con:** 3.3.5 Ayuda (Advisory/Recomendación, no obligatoria)
**Qué hace:** Agrega ayuda contextual (ej. formato esperado) en el atributo `title` de campos de formulario, aunque advierte que no todos los agentes de usuario exponen ese atributo a tecnologías asistivas.
**Ejemplo:** `<input id="search-address" title="Address example: 101 Collins St, Melbourne, Australia" type="text">`
**Cómo testearlo:** Verificar que los campos tengan etiqueta asociada y que además incluyan ayuda contextual en `title`.

### H90: Indicar controles de formulario requeridos
**Se relaciona con:** 3.3.2 Etiquetas o instrucciones (Suficiente, junto con G131)
**Qué hace:** Indica claramente, dentro del `label` o `legend`, que un control de formulario es obligatorio, incluyendo variantes textuales, con asteriscos o con imágenes (con significado explicado).
**Ejemplo:** `<label for="firstname">First name (required):</label><input id="firstname" type="text">`
**Cómo testearlo:** Confirmar que cada control requerido indique su estado en el `label`/`legend` y que los indicadores no textuales tengan su significado explicado previamente.

### H91: Usar controles de formularios HTML y enlaces
**Se relaciona con:** 2.1.1 Teclado y 4.1.2 Nombre, Rol, Valor (Suficiente, junto con G108)
**Qué hace:** Usa elementos estándar de HTML (inputs, enlaces, etc.) para operación por teclado e interoperabilidad con tecnologías asistivas, ya que el navegador expone automáticamente rol, nombre y valor/estado.
**Ejemplo:** `<label for="text-1">Tipo de fruta</label><input id="text-1" type="text" value="bananas">` — rol "texto editable", nombre por la etiqueta, valor "bananas".
**Cómo testearlo:** Inspeccionar el HTML y verificar, para cada enlace/control de formulario, que nombre, valor y estado estén correctamente especificados.

### H95: Usar el elemento track para proporcionar subtítulos
**Se relaciona con:** 1.2.2 Subtítulos (contenido pregrabado) (Suficiente, junto con G87)
**Qué hace:** Usa `<track kind="captions">` para asociar una pista de subtítulos sincronizados (diálogo, efectos de sonido, música relevante) a un video.
**Ejemplo:** `<track kind="captions" label="English" src="myvideo_en.vtt" srclang="en">` dentro de `<video>`.
**Cómo testearlo:** Verificar que cada video tenga un `track` de tipo `captions` en el idioma del video.

### H96: Usar el elemento track para proporcionar descripciones de audio
**Se relaciona con:** 1.2.1, 1.2.3, 1.2.5 y 1.2.7 (todas Advisory)
**Qué hace:** Usa `<track kind="descriptions">` para proveer texto que se sintetiza en voz, describiendo el contenido visual del video en los espacios disponibles del audio original.
**Ejemplo:** `<track kind="descriptions" label="English" src="myvideo-en.vtt" srclang="en">` dentro de `<video>`.
**Cómo testearlo:** Verificar que cada video tenga un `track` con `kind="descriptions"` en el idioma correspondiente.

### H97: Agrupar enlaces relacionados usando el elemento nav
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente) y 2.4.1 Evitar bloques (Advisory)
**Qué hace:** Agrupa enlaces de navegación relacionados dentro de un `<nav>` para que usuarios de lectores de pantalla puedan localizarlos y saltarlos fácilmente.
**Ejemplo:** `<nav><ul><li><a href="...">Web Accessibility</a></li>...</ul></nav>`; con varios `nav`, diferenciar con `aria-label`/`aria-labelledby`.
**Cómo testearlo:** Verificar que los grupos de enlaces visualmente relacionados estén contenidos en un elemento `nav`.

### H98: Usar atributos HTML autocomplete
**Se relaciona con:** 1.3.5 Identificar el propósito del campo de entrada (Suficiente)
**Qué hace:** Añade el atributo `autocomplete` con un término taxonómico predefinido a los campos de formulario, para que puedan interpretarse y autocompletarse de forma programática.
**Ejemplo:** `<input autocomplete="given-name" id="fname" type="text">`
**Cómo testearlo:** Verificar que cada campo que recopila datos del usuario tenga un `autocomplete` válido y que corresponda con el propósito indicado por su etiqueta.

### H99: Proveer un mecanismo de selección de páginas
**Se relaciona con:** 2.4.5 Múltiples formas (Advisory)
**Qué hace:** Expone programáticamente todas las ubicaciones de saltos de página de una publicación digital, permitiendo localizar referencias estáticas sincronizadas con la versión impresa.
**Ejemplo:** `<nav role="doc-pagelist"><ol><li><a href="intro.xhtml#pg1">1</a></li>...</ol></nav>`
**Cómo testearlo:** Verificar que exista el mecanismo, que incluya todos los saltos de página y que los enlaces apunten correctamente.

### H100: Proveer campos de email y contraseña correctamente marcados
**Se relaciona con:** 3.3.8 y 3.3.9 Autenticación accesible, mínima y mejorada (ambas Suficiente)
**Qué hace:** Marca correctamente los campos de autenticación para permitir autocompletado por el navegador/gestor de contraseñas, sin bloquear el pegado de datos.
**Ejemplo:** `<input autocomplete="email" id="email" type="email">` y `<input autocomplete="current-password" id="password" type="password">`
**Cómo testearlo:** Verificar que cada campo tenga nombre accesible apropiado y permita pegar contenido.

### H101: Usar elementos HTML semánticos para identificar regiones de una página
**Se relaciona con:** 1.3.1 Información y relaciones (Suficiente)
**Qué hace:** Usa elementos como `header`, `nav`, `main`, `section`, `form`, `aside` y `footer` para crear landmarks que permiten navegar programáticamente por las secciones principales de la página.
**Ejemplo:** `<header>...</header><nav>...</nav><main>...</main><aside>...</aside><footer>...</footer>`
**Cómo testearlo:** Verificar que cada landmark marque el contenido correcto y que los landmarks que lo requieren tengan nombre accesible.

### H102: Crear diálogos modales con el elemento HTML dialog
**Se relaciona con:** 2.4.3 Orden del foco (Suficiente, para cambios dinámicos de página)
**Qué hace:** Usa el elemento nativo `<dialog>` en lugar de implementaciones ARIA personalizadas; el navegador gestiona automáticamente el movimiento y confinamiento del foco, la inertización del fondo y la tecla Escape.
**Ejemplo:** `<dialog aria-labelledby="dialog-heading" id="mailing-list-dialog"><h1 id="dialog-heading" tabindex="-1">Sign up</h1>...</dialog>` abierto con `d.showModal()`.
**Cómo testearlo:** Verificar que el diálogo se abra por teclado, que el foco se mueva a él, quede confinado dentro mientras está abierto, y retorne al elemento invocador al cerrarse.
