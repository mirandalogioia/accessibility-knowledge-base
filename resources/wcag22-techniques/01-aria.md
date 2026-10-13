---
title: "WCAG 2.2 Techniques — ARIA"
status: in_progress
last_updated: 2026-10-13
---

# Técnicas ARIA (26)

> Ejemplos de formas de cumplir WCAG 2.2 usando atributos y roles WAI-ARIA. No son obligatorias: el contenido puede cumplir WCAG sin usar exactamente estas técnicas. Fuente: [W3C WAI — Techniques/aria](https://www.w3.org/WAI/WCAG22/Techniques/aria/).

### ARIA1: Usar `aria-describedby` para dar una descripción a controles de interfaz
**Se relaciona con:** 1.3.1 Info y relaciones (Advisory); 3.3.2 Etiquetas o instrucciones (Suficiente, con G131)
**Qué hace:** Asocia un control con texto descriptivo adicional ya presente en el mismo documento, mediante referencias de `id`.
**Ejemplo:**
```html
<label for="fname">First name</label>
<input aria-describedby="int2" id="fname" type="text">
<p id="int2">Your first name is sometimes called your "given name".</p>
```
**Cómo testearlo:** Verificar que el `aria-describedby` apunte a un `id` existente y que ese elemento aporte información adicional sobre el control.

### ARIA2: Identificar un campo obligatorio con `aria-required`
**Se relaciona con:** 1.3.1 Info y relaciones, 3.3.1 Identificación de errores, 3.3.2 Etiquetas o instrucciones (las tres Advisory)
**Qué hace:** Marca programáticamente un campo como obligatorio mediante `aria-required="true"`; debe acompañarse de una indicación visual (asterisco, texto).
**Ejemplo:**
```html
<label for="usrname">Login name *:</label>
<input aria-required="true" id="usrname" type="text">
```
**Cómo testearlo:** Confirmar que el atributo esté presente y que su valor refleje correctamente si el campo es requerido.

### ARIA4: Usar un rol WAI-ARIA para exponer el rol de un componente
**Se relaciona con:** 4.1.2 Nombre, rol, valor (Suficiente, con G10)
**Qué hace:** Asigna un `role` no abstracto de ARIA a un elemento para que la tecnología de asistencia comunique qué es y cómo interactuar con él.
**Ejemplo:**
```html
<div role="toolbar" tabindex="0">
  <img src="btn1.gif" role="button" alt="Home">
</div>
```
**Cómo testearlo:** Verificar que el `role` sea un valor válido no abstracto de ARIA y que describa correctamente las características del componente.

### ARIA5: Usar atributos de estado y propiedad de WAI-ARIA para exponer el estado de un componente
**Se relaciona con:** 4.1.2 Nombre, rol, valor (Suficiente, con G10)
**Qué hace:** Expone estado, propiedades y valores de widgets personalizados (toggles, sliders, etc.) para que la tecnología de asistencia los lea y detecte cambios.
**Ejemplo:**
```html
<a role="button" aria-pressed="false" tabindex="0">Mute</a>
<div role="slider" aria-valuemin="0" aria-valuenow="128" aria-valuemax="255"></div>
```
**Cómo testearlo:** Verificar que estén los estados/propiedades requeridos por el rol, sin atributos no soportados, y que los valores se actualicen al cambiar el componente.

### ARIA6: Usar `aria-label` para etiquetar objetos
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Da una etiqueta de texto a un objeto para que la tecnología de asistencia comunique su propósito; puede ser anulado por `aria-labelledby`.
**Ejemplo:**
```html
<div role="navigation" aria-label="Primary">...</div>
<div role="navigation" aria-label="Secondary">...</div>
```
**Cómo testearlo:** Verificar que el texto del `aria-label` describa adecuadamente el propósito del objeto.

### ARIA7: Usar `aria-labelledby` para el propósito de un enlace
**Se relaciona con:** 2.4.4 Propósito del enlace (en contexto) (Suficiente)
**Qué hace:** Concatena texto visible de la página (por orden de IDs) para formar el nombre accesible de un enlace, aclarando su propósito a usuarios de lector de pantalla.
**Ejemplo:**
```html
<h2 id="headline">Storms hit east coast</h2>
<a id="p123" href="news.html" aria-labelledby="p123 headline">Read more...</a>
```
**Cómo testearlo:** Confirmar que los IDs referenciados existen y que el texto combinado describe apropiadamente el propósito del enlace.

### ARIA8: Usar `aria-label` para el propósito de un enlace
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Suficiente); 2.4.9 Propósito del enlace (solo enlace) (Suficiente)
**Qué hace:** Reemplaza con un `aria-label` descriptivo el texto genérico de un enlace (ej. "leer más") cuando no hay texto visible suficiente.
**Ejemplo:**
```html
<a href="taxhike.html" aria-label="Read more about Seminole tax hike">Read more</a>
```
**Cómo testearlo:** Verificar que el valor de `aria-label` describa adecuadamente el propósito del enlace.

