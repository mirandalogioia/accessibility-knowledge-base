---
title: "WCAG 2.2 Techniques — CSS"
status: in_progress
last_updated: 2026-10-13
---

# Técnicas CSS (36)

> Ejemplos de formas de cumplir WCAG 2.2 usando CSS. No son obligatorias: el contenido puede cumplir WCAG sin usar exactamente estas técnicas. Fuente: [W3C WAI — Techniques/css](https://www.w3.org/WAI/WCAG22/Techniques/css/).

### C6: Posicionamiento de contenido basado en marcado estructural
**Se relaciona con:** 1.3.2 Secuencia significativa (Suficiente, con G57); 1.4.5 y 1.4.9 Imágenes de texto (Asesoría); 2.4.1 Evitar bloques (Asesoría)
**Qué hace:** Usa posicionamiento CSS para ubicar visualmente el contenido en cualquier parte del viewport, conservando un orden significativo cuando los estilos no están disponibles.
**Ejemplo:** Listas de definición (`<dl><dt><dd>`) posicionadas en columnas con CSS, que siguen siendo legibles como lista sin estilos.
**Cómo testearlo:** Desactivar las hojas de estilo y verificar que las relaciones estructurales y el significado del contenido se mantengan.

### C7: Usar CSS para ocultar parte del texto del enlace
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto y 2.4.9 Propósito del enlace (solo enlace) (ambos Suficiente)
**Qué hace:** Añade texto adicional dentro del enlace, oculto visualmente con CSS (caja de 1px, `overflow:hidden`), que describe su función solo para tecnología de asistencia.
**Ejemplo:** `<a href="...">`<span class="visually-hidden">Washington stimulates economic growth</span> Full Story`</a>` con `.visually-hidden {clip-path:inset(100%); height:1px; width:1px; overflow:hidden; position:absolute;}`
**Cómo testearlo:** Confirmar que existe un elemento confinado a 1px dentro del enlace y que el texto combinado describe claramente su propósito.

### C8: Uso de letter-spacing para controlar el espaciado dentro de una palabra
**Se relaciona con:** 1.3.2 Secuencia significativa (Suficiente con G57); 1.4.5, 1.4.9 y 1.4.12 Espaciado de texto (Asesoría)
**Qué hace:** Usa la propiedad CSS `letter-spacing` para separar visualmente letras dentro de una palabra, en vez de insertar espacios en blanco que alterarían el significado o la pronunciación.
**Ejemplo:** `h2 {letter-spacing: 1em}` aplicado a `<h2>Museum</h2>` produce "M u s e u m" visualmente sin tocar el texto real.
**Cómo testearlo:** Verificar que el espaciado entre caracteres se logra con la propiedad CSS `letter-spacing` y no con caracteres en blanco adicionales.

### C9: Uso de CSS para incluir imágenes decorativas
**Se relaciona con:** 1.1.1 Contenido no textual (Suficiente)
**Qué hace:** Incorpora imágenes puramente decorativas o de formato mediante CSS (`background`, `content` en `::before`/`::after`, `list-style-image`) en lugar de marcado HTML, para que la tecnología de asistencia las ignore.
**Ejemplo:** `body {background: #ffe url('/images/home-bg.jpg') repeat;}`
**Cómo testearlo:** Confirmar que las imágenes decorativas presentes están implementadas vía CSS y no en el HTML.

### C12: Uso de porcentajes para tamaños de fuente
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto (Suficiente); 1.4.8 Presentación visual (Suficiente con G146); 1.4.5 y 1.4.9 Imágenes de texto (Asesoría)
**Qué hace:** Define tamaños de fuente en porcentajes relativos al contexto, para que los agentes de usuario puedan escalar el texto correctamente.
**Ejemplo:** `strong {font-size: 120%}` hace que el texto en negrita sea siempre 120% del tamaño circundante.
**Cómo testearlo:** Verificar que el valor de `font-size` esté expresado en porcentaje.

### C13: Uso de tamaños de fuente con nombre
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto (Suficiente); 1.4.8 Presentación visual (Suficiente con G146); 1.4.5 y 1.4.9 Imágenes de texto (Asesoría)
**Qué hace:** Especifica el tamaño de fuente con valores nombrados (`larger`, `small`, etc.) que expresan tamaño relativo, permitiendo adaptación según el contexto heredado.
**Ejemplo:** `strong {font-size: larger}` en `<h1>...<strong>user</strong>...</h1>` asegura que el texto resaltado sea siempre mayor que el circundante.
**Cómo testearlo:** Comprobar que `font-size` use uno de los valores: xx-small, x-small, small, medium, large, x-large, xx-large, smaller o larger.

### C14: Uso de unidades em para tamaños de fuente
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto (Suficiente); 1.4.8 Presentación visual (Suficiente con G146); 1.4.5 y 1.4.9 Imágenes de texto (Asesoría)
**Qué hace:** Define tamaños de fuente con unidades `em`, que escalan proporcionalmente al tamaño de fuente del contexto, permitiendo un escalado efectivo del contenido.
**Ejemplo:** `strong {font-size: 1.6em}` hace que el texto resaltado sea siempre 1.6 veces mayor que su entorno.
**Cómo testearlo:** Verificar que el valor de `font-size` esté expresado en unidades `em`.

### C15: Uso de CSS para cambiar la presentación de un componente al recibir foco
**Se relaciona con:** 2.4.7 Foco visible (Suficiente); 1.4.1 Uso del color (Asesoría)
**Qué hace:** Da retroalimentación visual (color, fondo, contorno) cuando un elemento interactivo recibe foco o se pasa el mouse, señalando que es interactivo.
**Ejemplo:** `#main-nav a:hover, #main-nav a:active, #main-nav a:focus-visible {background-color:#DCFFFF; color:#000066;}`
**Cómo testearlo:** Navegar con Tab por los elementos enfocables y confirmar que el indicador visual aparece con el foco y desaparece al perderlo.

### C17: Escalado de elementos de formulario que contienen texto
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto (Asesoría)
**Qué hace:** Asegura que los controles de formulario (inputs, textareas, botones) escalen su tamaño de texto junto con el resto de la página, usando `font: inherit`.
**Ejemplo:** `input {font: inherit;} h1{font-size:2em;} p, label {font-size:1em;}`
**Cómo testearlo:** Ingresar texto en un control, aumentar el tamaño de texto del navegador al 200% y verificar que el texto del campo también crece proporcionalmente.

### C18: Uso de márgenes y relleno CSS en lugar de imágenes espaciadoras
**Se relaciona con:** 1.1.1 Contenido no textual (Asesoría)
**Qué hace:** Reemplaza imágenes espaciadoras (GIFs transparentes) por propiedades CSS de `margin` y `padding` para controlar el espaciado del layout.
**Ejemplo:** `table {margin:.5em;} td, th {padding:.4em; border:1px solid #000;}`
**Cómo testearlo:** Verificar que el espaciado visual se logra solo con CSS, sin imágenes espaciadoras en el HTML.

### C19: Especificación de alineación a la izquierda o derecha en CSS
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente)
**Qué hace:** Alinea bloques de texto a la izquierda o derecha mediante la propiedad `text-align`, evitando la justificación completa que dificulta la lectura.
**Ejemplo:** `p.left {text-align: left}` o `p.right {text-align: right}` aplicado a un párrafo.
**Cómo testearlo:** Verificar que el texto esté alineado a la izquierda o a la derecha (no justificado).

