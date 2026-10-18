---
title: "WCAG 2.2 Techniques — Client-Side Script"
status: in_progress
last_updated: 2026-10-13
---

# Técnicas de Client-Side Script (23)

> Ejemplos de formas de cumplir WCAG 2.2 usando JavaScript del lado del cliente. No son obligatorias: el contenido puede cumplir WCAG sin usar exactamente estas técnicas. Fuente: [W3C WAI — Techniques/client-side-script](https://www.w3.org/WAI/WCAG22/Techniques/client-side-script/).

### SCR1: Permitir al usuario ampliar el límite de tiempo predeterminado
**Se relaciona con:** 2.2.1 Tiempo ajustable (Suficiente)
**Qué hace:** Permite extender límites de tiempo controlados por scripts mediante formularios o diálogos que ofrecen ampliar el tiempo a al menos 10 veces el valor original.
**Ejemplo:** Un juego de ajedrez en línea avisa que el tiempo para mover se agota y ofrece "una opción para aumentar el tiempo".
**Cómo testearlo:** Esperar a que expire el límite de tiempo y verificar que exista una opción para extenderlo y que efectivamente se conceda más tiempo.

### SCR2: Usar manejadores redundantes de eventos de teclado y ratón
**Se relaciona con:** 2.1.1 Teclado (Suficiente, junto con G90)
**Qué hace:** Combina `onmouseover`/`onmouseout` con `onfocus`/`onblur` para que una interacción (p. ej. cambio de imagen) funcione igual con ratón y con teclado.
**Ejemplo:** Un enlace con imagen usa `updateImage()` llamada desde los cuatro eventos para alternar entre imagen normal y resaltada.
**Cómo testearlo:** Verificar que la imagen inicial sea la estándar, que hover y foco por teclado produzcan el mismo cambio, y que al quitar el ratón o el foco se restaure el estado original.

### SCR14: Usar scripts para hacer opcionales las alertas no esenciales
**Se relaciona con:** 2.2.4 Interrupciones (Suficiente); 4.1.3 Mensajes de estado (Advisory)
**Qué hace:** Da al usuario control para activar o desactivar anuncios de cambios no esenciales mediante `aria-live` y `aria-atomic` combinados con botones de alternancia.
**Ejemplo:** Un precio de acciones que se actualiza cada 10 segundos tiene botones "Activar/Desactivar anuncios" que cambian `aria-live` entre `"off"` y `"assertive"`.
**Cómo testearlo:** Confirmar que no se muestren alertas no esenciales por defecto y que exista un mecanismo accesible para activarlas/desactivarlas.

### SCR16: Proporcionar un script que avise que un límite de tiempo está por expirar
**Se relaciona con:** 2.2.1 Tiempo ajustable (Suficiente, junto con SCR1)
**Qué hace:** Al menos 20 segundos antes de que expire un límite de tiempo, muestra un diálogo preguntando si el usuario necesita más tiempo; si acepta, se reinicia el contador.
**Ejemplo:** Página de cotizaciones que se actualiza cada 5 minutos; 20 segundos antes aparece "¿Necesitás más tiempo?" usando `setTimeout()`/`clearTimeout()`.
**Cómo testearlo:** Verificar que, 20 segundos antes del límite, aparezca el diálogo de advertencia.

### SCR18: Proporcionar validación y alertas del lado del cliente
**Se relaciona con:** 3.3.1 Identificación de errores (Suficiente); 3.3.3 Sugerencia ante errores (Advisory); 3.3.4 Prevención de errores (Advisory)
**Qué hace:** Valida la entrada del usuario con scripts y muestra un diálogo de alerta en texto describiendo el error detectado.
**Ejemplo:** `onchange="if(isNaN(Date.parse(this.value))) alert('Valor de fecha inválido.');"`
**Cómo testearlo:** Ingresar datos inválidos en campos con formato requerido y verificar que se muestre una alerta describiendo el error.

### SCR19: Usar `onchange` en un `select` sin causar cambio de contexto
**Se relaciona con:** 3.2.2 Al recibir entradas (Suficiente); 3.2.5 Cambio a petición (Suficiente)
**Qué hace:** Actualiza dinámicamente otro elemento (p. ej. opciones de un segundo `select`) sin cambiar el contexto ni navegar a otra página.
**Ejemplo:** Al elegir un continente en el primer `select`, la función `countryChange()` repuebla el segundo `select` con los países correspondientes.
**Cómo testearlo:** Verificar que cambiar el valor del primer control actualice correctamente el segundo, y que no cambiar el valor no altere nada.

### SCR20: Usar funciones de teclado y de otros dispositivos
**Se relaciona con:** 2.1.1 Teclado (Suficiente, junto con G90)
**Qué hace:** Vincula una misma acción tanto a eventos de teclado como de ratón para que sea operable con múltiples dispositivos de entrada.
**Ejemplo:** `<a onmouseover="swapImageOn()" onfocus="swapImageOn()" onmouseout="swapImageOff()" onblur="swapImageOff()">` cambia una imagen de menú.
**Cómo testearlo:** Identificar toda la funcionalidad interactiva y verificar que sea accesible usando exclusivamente el teclado.

### SCR22: Usar scripts para controlar el parpadeo y detenerlo en cinco segundos o menos
**Se relaciona con:** 2.2.2 Pausar, detener, ocultar (Suficiente)
**Qué hace:** Controla con JavaScript un efecto de parpadeo, alternando visibilidad, y lo detiene automáticamente antes de los 5 segundos.
**Ejemplo:** Funciones `show()`/`hide()` alternadas con `setTimeout()` cada 450ms, deteniéndose a los 4.5 segundos.
**Cómo testearlo:** Cronometrar 5 segundos desde el inicio del parpadeo y confirmar que ya se haya detenido.

### SCR24: Usar mejora progresiva para abrir nuevas ventanas a pedido del usuario
**Se relaciona con:** 2.4.4 Propósito del enlace en contexto (Advisory); 2.4.6 Encabezados y etiquetas (Advisory); 2.4.9 Propósito del enlace, solo enlace (Advisory); 3.2.5 Cambio a petición (Suficiente)
**Qué hace:** Avisa al usuario que un enlace abrirá una nueva ventana y usa manejadores independientes del dispositivo, permitiendo que el navegador abra el contenido en la misma ventana si falla.
**Ejemplo:** Un script agrega el texto "(se abre en una ventana nueva)" a un enlace y valida en `onclick`/`onkeypress` si el usuario lo solicitó explícitamente (Enter/espacio).
**Cómo testearlo:** Activar cada enlace y comprobar el aviso previo, el uso de eventos independientes del dispositivo, y el comportamiento alternativo si no se abre la nueva ventana.

### SCR26: Insertar contenido dinámico en el DOM justo después de su elemento disparador
**Se relaciona con:** 2.4.3 Orden del foco (Suficiente)
**Qué hace:** Inserta el nuevo contenido en el DOM inmediatamente después del enlace o botón que lo disparó, para que el orden de tabulación y de lectura sean correctos por defecto.
**Ejemplo:** `src.parentElement.appendChild(el)` inserta un menú generado dinámicamente justo después del botón que ejecutó `ShowHide()`.
**Cómo testearlo:** Verificar que el script se dispare desde un evento `click` de enlace/botón y, con un inspector DOM, confirmar que el contenido nuevo queda ubicado correctamente en el árbol.

### SCR27: Reordenar secciones de la página usando el DOM
**Se relaciona con:** 2.4.3 Orden del foco (Suficiente)
**Qué hace:** Permite reordenar componentes mediante menús de enlaces con `onclick` (en vez de solo arrastrar y soltar), modificando el orden real en el DOM, no solo visualmente.
**Ejemplo:** Opciones "subir"/"bajar" en un menú disparan `MoveNode()`, que usa `swapNode()` para reordenar elementos en el DOM.
**Cómo testearlo:** Confirmar que existan menús de reordenamiento basados en enlaces, que los scripts se disparen solo con `onclick`, y que el orden cambie en el DOM (no solo visualmente).

### SCR28: Usar un menú expandible y contraíble para saltar bloques de contenido
**Se relaciona con:** 2.4.1 Evitar bloques (Suficiente)
**Qué hace:** Agrupa contenido repetitivo en un menú que el usuario puede expandir o contraer, facilitando saltarlo para llegar al contenido principal.
**Ejemplo:** Un botón con `aria-controls` y `aria-expanded` alterna su valor con una función `toggle()` para mostrar/ocultar una tabla de contenidos.
**Cómo testearlo:** Verificar que exista un control de expandir/contraer, que el contenido expandido se incluya en el orden de lectura lógico, y que contraído quede excluido del contenido determinado programáticamente.

### SCR29: Agregar acciones accesibles por teclado a elementos HTML estáticos
**Se relaciona con:** 2.1.1 Teclado (Asesora / Advisory)
**Qué hace:** Permite dar acceso por teclado a controles construidos sobre elementos estáticos (`div`, `span`), usando `tabindex` para hacerlos enfocables y agregando manejadores `onclick` y `onkeyup`/`onkeypress`.
**Ejemplo:** `<span id="active" role="button" tabindex="0">Hacer algo</span>` con JS que detecta tecla Enter o Espacio (`keyCode` 13 o 32) y ejecuta la misma función que el click.
**Cómo testearlo:** Verificar que el control funciona con click del mouse y también al enfocarlo con teclado y presionar Enter o Espacio.

### SCR30: Usar scripts para cambiar el texto de un enlace
**Se relaciona con:** 2.4.4 Propósito del enlace (en contexto) y 2.4.9 Propósito del enlace (solo enlace) (Suficiente)
**Qué hace:** Ofrece un control, cerca del inicio de la página, que expande dinámicamente el texto de los enlaces para que sean comprensibles sin contexto adicional, respetando distintas preferencias de usuario.
**Ejemplo:** Un botón que al activarse agrega texto contextual a los enlaces (ej. anexa " versión de La historia de la Web" a los enlaces con clase "hist") usando un objeto JS `linkContext`.
**Cómo testearlo:** Confirmar que el control de expansión existe al inicio, que es identificable por su propio texto, y que al activarlo los enlaces ambiguos se vuelven comprensibles.

### SCR31: Usar script para cambiar el color de fondo o el borde del elemento con foco
**Se relaciona con:** 2.4.7 Foco visible (Suficiente)
**Qué hace:** Usa JavaScript para cambiar dinámicamente el estilo (fondo o borde) del elemento que recibe foco, y revertirlo al perderlo, mejorando la visibilidad del indicador de foco.
**Ejemplo:** `onfocus="toggleFocus(this)" onblur="toggleFocus(this)"` donde la función alterna `el.style.backgroundColor` entre "yellow" e "inherit".
**Cómo testearlo:** Recorrer la página con Tab y verificar que el indicador de foco se mantiene claramente visible en cada elemento.

### SCR32: Proveer validación del lado del cliente y agregar texto de error vía el DOM
**Se relaciona con:** 3.3.1 Identificación de errores (Suficiente) y 3.3.3 Sugerencia ante errores (Asesora)
**Qué hace:** Valida campos de formulario con JavaScript e inserta mensajes de error en el DOM como un resumen con enlaces internos hacia los campos problemáticos.
**Ejemplo:** Un formulario con campos requeridos y de formato (texto, número, email) que al fallar la validación muestra una lista de errores enlazada a cada campo.
**Cómo testearlo:** Cargar valores válidos (sin errores) y luego inválidos (verificar que aparecen y reciben foco los mensajes), y confirmar que corregir el campo elimina el error.

### SCR33: Usar script para desplazar contenido, proveyendo un mecanismo de pausa
**Se relaciona con:** 2.2.1 Tiempo ajustable y 2.2.2 Pausar, detener, ocultar (Suficiente)
**Qué hace:** Permite controlar contenido en movimiento (scroll automático) mediante un mecanismo de pausa/reanudación implementado con CSS y JavaScript.
**Ejemplo:** `<div id="scroller"><p id="tag">Texto que se desplaza...</p></div>` con un enlace generado por JS para pausar o reanudar el desplazamiento.
**Cómo testearlo:** Verificar que existe un mecanismo de pausa, que el contenido se detiene sin reiniciarse solo, y que puede reanudarse desde el punto exacto donde se pausó.

### SCR34: Calcular tamaño y posición de forma que escale con el tamaño del texto
**Se relaciona con:** 1.4.4 Cambio de tamaño del texto, 1.4.8 Presentación visual (con G146) y 1.4.10 Reflow (Suficiente)
**Qué hace:** Usa propiedades JS (`offsetHeight`, `offsetWidth`, `offsetLeft`, `offsetTop`) para calcular dinámicamente dimensiones y posiciones que se adapten cuando el usuario cambia el tamaño del texto.
**Ejemplo:** Una función `calculatePosition()` que recorre los nodos padres sumando offsets para alinear un elemento debajo de otro de forma proporcional al texto.
**Cómo testearlo:** Aumentar el tamaño del texto al 200% desde la configuración del navegador (sin usar zoom) y verificar que los contenedores se ajustan sin que el texto se recorte o desaparezca.

### SCR35: Hacer acciones accesibles por teclado usando el evento `onclick` de anclas y botones
**Se relaciona con:** 2.1.1 Teclado (Suficiente, usada junto con G90)
**Qué hace:** Asocia acciones con scripts a elementos nativamente accionables (enlaces, botones) en vez de elementos genéricos, aprovechando que `onclick` es independiente del dispositivo y se activa también con Enter/Espacio o por APIs de accesibilidad.
**Ejemplo:** `<a href="hacer-algo.html" onclick="return doStuff();">hacer algo</a>`, con fallback de navegación a `hacer-algo.html` si el script no está disponible.
**Cómo testearlo:** Probar con script activo (click, teclado, Enter) y con script desactivado (verificar que funciona el fallback vía `href` o envío de formulario).

### SCR36: Proveer un mecanismo para mostrar texto en movimiento/scroll en una ventana estática
**Se relaciona con:** 2.2.1 Tiempo ajustable (Suficiente)
**Qué hace:** Permite a los usuarios detener el desplazamiento de texto y verlo completo de forma estática, para leer a su propio ritmo, beneficiando a usuarios con lectura más lenta o que usan tecnología de asistencia.
**Ejemplo:** Un botón alterna entre un contenedor chico con scroll (`scrolling`, 200x50px) y uno expandido estático (`notscrolling`, 500px), deteniendo el `setInterval` de la animación.
**Cómo testearlo:** Activar el control y verificar que el texto completo queda disponible de forma estática, sin presión de tiempo para leerlo.

### SCR38: Crear una versión alternativa conforme para una página con mejora progresiva
**Se relaciona con:** No vinculada a un criterio específico (la página aclara que no está referenciada desde ningún documento "Understanding")
**Qué hace:** Guarda la versión HTML base (previa a la mejora progresiva) y ofrece un toggle para volver a ella, resolviendo el problema de qué versión cuenta como la "versión conforme" cuando se usa mejora progresiva.
**Ejemplo:** Un script (`acctoggle.js`) guarda `document.head.innerHTML` y `document.body.innerHTML` iniciales y los restaura si la URL incluye `#accessible`.
**Cómo testearlo:** Verificar que la versión mejorada tiene un enlace a la versión alternativa conforme, y que esa alternativa efectivamente cumple WCAG 2 en el nivel reclamado.

### SCR39: Hacer que el contenido en hover o foco sea hoverable, descartable y persistente
**Se relaciona con:** 1.4.13 Contenido en hover o foco (Suficiente)
**Qué hace:** Asegura que el contenido adicional mostrado al pasar el mouse o enfocar permanezca visible si el puntero se mueve sobre él, no se cierre automáticamente, y pueda descartarse con teclado (ej. Escape) sin mover el foco.
**Ejemplo:** Un enlace muestra un tooltip con información adicional al hacer hover/focus; JS gestiona la visibilidad con `mouseover`/`focus` y escucha la tecla Escape para cerrarlo.
**Cómo testearlo:** Para hover, verificar que el puntero puede moverse sobre el contenido sin que desaparezca y que se puede cerrar con teclado; para foco, verificar que persiste indefinidamente y es descartable igual.

### SCR40: Usar la media query CSS `prefers-reduced-motion` en JavaScript para prevenir movimiento
**Se relaciona con:** 2.3.3 Animación por interacciones (Suficiente)
**Qué hace:** Detecta mediante JavaScript la preferencia del sistema de reducir el movimiento (`prefers-reduced-motion`) para deshabilitar animaciones disparadas por interacciones que puedan distraer o causar malestar físico.
**Ejemplo:** `const mql = window.matchMedia("(prefers-reduced-motion: no-preference)"); if (mql.matches) { /* ejecutar animación */ }`
**Cómo testearlo:** Activar la preferencia de movimiento reducido en el sistema y verificar, para cada elemento con animación, que esta se suprime (salvo que sea esencial para la funcionalidad).