### ARIA9: Usar `aria-labelledby` para concatenar una etiqueta de varios nodos de texto
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente); 3.3.2 Etiquetas o instrucciones (Suficiente, con G131)
**Qué hace:** Combina varios IDs (en orden) en `aria-labelledby` para armar una etiqueta accesible única a partir de texto disperso en la página.
**Ejemplo:**
```html
<span id="timeout-label"><label for="timeout-duration">Extend time-out to</label></span>
<input id="timeout-duration" value="20" aria-labelledby="timeout-label timeout-duration timeout-unit">
<span id="timeout-unit"> minutes</span>
```
**Cómo testearlo:** Verificar que los IDs sean únicos y existentes, y que el texto concatenado describa bien el propósito del elemento.

### ARIA10: Usar `aria-labelledby` para dar una alternativa textual a contenido no textual
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Asocia contenido no textual (ej. un gráfico armado con imágenes) con texto visible que funciona como su alternativa textual.
**Ejemplo:**
```html
<div role="img" aria-labelledby="star-id">
  <img src="fullstar.png" alt="">...
</div>
<div id="star-id">4 of 5</div>
```
**Cómo testearlo:** Confirmar que el `id` referenciado existe y que su texto describe adecuadamente el contenido no textual.

### ARIA11: Usar landmarks ARIA para identificar regiones de la página
**Se relaciona con:** 1.3.1 Info y relaciones, 1.3.6 Identificar el propósito, 2.4.1 Evitar bloques (los tres Suficiente)
**Qué hace:** Marca secciones de la página (banner, navigation, main, complementary, contentinfo) para que la tecnología de asistencia permita orientarse y saltar bloques repetidos.
**Ejemplo:**
```html
<div role="banner">logo...</div>
<div role="navigation">menú...</div>
<div role="main">contenido principal...</div>
```
**Cómo testearlo:** Verificar que cada landmark use el rol correcto y, si hay varios del mismo tipo, que cada uno tenga nombre accesible único.

### ARIA12: Usar `role="heading"` para identificar encabezados
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente)
**Qué hace:** Marca un elemento como encabezado con nivel jerárquico mediante `role="heading"` y `aria-level`, cuando no se usan las etiquetas h1-h6 nativas.
**Ejemplo:**
```html
<div role="heading" aria-level="2">Global News Items</div>
<div role="heading" aria-level="3">Politics</div>
```
**Cómo testearlo:** Verificar que el contenido sea apropiado como encabezado y que `aria-level` refleje el nivel jerárquico correcto.

### ARIA13: Usar `aria-labelledby` para nombrar regiones y landmarks
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente)
**Qué hace:** Vincula una región o landmark con un encabezado u otro texto ya presente en la página para darle un nombre accesible.
**Ejemplo:**
```html
<div role="complementary" aria-labelledby="hdr1">
  <h1 id="hdr1">Top News Stories</h1>
  ...
</div>
```
**Cómo testearlo:** Confirmar que el `id` referenciado existe y que su texto etiqueta adecuadamente la región.

### ARIA14: Usar `aria-label` para dar nombre accesible cuando no puede usarse una etiqueta visible
**Se relaciona con:** 4.1.2 Nombre, rol, valor (Suficiente)
**Qué hace:** Proporciona un nombre accesible a controles personalizados (sin `<label>` nativo posible) mediante `aria-label`.
**Ejemplo:**
```html
<dialog id="dialog">
  This is the content of the dialog.
  <button aria-label="Close">×</button>
</dialog>
```
**Cómo testearlo:** Verificar que el valor de `aria-label` describa adecuadamente el propósito del elemento.