### C20: Uso de medidas relativas para el ancho de columnas (máx. 80 caracteres)
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente); 1.4.4 Cambio de tamaño del texto (Asesoría)
**Qué hace:** Define el ancho de columnas con unidades relativas (em, %) para que, al redimensionar el navegador, las líneas de texto no superen aproximadamente 80 caracteres.
**Ejemplo:** `#main-content {max-width: 70em}` o `#main-content {width: 90%}`
**Cómo testearlo:** Confirmar que el ancho de columna usa unidades relativas y que, al redimensionar la ventana, las líneas mantienen 80 caracteres o menos.

### C21: Especificación del espaciado de líneas en CSS
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente); 1.4.12 Espaciado del texto (Asesora)
**Qué hace:** Define la altura de línea mediante CSS para que las personas con discapacidades cognitivas puedan seguir el texto más fácilmente, ya que un espaciado de 1.5 a 2 ayuda a ubicar la línea siguiente.
**Ejemplo:** `body { line-height: 1.5; }`
**Cómo testearlo:** Verificar que el espaciado entre líneas de los bloques de texto esté entre 1.5 y 2.

### C22: Uso de CSS para controlar la presentación visual del texto
**Se relaciona con:** 1.3.1 Información y relaciones (Asesora); 1.4.4 Cambio de tamaño del texto (Asesora); 1.4.5 y 1.4.9 Imágenes de texto (Suficiente)
**Qué hace:** Usa CSS para gestionar tamaño, color, fuente y posición del texto en lugar de imágenes, separando estilo de contenido para que el usuario pueda personalizar la presentación desde el navegador.
**Ejemplo:** `code { font-family:"Courier New", Courier, monospace }`
**Cómo testearlo:** Comprobar que las propiedades CSS controlan efectivamente la presentación visual del texto.