### ARIA15: Usar `aria-describedby` para proporcionar descripciones de imágenes
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Vincula una imagen con una descripción extendida presente en la página cuando el `alt` breve no alcanza.
**Ejemplo:**
```html
<img src="ladymacbeth.jpg" alt="Lady MacBeth" aria-describedby="p1">
<p id="p1">This painting dates back to 1889 and is oil on canvas...</p>
```
**Cómo testearlo:** Verificar que el `id` referenciado existe y que el texto combinado (alt + descripción) equivale al propósito de la imagen.

### ARIA16: Uso de `aria-labelledby` para proporcionar un nombre a controles de interfaz de usuario
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente), 4.1.2 Nombre, rol, valor (Suficiente)
**Qué hace:** Usa `aria-labelledby` para asociar un control con texto descriptivo visible en la página, útil cuando el contexto visual le da nombre al control pero no hay `<label>` explícito.
**Ejemplo:**
```html
<input name="searchtxt" type="text" aria-labelledby="searchbtn">
<input name="searchbtn" id="searchbtn" type="submit" value="Search">
```
**Cómo testearlo:** Verificar que `aria-labelledby` referencia un ID válido y que el texto referenciado describe con precisión el control.

### ARIA17: Uso de roles de agrupación para identificar controles de formulario relacionados
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente), 3.3.2 Etiquetas o instrucciones (Suficiente, combinada con G131)
**Qué hace:** Agrupa controles de formulario relacionados (p. ej. partes de un mismo dato) usando `role="group"` o `role="radiogroup"` con un nombre accesible mediante `aria-labelledby`.
**Ejemplo:**
```html
<div role="group" aria-labelledby="ssn1">
  <span id="ssn1">Social Security Number</span>
  <input size="3" title="First 3 digits">-<input size="2" title="Next 2 digits">-<input size="4" title="Last 4 digits">
</div>
```
**Cómo testearlo:** Confirmar que los controles están dentro de un elemento con `role=group`/`radiogroup` y que el grupo tiene nombre accesible.

### ARIA18: Uso de `aria-alertdialog` para identificar errores
**Se relaciona con:** 3.3.1 Identificación de errores (Suficiente), 3.3.3 Sugerencia ante errores (Suficiente), 4.1.3 Mensajes de estado (Advisory)
**Qué hace:** Crea un diálogo modal con `role="alertdialog"` para notificar errores de entrada; debe tener nombre accesible, contener elemento enfocable, atrapar el foco y devolverlo al cerrar.
**Ejemplo:**
```html
<dialog role="alertdialog" aria-labelledby="alert-heading" id="date-alert">
  <h1 id="alert-heading">Error</h1>
  <p>La fecha de nacimiento es posterior a la de contratación...</p>
  <button commandfor="date-alert" command="close">Corregir</button>
</dialog>
```
**Cómo testearlo:** Disparar el error y verificar nombre accesible, gestión del foco y que se identifique (y sugiera corrección) el error.

### ARIA19: Uso de `role=alert` o live regions para identificar errores
**Se relaciona con:** 3.3.1 Identificación de errores (Suficiente), 4.1.3 Mensajes de estado (Suficiente, con técnica más específica)
**Qué hace:** Usa `role="alert"` o `aria-live` para que el lector de pantalla anuncie errores automáticamente sin que el usuario deba enfocar la zona del mensaje.
**Ejemplo:** Contenedor vacío `role="alert"` presente desde el inicio; al validar, se inyecta el mensaje de error dentro de ese mismo contenedor.
**Cómo testearlo:** Verificar que el contenedor con `role="alert"`/`aria-live` exista vacío al cargar y que el mensaje de error se inserte dentro de él al activarse.

### ARIA20: Uso del rol `region` para identificar una región de la página
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente)
**Qué hace:** Asigna `role="region"` a secciones significativas que no corresponden a un landmark estándar, para que las tecnologías asistivas las identifiquen como áreas independientes.
**Ejemplo:**
```html
<div role="region" aria-labelledby="pollhead">
  <h3 id="pollhead">Encuesta de la semana</h3>
  ...
</div>
```
**Cómo testearlo:** Confirmar que el contenido amerita ser una región propia, que no hay un rol landmark más apropiado, y que tiene nombre accesible.

### ARIA21: Uso de `aria-invalid` para indicar un campo con error
**Se relaciona con:** 3.3.1 Identificación de errores (Suficiente)
**Qué hace:** Marca campos que fallaron la validación con `aria-invalid="true"`, permitiendo validaciones personalizadas más allá de tipos HTML nativos; no debe estar en "true" antes de validar.
**Ejemplo:**
```html
<input aria-invalid="false" id="first" name="first" type="text">
// si field.value.trim() === '' → field.setAttribute('aria-invalid','true')
```
**Cómo testearlo:** Verificar que `aria-invalid` no sea "true" sin error, que pase a "true" al fallar la validación, y que haya texto asociado explicando el error.

### ARIA22: Uso de `role=status` para presentar mensajes de estado
**Se relaciona con:** 4.1.3 Mensajes de estado (Suficiente, sola o junto con G193)
**Qué hace:** Usa `role="status"` (con `aria-live="polite"` y `aria-atomic="true"` implícitos) para que lectores de pantalla anuncien actualizaciones de estado sin requerir foco del usuario.
**Ejemplo:**
```html
<div role="status" aria-atomic="true">5 resultados encontrados.</div>
```
**Cómo testearlo:** Confirmar que el contenedor tiene `role="status"` antes del mensaje, que el mensaje aparece dentro de él, y que el contexto (p. ej. texto alt) también está incluido.

### ARIA23: Uso de `role=log` para identificar actualizaciones secuenciales de información
**Se relaciona con:** 4.1.3 Mensajes de estado (Suficiente)
**Qué hace:** Usa `role="log"` (implícitamente `aria-live="polite"` y `aria-atomic="false"`) en regiones con información secuencial (como un chat) para anunciar automáticamente nuevos mensajes.
**Ejemplo:**
```html
<div role="log" aria-labelledby="chatHeading" id="chatRegion">
  <h4 id="chatHeading">Historial de chat</h4>
  <ul id="conversation"><li>Último mensaje</li></ul>
</div>
```
**Cómo testearlo:** Verificar que el contenedor de la información secuencial tenga `role="log"`.

### ARIA24: Identificación semántica de un icono de fuente con `role=img`
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente)
**Qué hace:** Marca iconos de fuente con `role="img"` para que, si un usuario reemplaza fuentes por CSS personalizado, los selectores puedan excluir estos iconos y mantenerlos visibles.
**Ejemplo:**
```html
<span class="icon icon-star-bg" role="img" aria-label="Favorito"></span>
/* CSS de usuario */ *:not([role="img"]) { font-family: Verdana, sans-serif !important; }
```
**Cómo testearlo:** Confirmar que cada icono de fuente tenga `role="img"`.

### ARIA25: Uso de una región activa ARIA para comunicar el estado de una barra de progreso
**Se relaciona con:** 4.1.3 Mensajes de estado (Suficiente)
**Qué hace:** Combina `role="progressbar"` (con `aria-valuemin/max/now`) con un contenedor `aria-live="polite"` oculto visualmente que anuncia el avance sin mover el foco.
**Ejemplo:** Carga de documento: barra de progreso + `<div aria-live="polite">0% completo</div>` que se actualiza dinámicamente.
**Cómo testearlo:** Con lector de pantalla, confirmar que los cambios de progreso se anuncian automáticamente sin desplazar el foco.

### ARIA26: Uso de `aria-current` para identificar el elemento actual en un conjunto
**Se relaciona con:** 1.3.1 Info y relaciones (Suficiente), 2.4.8 Ubicación (Suficiente)
**Qué hace:** Indica programáticamente cuál ítem de un conjunto (página, paso, etc.) está activo/actual, cuando visualmente solo se distingue por estilo.
**Ejemplo:**
```html
<nav><ul>
  <li><a href="/">Home</a></li>
  <li><a href="/food" aria-current="page">Food</a></li>
</ul></nav>
```
**Cómo testearlo:** Verificar que todo elemento resaltado visualmente como "actual" tenga `aria-current` con el valor apropiado (page, step, time, etc.).

### ARIA27: Uso de `ariaNotify` para comunicar el estado de una barra de progreso
**Se relaciona con:** 4.1.3 Mensajes de estado (Suficiente)
**Qué hace:** Usa el método experimental `document.ariaNotify()` para anunciar el estado de una barra de progreso a tecnologías asistivas; se recomienda como mejora progresiva junto a ARIA25, no en solitario.
**Ejemplo:**
```html
<div role="progressbar" aria-valuemin="0" aria-valuemax="100" aria-valuenow="0" id="upload-progress"></div>
<script>document.ariaNotify("50% completado");</script>
```
**Cómo testearlo:** Confirmar que la barra cambia dinámicamente y que, con lector de pantalla, se anuncian las actualizaciones sin mover el foco.