### C23: Especificar colores de texto y fondo solo en contenido secundario
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente)
**Qué hace:** Aplica colores CSS únicamente a elementos secundarios (navegación, banners) dejando el contenido principal sin colores especificados, para que el usuario pueda personalizar sus colores preferidos sin perder las pistas visuales de organización.
**Ejemplo:** Una página con colores definidos en la barra de navegación y tabla de contenidos, pero no en el contenido principal, que respeta la configuración de color del navegador del usuario.
**Cómo testearlo:** Cambiar los colores de texto/fondo en el navegador y confirmar que el contenido principal los adopta mientras el contenido secundario conserva sus colores originales.

### C24: Uso de valores porcentuales en CSS para tamaños de contenedores
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente, junto con G146)
**Qué hace:** Define el ancho de los contenedores en porcentajes en lugar de unidades fijas, para que el contenido se reajuste al aumentar el tamaño del texto sin generar desplazamiento horizontal.
**Ejemplo:** Un periódico online cuyo contenedor de contenido usa ancho en porcentaje, de modo que al aumentar el tamaño de fuente el texto se reacomoda sin scroll horizontal.
**Cómo testearlo:** Verificar que los anchos usen porcentajes, aumentar el texto al 200% y confirmar que no se requiere desplazamiento horizontal.

### C25: Especificar bordes y maquetación sin especificar colores de texto/fondo
**Se relaciona con:** 1.4.8 Presentación visual (Suficiente)
**Qué hace:** Usa CSS para definir bordes y estructura de la página, pero evita fijar colores de texto y fondo, permitiendo que el usuario aplique sus propios colores sin romper el diseño.
**Ejemplo:** Un sitio con menú flotante a la izquierda definido por bordes y layout en CSS, sin colores especificados, donde el usuario puede aplicar su propia paleta desde el navegador.
**Cómo testearlo:** Cambiar la configuración de colores de texto/fondo/enlaces en el navegador y verificar que se apliquen conservando bordes y maquetación intactos.

### C27: Hacer coincidir el orden del DOM con el orden visual
**Se relaciona con:** 1.3.2 Secuencia significativa (Suficiente); 2.4.3 Orden del foco (Suficiente)
**Qué hace:** Asegura que el orden del contenido en el código fuente coincida con el orden visual que produce CSS, evitando que usuarios de lectores de pantalla y usuarios videntes perciban secuencias distintas.
**Ejemplo:** Un periódico online donde la barra de navegación se ve arriba a la izquierda, debajo del logo, pero en el código aparece después del logo, generando desalineación.
**Cómo testearlo:** Comparar el orden visual de la página con el orden del DOM inspeccionado con herramientas de desarrollador; deben coincidir (arriba a abajo, izquierda a derecha).

### C28: Especificar el tamaño de contenedores de texto usando unidades em
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto (Suficiente, combinada); 1.4.12 Espaciado del texto (Asesora)
**Qué hace:** Define el ancho/alto de los contenedores de texto en unidades `em` para que se adapten proporcionalmente al aumentar el tamaño de fuente, evitando recortes o desbordes.
**Ejemplo:** `#nav_menu { width: 20em; height: 100em; } #nav_list { font-size: 100%; }`
**Cómo testearlo:** Identificar contenedores de texto y comprobar que su ancho y/o alto estén expresados en `em`.

### C29: Usar un conmutador de estilos para ofrecer una versión alternativa conforme
**Se relaciona con:** No referenciada desde un documento "Understanding" específico; se usa para ofrecer versiones alternativas conformes.
**Qué hace:** Combina CSS con scripting para dar controles en la página que permitan al usuario ajustar la presentación visual (p. ej. colores) cuando no puede modificar la configuración del navegador o sistema.
**Ejemplo:** `function changeColors(newCSS){ document.getElementById('currentCSS').href = newCSS; }` — el usuario elige entre opciones como "azul oscuro sobre blanco" o "amarillo sobre negro".
**Cómo testearlo:** Verificar que existan controles para elegir presentaciones alternas, que modifiquen el CSS activo, y que la versión resultante sea conforme.

### C30: Reemplazar texto con imágenes de texto mediante CSS, con control para alternar
**Se relaciona con:** 1.4.5 y 1.4.9 Imágenes de texto (Suficiente)
**Qué hace:** Usa hojas de estilo alternativas para mostrar texto normal o reemplazarlo visualmente por imágenes de texto, ofreciendo un control de interfaz para cambiar entre ambas presentaciones.
**Ejemplo:** `<h1><span>Pufferfish Design Studio</span></h1>` con CSS que pone `background-image` en el `h1` y oculta el `span` fuera de pantalla (`left: -999em`) para lectores de pantalla.
**Cómo testearlo:** Verificar que exista un control para alternar presentaciones y que, al activarlo, el texto programático reemplace a las imágenes de texto.

### C31: Usar CSS Flexbox para el reflujo del contenido
**Se relaciona con:** 1.4.10 Reflow (Suficiente)
**Qué hace:** Emplea diseños flexibles (flexbox) que reorganizan los elementos según el espacio disponible, manteniendo orden y relación de lectura, sin requerir scroll horizontal a 320px CSS ni vertical a 256px CSS.
**Ejemplo:** Layout con `flex`, `flex-flow: row wrap` y `flex-basis`, combinado con media queries, que pasa de columnas en fila a apilamiento vertical según el ancho de pantalla.
**Cómo testearlo:** Configurar viewport en 1280×1024px, aplicar zoom al 400% y verificar que no se necesite desplazamiento horizontal ni vertical.

### C32: Usar media queries y grid CSS para el reflujo de columnas
**Se relaciona con:** 1.4.10 Reflow (Suficiente)
**Qué hace:** Utiliza `grid` y media queries para reorganizar columnas (header, main, aside, footer) según el ancho del viewport, manteniendo el orden de lectura sin generar scroll horizontal a 320px CSS.
**Ejemplo:** Grid con áreas definidas, unidades `fr` y puntos de ruptura en 576px y 992px que adaptan el diseño responsivo.
**Cómo testearlo:** Configurar viewport en 1280×1024px, aplicar zoom al 400% y comprobar que todo el contenido sea accesible sin scroll horizontal ni vertical.

### C33: Permitir el reflujo con URLs largas y cadenas de texto
**Se relaciona con:** 1.4.10 Reflow (Suficiente)
**Qué hace:** Evita que URLs extensas o cadenas sin espacios rompan el reflujo al hacer zoom, permitiendo que el texto se divida y ajuste al ancho disponible en lugar de generar scroll horizontal a 320px CSS.
**Ejemplo:** `a { overflow-wrap: break-word; word-wrap: break-word; }`
**Cómo testearlo:** Configurar viewport en 1280×1024px, aplicar zoom al 400% y verificar que no se requiera desplazamiento horizontal ni vertical.

### C34: Usar media queries para desactivar encabezados/pies adhesivos
**Se relaciona con:** 1.4.11 Reflow (Advisory)
**Qué hace:** Muestra encabezados y pies fijos (sticky) solo cuando hay espacio suficiente, desactivándolos con media queries (`min-height`, `max-height`, `min-width`) para no bloquear contenido en móviles u orientación horizontal.
**Ejemplo:** `@media (min-device-width: 576px) and (orientation: landscape) { header { position: static; } }`
**Cómo testearlo:** Cambiar orientación/tamaño de viewport o hacer zoom y verificar que los elementos fijos se desactiven según los puntos de ruptura definidos.

### C35: Permitir espaciado de texto sin truncar contenido
**Se relaciona con:** 1.4.12 Espaciado de texto (Suficiente)
**Qué hace:** Permite que el usuario aumente el espaciado entre párrafos, líneas, palabras y caracteres sin que el contenido se pierda o trunque; contenedores fijos deben ser ~20% más anchos de lo necesario, o usar `inline-block` sin márgenes negativos.
**Ejemplo:** `nav li { width: 10em; }` para dar margen extra a los enlaces de un menú.
**Cómo testearlo:** Aplicar al 100% de zoom las métricas de espaciado de texto (p. ej. con un bookmarklet) y verificar que no haya pérdida de contenido ni funcionalidad.

### C36: Permitir la anulación del espaciado de texto
**Se relaciona con:** 1.4.12 Espaciado de texto (Suficiente)
**Qué hace:** Similar a C35: evita fijar alturas en contenedores de texto para que puedan expandirse libremente cuando el usuario aplica hojas de estilo, extensiones o apps con mayor espaciado.
**Ejemplo:** Una tarjeta (`.card`) con título y párrafo sin `height` definido, que se expande verticalmente sin solaparse.
**Cómo testearlo:** Con zoom al 100%, aplicar métricas de espaciado de texto y confirmar que todo el contenido siga visible y funcional, sin truncamiento.

### C37: Usar max-width y height para ajustar imágenes
**Se relaciona con:** 1.4.10 Reflow (Advisory)
**Qué hace:** Adapta imágenes al espacio disponible manteniendo proporciones, evitando scroll horizontal a 320px CSS o vertical a 256px CSS en diseños responsivos.
**Ejemplo:** `.img-responsive { max-width: 100%; }` aplicado a una imagen dentro de un panel.
**Cómo testearlo:** Configurar viewport a 1280×1024px, aplicar zoom 400% y verificar que las imágenes no generen scroll en ninguna dirección.

### C38: Usar width, max-width y flexbox para ajustar etiquetas e inputs
**Se relaciona con:** 1.4.10 Reflow (Suficiente)
**Qué hace:** Hace que etiquetas e inputs de formularios cambien de alineación horizontal a vertical según el espacio disponible, usando `width`, `max-width` y flexbox, evitando scroll horizontal a 320px CSS.
**Ejemplo:** `input, label, select { width: 100%; max-width: 100%; }` dentro de un `.form-group` con `display: flex; flex-flow: row wrap;`.
**Cómo testearlo:** Mostrar la página con zoom al 400% en viewport de 1280×1024px y verificar que etiquetas/inputs se adapten sin requerir scroll horizontal.

### C39: Usar la media query prefers-reduced-motion para evitar movimiento
**Se relaciona con:** 2.3.3 Animación por interacciones (Suficiente)
**Qué hace:** Permite desactivar animaciones de movimiento no esenciales cuando el usuario activó la preferencia del sistema de reducir movimiento, evitando distracción o náuseas (trastornos vestibulares).
**Ejemplo:** `@media (prefers-reduced-motion: reduce) { /* estilos sin movimiento */ }`
**Cómo testearlo:** Activar "movimiento reducido" en el sistema y verificar, para cada animación disparada por interacción, que sea esencial o que esté suprimida.

### C40: Crear un indicador de foco de dos colores
**Se relaciona con:** 1.4.11 Contraste no textual, 2.4.7 Foco visible, 2.4.13 Apariencia del foco (Suficiente)
**Qué hace:** Combina dos colores con alto contraste entre sí (≥9:1) en el indicador de foco, garantizando que al menos uno tenga 3:1 de contraste contra cualquier fondo sólido.
**Ejemplo:** `*:focus { outline: 2px #F9F9F9 solid; box-shadow: 0 0 0 4px #193146; }`
**Cómo testearlo:** Verificar contraste 9:1 entre ambos colores, que cada banda mida al menos 2px CSS, y que el indicador se vea sobre un fondo sólido.

### C41: Crear un indicador de foco fuerte dentro del componente
**Se relaciona con:** 2.4.13 Apariencia del foco (Suficiente)
**Qué hace:** Da alto contraste al indicador de foco respecto al fondo interno del propio componente, para que sea visible sin depender del fondo externo.
**Ejemplo:** `main button:focus { outline: 3px #ffff00 solid; outline-offset: -4px; }` en un botón azul oscuro.
**Cómo testearlo:** Enfocar con teclado cada elemento interactivo y verificar que el indicador mida al menos 2px CSS y tenga contraste mínimo 3:1 entre estado enfocado y no enfocado.

### C42: Usar min-height y min-width para espaciar objetivos
**Se relaciona con:** 2.5.8 Tamaño del objetivo (Mínimo) (Suficiente)
**Qué hace:** Da espaciado suficiente entre enlaces pequeños (menús, paginación) usando contenedores de al menos 24×24px CSS, evitando activaciones accidentales sin agrandar el texto visualmente.
**Ejemplo:** `li { margin: 3px; min-height: 24px; min-width: 24px; text-align: center; }`
**Cómo testearlo:** Dibujar un círculo de 24px de diámetro centrado en cada objetivo pequeño y verificar que no se solape con otros objetivos.

### C43: Usar CSS scroll-padding para revelar contenido oculto
**Se relaciona con:** 2.4.11 Foco no oscurecido (Mínimo) y 2.4.12 Foco no oscurecido (Mejorado) (Suficiente)
**Qué hace:** Agrega espacio de relleno con `scroll-padding` para que componentes tapados por elementos fijos (banners de cookies, etc.) se vuelvan visibles al recibir foco de teclado.
**Ejemplo:** `html { padding-bottom: var(--height-dialog); scroll-padding-bottom: var(--scroll-padding); }`, actualizado dinámicamente según la altura del banner.
**Cómo testearlo:** Verificar que el componente enfocado no quede completamente oculto (mínimo), o que ninguna parte quede oculta (mejorado/AAA).

### C44: Usar CSS para garantizar objetivos de al menos 44×44 px
**Se relaciona con:** 2.5.5 Tamaño del objetivo (Mejorado) (Suficiente)
**Qué hace:** Asegura que elementos interactivos, especialmente en paginación, midan al menos 44×44 píxeles CSS para prevenir activaciones accidentales de objetivos adyacentes.
**Ejemplo:** `.pagination-list a { min-block-size: 44px; min-inline-size: 44px; padding: 0.5em; }`
**Cómo testearlo:** Para cada objetivo interactivo aplicable, verificar que mida al menos 44×44 píxeles CSS.

### C45: Usar CSS :focus-visible para indicar el foco de teclado
**Se relaciona con:** 2.4.7 Foco visible (Suficiente)
**Qué hace:** Aplica estilos de foco solo cuando la navegación es por teclado (no con mouse), usando el pseudo-selector `:focus-visible` en vez de `:focus`.
**Ejemplo:** `:focus-visible { outline: 5px solid red; }`
**Cómo testearlo:** Navegar con Tab/Shift+Tab por cada componente interactivo y verificar que aparezca un indicador visual de foco al recibirlo.
