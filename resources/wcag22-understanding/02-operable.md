---
title: "WCAG 2.2 Understanding — Principio 2: Operable (Operable)"
status: in_progress
last_updated: 2026-10-13
---

# 2. Operable (Operable)

> Los componentes de la interfaz de usuario y la navegación deben ser operables.

Fuente: [W3C WAI — Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/)

## 2.1 Accesible por teclado

### 2.1.1 Teclado (Nivel A)
**Qué pide:** Que toda la funcionalidad del contenido esté disponible mediante teclado o una interfaz de teclado alterna, sin requerir tiempos específicos para cada pulsación individual (salvo que la función dependa inherentemente de la trayectoria o velocidad del movimiento, no solo del punto final).
**Por qué importa:** Las personas ciegas no pueden usar dispositivos que requieren coordinación ojo-mano, como el ratón. Las personas con baja visión pueden tener dificultad para seguir el puntero en pantalla, y quienes tienen temblores en las manos u otras limitaciones motrices suelen encontrar el teclado más manejable que el mouse.
**Cómo cumplirlo:**
- Usar controles de formularios HTML y enlaces estándar, que ya son accesibles por teclado de forma nativa.
- Proporcionar manejadores de eventos activados por teclado (no solo por mouse).
- Implementar redundancia: que cada acción tenga tanto manejador de teclado como de mouse.
- Usar atributos WAI-ARIA para hacer que widgets personalizados tengan acciones accesibles por teclado.
**Ejemplos/notas:** Un programa de dibujo que permite crear, dimensionar y rotar objetos desde el teclado; una aplicación de arrastrar y soltar que también admite "cortar" y "pegar"; un formulario de búsqueda donde Enter envía aunque el botón visual solo responda al puntero. Quedan exceptuados casos como programas de pintura con trazos dependientes de la velocidad, o simuladores de vuelo/helicóptero.

### 2.1.2 Sin trampas de teclado (Nivel A)
**Qué pide:** Que el foco del teclado nunca quede "atrapado" dentro de una subsección del contenido sin que el usuario pueda salir usando solo el teclado. Si se requieren teclas distintas de las flechas, el Tab o Escape para salir, se debe informar al usuario cómo hacerlo.
**Por qué importa:** Afecta especialmente a personas que dependen del teclado o de una interfaz de teclado para navegar la web, incluyendo personas ciegas y personas con discapacidades físicas que no pueden usar el mouse para "escapar" de un elemento.
**Cómo cumplirlo:**
- Asegurar que los usuarios no queden atrapados en ningún componente o subsección de contenido.
- Permitir restringir el foco temporalmente en casos justificados (como diálogos modales), siempre que exista una salida estándar.
- Usar métodos de salida convencionales: Escape, flechas sin modificar, o Tab.
- Si se usa un método no estándar, instruir explícitamente al usuario sobre cómo salir.
**Ejemplos/notas:** Un widget de calendario donde se navega con Tab sin quedar atrapado; un diálogo modal donde el foco se mantiene dentro hasta presionar "Cancelar", "Aceptar" o Escape; un editor de texto enriquecido que indica explícitamente usar Alt+F10 para salir del área de edición.

### 2.1.3 Teclado (sin excepciones) (Nivel AAA)
**Qué pide:** Lo mismo que 2.1.1, pero sin ninguna excepción: toda la funcionalidad debe ser operable por teclado, incluso aquella que dependería de la trayectoria del movimiento. El contenido que use necesariamente entrada dependiente de la ruta no puede cumplir este criterio de nivel AAA.
**Por qué importa:** Las personas que solo pueden usar una interfaz de teclado necesitan poder realizar absolutamente todas las acciones disponibles en el contenido, sin excepciones que las dejen fuera de ciertas funciones.
**Cómo cumplirlo:**
- No existen técnicas adicionales específicas: se siguen las mismas técnicas que para 2.1.1.
- No es obligatorio que cada control visible sea enfocable por teclado, siempre que exista una forma alternativa de realizar acciones comparables.
- Si el contenido requiere entrada dependiente de la ruta, directamente no puede alcanzar este nivel.
**Ejemplos/notas:** Botones personalizados que solo reaccionan a Enter (o a combinaciones de teclas personalizadas) pueden igualmente satisfacer el criterio, lo que demuestra flexibilidad en la implementación.

### 2.1.4 Atajos de teclado de un solo carácter (Nivel A)
**Qué pide:** Que, si un atajo de teclado usa solo letras, puntuación, números o símbolos (sin modificador como Ctrl o Alt), exista al menos una forma de desactivarlo, remapearlo a una combinación con tecla no imprimible, o activarlo solo mientras el componente tiene el foco.
**Por qué importa:** Reduce la activación accidental de atajos. Los usuarios de entrada por voz son especialmente afectados, porque su dictado se interpreta letra por letra y puede disparar comandos involuntarios; también ayuda a personas con discapacidades de destreza que presionan teclas sin querer, y a personas con discapacidades cognitivas que se benefician de poder remapear atajos de forma consistente entre aplicaciones.
**Cómo cumplirlo:**
- Proporcionar un mecanismo para desactivar completamente los atajos de un solo carácter.
- Permitir remapear el atajo para que incluya una tecla modificadora no imprimible (Ctrl, Alt, etc.).
- Activar el atajo únicamente cuando el componente correspondiente tiene el foco.
- Basta con cumplir una sola de estas tres opciones.
**Ejemplos/notas:** Gmail y WordPress permiten desactivar o modificar sus atajos de un solo carácter. Una usuaria de entrada por voz evita activar atajos accidentalmente al desactivarlos; un usuario de teclado cambia el atajo "S" por "Ctrl+S" para evitar pérdidas de enfoque involuntarias.

## 2.2 Tiempo suficiente

### 2.2.1 Tiempo ajustable (Nivel A)
**Qué pide:** Que, para cada límite de tiempo establecido por el contenido, el usuario pueda desactivarlo, ajustarlo (hasta diez veces el valor por defecto) o extenderlo con una acción simple antes de que expire, salvo excepciones justificadas (tiempo real, esencial, o superior a 20 horas).
**Por qué importa:** Las personas ciegas, con baja visión, con problemas de destreza o con limitaciones cognitivas necesitan más tiempo para leer, ubicar elementos en pantalla y completar formularios. También incluye a usuarios de lectores de pantalla y a personas sordas que usan lengua de señas y requieren tiempo extra para acceder a información textual.
**Cómo cumplirlo:**
- Desactivar el límite: permitir apagarlo antes de encontrarlo.
- Ajustar el límite: autorizar extensiones de hasta diez veces el valor predeterminado.
- Extender el límite: avisar antes de que expire y conceder al menos 20 segundos para prorrogarlo mediante una acción simple, permitiendo múltiples extensiones.
- Se consideran excepciones válidas los límites de tiempo real (p. ej. subastas) donde el límite se aplica igual a todos los participantes.
**Ejemplos/notas:** Página que pregunta si el usuario necesita más tiempo tras un período de inactividad; titular que rota automáticamente pero permite extender la duración hasta diez veces; animación con texto que aparece y desaparece, con botón de pausa; sitio de venta de entradas que avisa antes de expirar el tiempo y permite extenderlo con un botón simple.

### 2.2.2 Pausar, detener, ocultar (Nivel A)
**Qué pide:** Que, para contenido que se mueve, parpadea, se desplaza o se actualiza automáticamente sin interacción directa del usuario, exista un mecanismo para pausarlo, detenerlo u ocultarlo, salvo que dure menos de 5 segundos o sea parte de una actividad esencial.
**Por qué importa:** Evita distracciones durante la interacción con la página. Afecta en particular a personas con discapacidades cognitivas y trastornos por déficit de atención, para quienes el contenido en movimiento continuo resulta muy perturbador, así como a personas con discapacidades visuales o de lectura y usuarios de lectores de pantalla, para quienes el contenido dinámico genera problemas de concentración.
**Cómo cumplirlo:**
- Permitir pausar el contenido y reanudarlo desde donde quedó.
- Limitar el contenido parpadeante o en movimiento a una duración menor a 5 segundos.
- Usar scripts que detengan el parpadeo automáticamente dentro de ese plazo.
- Proporcionar controles (botones o mecanismos) que detengan el contenido en movimiento.
- Ofrecer una opción para recargar la página sin el contenido parpadeante.
**Ejemplos/notas:** Animaciones educativas con botones de "pausar" y "reiniciar"; un anuncio que parpadea pero se detiene tras 5 segundos; una flecha intermitente junto al botón de enviar que cesa tras 5 segundos. Los indicadores de carga no requieren controles si son el único contenido visible en ese momento.

### 2.2.3 Sin tiempos (Nivel AAA)
**Qué pide:** Que el tiempo no sea parte esencial de ninguna actividad presentada por el contenido, salvo en eventos en tiempo real no controlables (como una subasta en vivo), sin las excepciones más flexibles que admite 2.2.1.
**Por qué importa:** Beneficia a personas con discapacidades físicas que necesitan más tiempo para reaccionar; a personas con baja visión que requieren tiempo adicional para ubicar elementos; a usuarios ciegos con lectores de pantalla que precisan más tiempo para entender la estructura; a personas con limitaciones cognitivas que necesitan procesar la información con calma; y a personas sordas que pueden requerir más tiempo para leer en una segunda lengua.
**Cómo cumplirlo:**
- Permitir a los usuarios completar una actividad sin ningún límite de tiempo.
- Diseñar evaluaciones o pruebas calificadas por desempeño/puntuación y no por velocidad de respuesta.
- Diseñar juegos u otras interacciones por turnos en vez de competencia simultánea en tiempo real.
**Ejemplos/notas:** Pruebas calibradas por puntuación en lugar de velocidad; juegos basados en turnos en vez de tiempo real simultáneo.

### 2.2.4 Interrupciones (Nivel AAA)
**Qué pide:** Que las interrupciones (actualizaciones de contenido generadas por el servidor o el autor) puedan ser pospuestas o suprimidas por el usuario, excepto las que involucren una emergencia.
**Por qué importa:** Beneficia especialmente a personas con limitaciones cognitivas o trastornos de atención, que necesitan mantenerse enfocadas en lo que leen, y a usuarios ciegos o con baja visión, para quienes una actualización automática del contenido mientras lo están leyendo genera discontinuidad y confusión (pueden empezar a leer un tema y terminar leyendo otro sin darse cuenta).
**Cómo cumplirlo:**
- Proporcionar un mecanismo para posponer las actualizaciones de contenido.
- Ofrecer la opción de solicitar manualmente las actualizaciones en lugar de que ocurran de forma automática.
- Usar scripts para que las alertas no esenciales sean opcionales.
**Ejemplos/notas:** La página de preferencias de un portal web incluye una opción para posponer todas las actualizaciones y alertas (salvo las de emergencia) hasta el final de la sesión actual.

### 2.2.5 Reautenticación (Nivel AAA)
**Qué pide:** Que cuando una sesión autenticada expira, el usuario pueda volver a autenticarse y continuar la actividad sin perder los datos que ya había ingresado.
**Por qué importa:** Muchos sitios imponen límites de tiempo de inactividad por razones de seguridad, lo cual perjudica a personas con discapacidades que necesitan más tiempo para completar una transacción. Beneficia especialmente a personas con limitaciones cognitivas que leen con lentitud y requieren tiempo adicional para responder, a usuarios de lectores de pantalla que necesitan más tiempo para navegar formularios complejos, y a personas con discapacidades motoras que requieren tiempo extra para interactuar con los controles.
**Cómo cumplirlo:**
- Guardar los datos ingresados para reutilizarlos después de la reautenticación.
- Codificar los datos del usuario de forma oculta o encriptada en la página de reautenticación para recuperarlos tras el login.
**Ejemplos/notas:** Una tienda en línea desconecta al usuario por timeout durante la compra, pero al reautenticarse el checkout se restaura con la misma información y estado; un programa de correo con timeout de 30 minutos notifica previamente y ofrece un enlace para reautenticarse en una ventana nueva, manteniendo intacto el email en redacción.

### 2.2.6 Tiempos de espera (Nivel AAA)
**Qué pide:** Que se advierta a los usuarios sobre la duración de cualquier inactividad que pueda causar pérdida de datos, a menos que los datos se conserven por más de 20 horas cuando el usuario no realiza ninguna acción.
**Por qué importa:** Protege especialmente a personas con discapacidades cognitivas (relacionadas con el lenguaje, la memoria, el enfoque/atención o las funciones ejecutivas y la toma de decisiones), que requieren más tiempo para leer o completar formularios. Conocer la duración del timeout les permite decidir si pueden completar la tarea, reduciendo la frustración y permitiendo tomar descansos sin perder el progreso.
**Cómo cumplirlo:**
- Establecer el timeout después de al menos 20 horas de inactividad.
- Alternativamente, almacenar los datos del usuario durante más de 20 horas.
- Proporcionar una advertencia sobre la duración de la inactividad permitida al inicio del proceso.
**Ejemplos/notas:** Un comercio electrónico guarda la información de compra durante 20 horas o más; una aplicación fiscal notifica que una inactividad mayor a una hora disparará un timeout por seguridad; un formulario de contacto simple no tiene timeout, y los datos solo se pierden si se cierra el navegador.

## 2.3 Convulsiones y reacciones físicas

### 2.3.1 Tres destellos o por debajo del umbral (Nivel A)
**Qué pide:** Que las páginas web no contengan nada que parpadee más de tres veces por segundo, a menos que el destello esté por debajo de los umbrales generales y rojo definidos (relacionados con el tamaño del área afectada y el contraste de luminancia).
**Por qué importa:** Protege a personas con trastornos de convulsiones fotosensibles, especialmente epilepsia fotosensible, que son vulnerables a ciertos patrones de parpadeo. El criterio se basa en normas de televisión adaptadas a pantallas de computadora, considerando que el contenido se visualiza desde distancias más cercanas.
**Cómo cumplirlo:**
- Limitar la frecuencia: que nada parpadee más de tres veces por segundo.
- Reducir el área afectada: mantener las zonas que destellan por debajo de un tamaño límite (aproximadamente 87.296 píxeles CSS).
- Usar herramientas de análisis especializadas para verificar la luminancia y el cumplimiento del umbral.
**Ejemplos/notas:** Un video de disparo de arma limita el tamaño del destello a un área pequeña bajo el umbral; una escena de película con relámpagos se edita para mostrar un máximo de tres destellos por segundo.

### 2.3.2 Tres destellos (Nivel AAA)
**Qué pide:** Que las páginas web no contengan nada que parpadee más de tres veces por segundo, sin ninguna excepción por tamaño de área o umbral de luminosidad (a diferencia del nivel AA).
**Por qué importa:** Reduce significativamente el riesgo de convulsiones al eliminar todo contenido que parpadee más de tres veces por segundo, sin importar brillo o tamaño; incluso un solo píxel parpadeante violaría este criterio. Beneficia a personas con epilepsia fotosensible y otros trastornos de convulsiones fotosensibles, permitiéndoles acceder a todo el contenido sin depender únicamente de alternativas textuales.
**Cómo cumplirlo:**
- Única técnica suficiente documentada: asegurar que ningún componente del contenido parpadee más de tres veces en un segundo, sin excepciones de tamaño o contraste.
**Ejemplos/notas:** Una película con escenas de relámpagos brillantes debe editarse para que los relámpagos ocurran como máximo tres veces por segundo, sin excepción alguna.

### 2.3.3 Animación provocada por interacciones (Nivel AAA)
**Qué pide:** Que la animación activada por la interacción del usuario (por ejemplo, al desplazarse o al interactuar con un control) pueda desactivarse, a menos que sea esencial para la funcionalidad o la información que se transmite.
**Por qué importa:** Algunos usuarios experimentan mareos, náuseas o dolores de cabeza al ver contenido animado; por ejemplo, si desplazarse por una página hace que los elementos se muevan más allá del movimiento esencial asociado al scroll, puede desencadenar trastornos vestibulares. El desplazamiento tipo parallax es un ejemplo frecuente de animación innecesaria. Beneficia principalmente a personas con trastornos vestibulares, que necesitan control sobre el movimiento disparado por interacciones.
**Cómo cumplirlo:**
- Usar la consulta de medios CSS `prefers-reduced-motion` para evitar o reducir el movimiento.
- Implementar JavaScript que respete la preferencia `prefers-reduced-motion` del sistema operativo o navegador.
- Permitir que los usuarios establezcan una preferencia global que desactive las animaciones no esenciales.
**Ejemplos/notas:** Desplazamiento parallax con una opción explícita en la página para desactivar animaciones innecesarias de forma global; transiciones que se desactivan automáticamente cuando el usuario activa la preferencia de movimiento reducido; aplicaciones donde la animación es parte esencial de la funcionalidad (como previsualizaciones de animación) quedan exceptuadas de este requisito.

## 2.4 Navegable

### 2.4.1 Evitar bloques (Nivel A)
**Qué pide:** Debe existir un mecanismo para evitar bloques de contenido que se repiten en múltiples páginas web (por ejemplo, menús de navegación o encabezados idénticos), de modo que quienes navegan de forma secuencial puedan llegar directamente al contenido principal. No es necesario duplicar funciones que ya ofrece el user agent (como "ir al inicio de la página"), y el foco debe estar en páginas relacionadas dentro de un conjunto definido, no en evitar toda posible repetición entre páginas no relacionadas.
**Por qué importa:** Los usuarios de lectores de pantalla evitan escuchar el mismo encabezado y navegación en cada página; los usuarios de teclado llegan al contenido con menos pulsaciones (evitando incluso dolor físico por el uso excesivo del teclado); los usuarios de magnificadores de pantalla no necesitan buscar repetidamente dónde empieza el contenido principal; y agrupar enlaces en listas beneficia a usuarios con discapacidades cognitivas y a usuarios de lectores de pantalla.
**Cómo cumplirlo:**
- Crear enlaces de salto ("skip links") hacia el contenido principal o para saltar bloques repetidos.
- Usar landmarks ARIA para identificar regiones de la página (navegación, principal, pie, etc.).
- Aplicar encabezados al inicio de cada sección.
- Usar el atributo `title` en iframes.
- Implementar menús de navegación expandibles/colapsables.
**Ejemplos/notas:** En un sitio de noticias, un usuario de teclado debería tabular por ~40 enlaces y uno de lector de pantalla escuchar 200 palabras antes de llegar al contenido si no hubiera un mecanismo de salto. En un sitio de e-commerce, un enlace de salto permite evitar listas extensas de filtros y llegar directo a los resultados de productos.

### 2.4.2 Página titulada (Nivel A)
**Qué pide:** Cada página web debe tener un título que describa su tema o propósito, para que los usuarios puedan identificarla sin necesidad de interpretar todo el contenido. Los títulos aparecen en mapas del sitio, resultados de búsqueda y en la pestaña/barra de título del navegador. En aplicaciones de página única (SPA), el título debe actualizarse dinámicamente para reflejar la vista actual.
**Por qué importa:** Todos los usuarios se benefician al identificar rápidamente si una página contiene lo que buscan. Las personas con discapacidad visual pueden diferenciar páginas cuando tienen varias abiertas; las personas con discapacidades cognitivas, memoria a corto plazo limitada o dificultades de lectura identifican el contenido gracias al título; y las personas con discapacidades motrices severas que navegan por audio también se benefician.
**Cómo cumplirlo:**
- Proporcionar títulos descriptivos usando el elemento HTML `<title>`.
- En documentos PDF, especificar el título en el diccionario de información del documento.
- Mantener coherencia entre el texto del enlace que lleva a la página y su título.
**Ejemplos/notas:** Un conjunto de páginas con títulos como "Guía de Prácticas de Autoría ARIA | APG | WAI | W3C" para la página principal y "Patrón X | APG | WAI | W3C" para páginas internas. Una app bancaria genera títulos dinámicos como "Banco XYZ, cuentas de Alex Smith" o "Banco XYZ, resumen de diciembre de 2005 de la cuenta 1234-5678".

### 2.4.3 Orden del foco (Nivel A)
**Qué pide:** Cuando los usuarios navegan secuencialmente por el contenido, deben encontrar la información en un orden coherente con el significado del contenido y que permita operarlo desde el teclado. El orden de foco no necesariamente debe coincidir con el orden visual, y puede haber múltiples órdenes lógicos válidos siempre que se implemente uno de forma consistente.
**Por qué importa:** Beneficia a usuarios con discapacidades motrices que dependen del teclado, asegurando secuencias de navegación lógicas y utilizables; a usuarios con dificultades de lectura, evitando desorientación cuando el foco salta de forma inesperada; a usuarios con discapacidad visual, que se orientan mejor cuando el orden de tabulación es predecible; y a usuarios de magnificadores de pantalla, que solo ven una porción de la página a la vez.
**Cómo cumplirlo:**
- Ordenar los elementos interactivos siguiendo la secuencia del contenido.
- Asegurar que el orden del DOM coincida con el orden visual.
- Insertar contenido dinámico inmediatamente después del elemento que lo dispara.
- Usar el elemento `<dialog>` de HTML para modales.
**Ejemplos/notas:** Navegación en árbol con flechas para expandir/colapsar nodos; diálogos no modales donde el foco se mueve al diálogo tras activar el botón disparador; diálogos modales que atrapan el foco dentro de sí mismos; y diseños en múltiples columnas donde el orden visual (CSS) difiere del orden en el código fuente HTML.

### 2.4.4 Propósito del enlace (en contexto) (Nivel A)
**Qué pide:** El propósito de cada enlace debe poder determinarse a partir del texto del enlace solo, o del texto del enlace junto con su contexto (la oración, párrafo, elemento de lista o celda de tabla que lo contiene), de forma que el usuario entienda el destino antes de activarlo. Si el propósito no puede determinarse ni siquiera con el contexto disponible en la página, el criterio no aplica en ese caso.
**Por qué importa:** Las personas con discapacidades motrices ganan eficiencia al poder saltar enlaces que no les interesan; las personas con limitaciones cognitivas evitan desorientarse por navegación poco clara; y las personas con discapacidad visual pueden determinar el propósito de un enlace explorando su contexto, sin necesidad de estrategias de navegación complejas o pulsaciones excesivas.
**Cómo cumplirlo:**
- Redactar texto de enlace descriptivo que identifique su propósito.
- Combinar el texto del enlace con el contexto de la oración que lo rodea.
- Usar asociaciones programáticas mediante ARIA (aria-label, aria-labelledby).
- Apoyarse en elementos estructurales que lo envuelven (ítems de lista, párrafos, celdas de tabla).
- Ofrecer controles para alternar entre versiones cortas y largas del texto del enlace.
**Ejemplos/notas:** "Período medieval de la historia" como enlace descriptivo; descripción previa al enlace "Conocé más sobre la Comisión de Voto Electrónico del Gobierno de Irlanda en ¡Andá a Votar!"; un ícono junto con texto descriptivo; títulos de libros con enlaces separados "PDF" y "mp3"; resúmenes de noticias seguidos de un enlace "Leer más".

### 2.4.5 Múltiples formas (Nivel AA)
**Qué pide:** Debe existir más de una manera de localizar una página web dentro de un conjunto de páginas, salvo cuando la página sea resultado de un proceso o paso intermedio (como una confirmación de pago). Incluso los sitios pequeños deben ofrecer opciones de orientación, por ejemplo enlaces desde la página de inicio que funcionen como mapa del sitio.
**Por qué importa:** Las personas con discapacidad visual pueden navegar más eficientemente mediante búsqueda en vez de recorrer barras de navegación con magnificador o lector de pantalla; las personas con discapacidades cognitivas se benefician de una tabla de contenidos o mapa del sitio que ofrezca una visión general en lugar de recorrer páginas secuencialmente; y en publicaciones digitales, la tabla de contenidos y el índice ayudan a ubicar contenido y mantener la posición de lectura.
**Cómo cumplirlo (se requieren al menos dos):**
- Enlaces de navegación entre páginas relacionadas.
- Tabla de contenidos.
- Mapa del sitio.
- Función de búsqueda.
- Listado completo de enlaces a través de las páginas.
- Enlaces desde la página de inicio a todas las páginas del sitio.
**Ejemplos/notas:** Un sitio de recetas que ofrece tanto búsqueda por ingrediente como navegación por categorías; un sitio de salón de belleza de cinco páginas con navegación secuencial más enlaces cruzados. Están exentas las páginas de confirmación de procesos (por ejemplo, de un banco) y los resultados de un motor de búsqueda.

### 2.4.6 Encabezados y etiquetas (Nivel AA)
**Qué pide:** Los encabezados y etiquetas deben describir el tema o propósito del contenido, para que los usuarios comprendan la organización de la página y ubiquen la información que buscan. No hace falta que sean extensos: "una palabra, o incluso un solo carácter, puede ser suficiente" si da una pista adecuada. El criterio exige que, si se proveen encabezados y etiquetas, sean descriptivos — no obliga a que existan (eso lo cubren otros criterios como 1.3.1 y 4.1.2).
**Por qué importa:** Los encabezados descriptivos ayudan especialmente a personas con lectura lenta o memoria a corto plazo limitada, permitiéndoles predecir el contenido de cada sección. Las etiquetas de formulario claras ayudan a completar formularios correctamente. Cuando están bien marcados semánticamente, los usuarios de lectores de pantalla se benefician al navegar listas de encabezados generadas automáticamente o moverse entre secciones.
**Cómo cumplirlo:**
- Redactar encabezados descriptivos del contenido que introducen.
- Redactar etiquetas descriptivas para campos y controles.
- Asegurar que estén correctamente marcados en el código (ver también 1.3.1).
**Ejemplos/notas:** Titulares de noticias que reflejan claramente el tema del artículo; secciones de una guía de escritura como "Eliminar palabras innecesarias"; estructura consistente en trabajos de congreso (Resumen, Introducción, Conclusión); campos de formulario etiquetados "Nombre" y "Apellido"; un botón con ícono de lupa cuya etiqueta accesible es "buscar".

### 2.4.7 Foco visible (Nivel AA)
**Qué pide:** Cualquier interfaz operable con teclado debe tener un modo de operación donde el indicador de foco del teclado sea visible. Los user agents pueden optimizar cuándo se muestra el indicador (por ejemplo, solo durante el uso de teclado), pero debe existir al menos un modo donde el indicador permanezca visible de forma permanente, sin límite de tiempo. Además, el indicador de foco está sujeto a los requisitos de contraste de 1.4.11.
**Por qué importa:** Los usuarios de teclado pueden determinar visualmente qué componente recibirá las próximas acciones; las personas con limitaciones cognitivas (déficit de atención, memoria a corto plazo, funciones ejecutivas) pueden ubicar fácilmente dónde está el foco en cada momento.
**Cómo cumplirlo:**
- Usar componentes de interfaz nativos que ya resaltan el foco del navegador.
- Aplicar estilos CSS (`:focus`, `:focus-visible`) para indicar el foco.
- Usar los indicadores de foco por defecto de la plataforma.
- Implementar indicadores de foco visibles personalizados por el autor.
- Crear indicadores de foco de dos colores para asegurar contraste.
- Usar scripting para modificar el color de fondo o los bordes al recibir foco.
**Ejemplos/notas:** Campos de texto que muestran un cursor visible o texto resaltado al recibir foco; controles de interfaz que muestran un borde visible al recibir foco mediante teclado.

### 2.4.8 Ubicación (Nivel AAA)
**Qué pide:** Debe existir una forma de que el usuario se oriente dentro de un conjunto de páginas web, un sitio o una aplicación web, y pueda encontrar información relacionada.
**Por qué importa:** Ayuda a personas con períodos de atención reducidos que pueden desorientarse tras varios pasos de navegación, y particularmente a usuarios que llegan mediante enlaces directos a páginas muy anidadas y necesitan navegar el sitio para comprender el contenido o descubrir recursos adicionales.
**Cómo cumplirlo:**
- Migas de pan (breadcrumbs).
- Mapas del sitio.
- Indicadores de ubicación actual en la barra de navegación.
- Atributo ARIA `aria-current` para marcar el ítem activo.
- Identificar las relaciones de la página web dentro de una colección mayor.
**Ejemplos/notas:** La página de inicio de un grupo de investigación universitario enlaza al departamento y a la universidad, estableciendo contexto jerárquico. Un sitio tipo portal muestra migas de pan que indican la posición del usuario dentro de la jerarquía de categorías, además de un enlace a la página principal del portal.

### 2.4.9 Propósito del enlace (solo enlace) (Nivel AAA)
**Qué pide:** El propósito de un enlace debe poder entenderse a partir únicamente del texto del enlace, sin necesidad de contexto adicional (por ejemplo, al verlo en una lista completa de enlaces de la página). El nombre del documento o aplicación de destino puede ser suficiente. Existe una excepción cuando el propósito no puede determinarse ni siquiera con todo el contexto de la página; en ese caso, toda la información contextual necesaria debe incorporarse al propio texto del enlace. Puede ofrecerse un mecanismo para alternar entre texto de enlace breve y completo.
**Por qué importa:** Las personas con discapacidades motrices pueden saltar páginas que no les interesan sin pulsaciones innecesarias; las personas con limitaciones cognitivas evitan desorientarse en navegación no deseada; y las personas con discapacidad visual mantienen su posición en el contenido y se benefician de listas de enlaces de lectores de pantalla que describen claramente el destino.
**Cómo cumplirlo:**
- Redactar texto de enlace descriptivo (de forma general o específica en HTML).
- Usar etiquetas ARIA para transmitir el propósito.
- Implementar controles de usuario para alternar entre texto corto y largo.
- Usar CSS para ocultar visualmente texto descriptivo adicional, manteniéndolo accesible.
- En PDFs, usar anotaciones de enlace y texto alternativo.
**Ejemplos/notas:** Un ícono combinado con texto ("Comisión de Voto Electrónico del Gobierno de Irlanda") formando un único enlace; enlaces de formato de libro ("Los viajes de Gulliver, MP3") que incluyen el título junto con el tipo de formato.

### 2.4.10 Encabezados de sección (Nivel AAA)
**Qué pide:** Deben proveerse encabezados para las secciones de una página web cuando esta está organizada en secciones. Los documentos extensos se benefician de estructuras jerárquicas de encabezados que aclaran la organización del contenido y facilitan la navegación. Es de Nivel AAA porque no puede aplicarse a todo tipo de contenido (por ejemplo, documentos preexistentes sin encabezados originales).
**Por qué importa:** Las personas ciegas pueden identificar las transiciones entre secciones y entender el propósito de cada una; las personas con discapacidades de aprendizaje comprenden más fácilmente la organización general de la página usando los encabezados como guía estructural; quienes navegan con teclado pueden saltar entre encabezados para ubicar rápidamente contenido relevante; y los usuarios de contenido dinámico pueden acceder rápidamente a secciones actualizadas mediante navegación por encabezados.
**Cómo cumplirlo:**
- Organizar la página usando encabezados.
- Ubicar elementos de encabezado al inicio de cada sección de contenido.
**Ejemplos/notas:** Un menú de restaurante con secciones tituladas Entradas, Ensaladas, Sopas, Plato principal, Postre; una página de configuración dividida en grupos relacionados con encabezados descriptivos para cada clase de ajustes.

### 2.4.11 Foco no oscurecido (mínimo) (Nivel AA)
**Qué pide:** Cuando un componente de interfaz recibe foco de teclado, el componente no debe quedar completamente oculto por otro contenido creado por el autor (como encabezados o pies de página fijos/"sticky"); al menos debe permanecer parcialmente visible en el viewport. (La versión AAA, 2.4.12, exige visibilidad completa).
**Por qué importa:** Los usuarios que dependen del teclado, entrada por voz o dispositivos alternativos pueden ver el componente que recibe el foco; los usuarios con baja visión que usan magnificación se benefician de una indicación visible del punto actual de interacción; y los usuarios con limitaciones de atención o memoria pueden descubrir más fácilmente dónde está el foco.
**Cómo cumplirlo:**
- Usar la propiedad CSS `scroll-padding` para evitar que contenido oscurezca el elemento enfocado.
- Diseñar encabezados/pies "sticky" de forma que dejen espacio para el contenido enfocado.
- Asegurar que diálogos modales no bloqueen la visibilidad del propio foco dentro de ellos.
**Ejemplos/notas:** Un pie de página fijo que usa scroll-padding para que los ítems enfocados permanezcan visibles al tabular; un diálogo modal de aceptación de cookies mantiene visible el foco porque el propio diálogo permanece en pantalla; una notificación fija que desaparece automáticamente al perder el foco, evitando ocultar otros controles.

### 2.4.12 Foco no oscurecido (mejorado) (Nivel AAA)
**Qué pide:** El componente que recibe el foco del teclado debe permanecer siempre completamente visible en el viewport del usuario, sin que ningún contenido del autor (encabezados fijos, pies fijos, diálogos no modales, etc.) lo oculte, ni siquiera parcialmente.
**Por qué importa:** Beneficia a los usuarios que dependen del teclado (incluyendo entrada por voz, teclados en pantalla y software de barrido) para identificar qué componente tiene el foco; a usuarios con baja visión que usan magnificación; y a usuarios con limitaciones cognitivas de atención, memoria o función ejecutiva.
**Cómo cumplirlo:**
- Usar `scroll-padding` en CSS para evitar que overlays oculten el componente enfocado.
**Ejemplos/notas:** Pies de página fijos que usan scroll padding para mantener visibles los ítems enfocados; diálogos modales de cookies que impiden el acceso a otros controles hasta ser cerrados; notificaciones que desaparecen al perder el foco sin ocultar otros controles.

### 2.4.13 Apariencia del foco (Nivel AAA)
**Qué pide:** Establece estándares mínimos de visibilidad y discernibilidad para los indicadores de foco de teclado (en relación con 2.4.7 Foco Visible, que solo exige que exista un indicador, y con 1.4.11 Contraste no textual). Se permiten distintas formas de indicador —se alienta el contorno sólido, aunque no es obligatorio— siempre que cumplan ciertos umbrales de tamaño y contraste.
**Por qué importa:** Beneficia a cualquier persona que dependa del teclado al hacer visualmente evidente el componente enfocado; a personas con limitaciones de atención, memoria a corto plazo o función ejecutiva, que ubican el foco más fácilmente; y de forma significativa a personas mayores y con baja visión que no pueden detectar cambios visuales sutiles.
**Cómo cumplirlo:**
- Usar un indicador de foco visible provisto por el autor.
- Crear un indicador de foco de dos colores para asegurar suficiente contraste con todos los componentes.
- Crear un indicador de foco fuerte dentro del propio componente.
**Ejemplos/notas:** Enlaces que muestran contornos de alto contraste al recibir foco; botones que muestran un contorno alrededor del texto al enfocarse; campos de texto que muestran límites indicando el estado de foco; botones de radio que muestran contornos señalando el input enfocado.

## 2.5 Modalidades de entrada

### 2.5.1 Gestos del puntero (Nivel A)
**Qué pide:** Que toda funcionalidad operada mediante gestos basados en trayectoria (como deslizar el dedo o trazar una forma) o gestos multipunto (como pellizcar con dos dedos o tocar con varios dedos a la vez) también pueda realizarse con un solo puntero y sin un trayecto específico (un toque, un clic o una pulsación larga), salvo que el gesto complejo sea esencial para la función (por ejemplo, firmar con el dedo). El criterio aplica solo a los gestos definidos por el autor del contenido, no a los gestos propios del sistema operativo, el navegador o la tecnología de asistencia.
**Por qué importa:** Beneficia a personas que no pueden realizar gestos precisos de trayectoria o multipunto por una discapacidad motriz, a quienes usan punteros alternativos (como punteros de cabeza) que solo permiten un punto de contacto, y a personas con discapacidades cognitivas o de aprendizaje que se benefician de interacciones simples y familiares en lugar de gestos personalizados.
**Cómo cumplirlo:**
- Ofrecer controles visibles (botones, enlaces) que logren el mismo resultado que el gesto.
- Permitir activar sliders o controles deslizantes con un solo punto de contacto.
- Evitar depender únicamente de gestos de trayectoria sin alternativa más simple.
**Ejemplos/notas:** Un mapa con zoom por pellizco/separación de dedos que también ofrece botones de más/menos; un carrusel de noticias que se desliza horizontalmente pero también tiene botones visibles de avanzar/retroceder.

### 2.5.2 Cancelación del puntero (Nivel A)
**Qué pide:** Evitar la activación accidental de funciones al usar punteros, exigiendo una de estas cuatro estrategias: (1) activar en el evento de "soltar" (up-event), lo que permite cancelar moviendo el puntero fuera del control antes de soltar; (2) ofrecer confirmación, deshacer o reversión para acciones complejas como arrastrar y soltar; (3) que el evento de "presionar" (down-event) dispare solo comportamientos reversibles o temporales (como un popup que desaparece al soltar); o (4) permitir activación en el down-event únicamente cuando sea esencial, como en la emulación de teclado o actividades que requieren precisión de tiempo real (un piano virtual, un simulador de tiro).
**Por qué importa:** Ayuda a todos los usuarios a recuperarse fácilmente de errores de puntería, especialmente a personas con discapacidades visuales, cognitivas y motrices, reduciendo el riesgo de activaciones accidentales y garantizando mecanismos de deshacer/abortar en controles complejos. También evita la desorientación por cambios de contexto inesperados durante la navegación.
**Cómo cumplirlo:**
- Usar controles nativos que se activan en el evento de soltar.
- Implementar la posibilidad de cancelar una acción de arrastrar y soltar devolviendo el elemento a su posición original.
- Usar eventos de activación independientes del dispositivo, como el evento `click` de JavaScript, que funciona igual para touch, mouse y teclado.
**Ejemplos/notas:** Elementos táctiles que se activan solo cuando el dedo se levanta dentro de los límites del control; interfaces de arrastrar y soltar (por ejemplo, para ordenar tarjetas) donde soltar fuera de la zona de destino revierte la acción.

### 2.5.3 Etiqueta en el nombre (Nivel A)
**Qué pide:** Que el texto visible que etiqueta un componente de interfaz esté también incluido en su nombre accesible (el nombre programático usado por tecnologías de asistencia), de modo que lo que se ve y lo que se "oye" o procesa coincidan.
**Por qué importa:** Beneficia a usuarios de entrada por voz, que navegan y activan controles diciendo en voz alta la etiqueta visible, y a usuarios de texto a voz, para quienes es más coherente que lo que escuchan coincida con lo que ven en pantalla.
**Cómo cumplirlo:**
- Incluir el texto de la etiqueta visible como parte del nombre accesible.
- Hacer coincidir el nombre accesible con la etiqueta visible (el nombre accesible puede ampliar la etiqueta, pero debe empezar por ella).
- Mantener el orden de las palabras consistente entre lo visible y lo programático.
- Evitar diferencias de nombre que impidan que los comandos de voz coincidan.
**Ejemplos/notas:** Un botón con etiqueta visible "Buscar" puede tener como nombre accesible "Buscar" o "Buscar un valor"; diferencias de mayúsculas o puntuación (como "Nombre:" vs. "nombre") son aceptables; una fórmula matemática como "A>B" debe conservarse igual en el nombre accesible en vez de deletrearse.

### 2.5.4 Activación por movimiento (Nivel A)
**Qué pide:** Que las funciones que se activan al mover el dispositivo (inclinarlo, agitarlo) o mediante gestos captados por cámaras o sensores también puedan operarse con componentes de interfaz convencionales, y que exista una forma de desactivar la activación por movimiento para evitar disparos accidentales. Se exceptúan los casos en que el movimiento es esencial para la función, como en una aplicación de podómetro.
**Por qué importa:** Ayuda a personas con limitaciones de movilidad que no pueden inclinar, agitar o gesticular con el dispositivo, y a quienes están en situaciones que impiden mover el dispositivo (por ejemplo, montado en una silla de ruedas), dándoles acceso mediante controles convencionales o tecnología de asistencia.
**Cómo cumplirlo:**
- Ofrecer controles de interfaz convencionales (botones, menús) junto con la activación por movimiento.
- Incluir una opción de configuración en la aplicación para desactivar funciones basadas en movimiento.
- Aprovechar ajustes a nivel de sistema operativo que permitan desactivar la actuación por movimiento.
**Ejemplos/notas:** Una app permite desactivar "agitar para deshacer"; navegación por inclinación acompañada de botones de navegación de página; paneo del dispositivo para ver fotos con controles alternativos disponibles.

### 2.5.5 Tamaño del objetivo (mejorado) (Nivel AAA)
**Qué pide:** Que los objetivos de puntero (botones, enlaces no embebidos en texto, controles) tengan al menos 44 por 44 píxeles CSS, salvo excepciones (enlaces en línea dentro de texto corrido, tamaños controlados por el agente de usuario, o cuando el tamaño particular es esencial para la presentación).
**Por qué importa:** El toque es un mecanismo de entrada de precisión gruesa: el dedo tapa la vista y carece del control fino de un mouse o lápiz óptico. Beneficia a usuarios de pantallas táctiles, personas con temblores en las manos u otras limitaciones de movilidad, personas que usan el dispositivo en entornos con vibración (como el transporte público), usuarios que operan con una sola mano o con dedos grandes/nudillos, y personas con baja visión que se benefician de objetivos más grandes y visibles.
**Cómo cumplirlo:**
- Usar CSS para garantizar que los objetivos midan al menos 44x44 píxeles CSS.
- Dar prioridad a tamaños mayores cuando el control se usa con frecuencia, es irreversible, está en el borde de la pantalla o forma parte de tareas secuenciales.
- Si hay múltiples objetivos que cumplen la misma función, basta con que uno tenga el tamaño mínimo.
- Asegurar que los enlaces embebidos en oraciones completas también cumplan el tamaño si constituyen el único contenido interactivo.
**Ejemplos/notas:** Botones con áreas táctiles de 44x44 px; enlaces dentro de un párrafo de texto corrido están exentos; notas al pie o íconos de ayuda incrustados en una oración también están exentos.

### 2.5.6 Mecanismos de entrada concurrentes (Nivel AAA)
**Qué pide:** Que el contenido no restrinja la interacción a un único mecanismo de entrada (teclado, mouse, lápiz óptico, pantalla táctil), permitiendo que los usuarios combinen y cambien entre distintos métodos según su preferencia o necesidad, salvo que la restricción sea esencial, necesaria por seguridad, o esté determinada por configuraciones del propio usuario.
**Por qué importa:** Permite a cada usuario interactuar mediante el método de entrada que prefiere o tiene disponible, cambiar de método sin perder funcionalidad, y agregar o quitar dispositivos de entrada según lo soporte el sistema operativo.
**Cómo cumplirlo:**
- Usar manejadores de eventos de alto nivel e independientes del dispositivo de entrada (como `focus`, `blur`, `click`) en JavaScript.
- Registrar simultáneamente manejadores para entrada de teclado y de puntero.
- Evitar bloquear o deshabilitar un tipo de entrada mientras otro está activo, salvo justificación esencial (por ejemplo, una app de mecanografía).
**Ejemplos/notas:** Un usuario con movilidad reducida conecta mouse y teclado a un celular con pantalla táctil y el contenido acepta los tres; alguien con temblores en las manos usa teclado y trackpad en una laptop táctil en vez de tocar la pantalla; un usuario abre un menú con el mouse y luego navega los ítems con las flechas del teclado.

### 2.5.7 Movimientos de arrastre (Nivel AA)
**Qué pide:** Que toda funcionalidad que dependa de movimientos de arrastre (drag and drop) tenga una alternativa operable con un solo puntero, sin necesidad de arrastrar. Arrastrar exige una secuencia de cuatro acciones precisas (tocar/hacer clic para establecer un punto de inicio, mantener presionado mientras se reposiciona el puntero, y soltar en el punto final), que muchos usuarios no pueden ejecutar con precisión.
**Por qué importa:** Beneficia a personas con discapacidades motrices que usan mouse, lápiz óptico o pantallas táctiles, así como a quienes usan trackballs, punteros de cabeza o sistemas de seguimiento ocular, permitiéndoles operar la interfaz sin necesitar la destreza que exige arrastrar.
**Cómo cumplirlo:**
- Ofrecer un método alternativo de un solo puntero (tocar/hacer clic sin arrastrar) para lograr el mismo resultado.
- Implementar la funcionalidad equivalente mediante otros componentes o patrones de interacción (botones de flecha, menús contextuales).
- Usar campos de entrada de texto como alternativa independiente del dispositivo (por ejemplo, un campo numérico en vez de un slider).
- Tener en cuenta que los gestos de trayectoria por sí solos no son una alternativa válida al arrastre.
**Ejemplos/notas:** Mapas que se pueden arrastrar pero también ofrecen botones direccionales; listas ordenables con botones de subir/bajar además del arrastre; tableros Kanban con arrastrar y soltar y alternativa de selección más botones de flecha; sliders de rango que permiten hacer clic en cualquier punto de la barra, no solo arrastrar.

### 2.5.8 Tamaño del objetivo (mínimo) (Nivel AA)
**Qué pide:** Que los controles interactivos tengan un tamaño mínimo de 24 por 24 píxeles CSS, o bien, si son más pequeños, que tengan suficiente espaciado entre sí (de forma que un círculo de 24 px de diámetro centrado en cada objetivo no se superponga con el de otro objetivo), salvo excepciones como enlaces en línea dentro de texto corrido.
**Por qué importa:** Ayuda a que los controles interactivos se puedan activar fácilmente sin disparar por error elementos adyacentes. Beneficia a personas con limitaciones de destreza y motricidad fina (temblores, espasticidad, cuadriplejia), a quienes usan dispositivos de entrada especializados menos precisos que un mouse o trackpad convencional, a usuarios de pantallas táctiles en general, a personas en entornos con vibración (transporte público), a quienes operan el dispositivo con una sola mano, y a personas con dedos grandes o movilidad limitada de dedos/nudillos.
**Cómo cumplirlo:**
- Usar propiedades CSS como `min-height` y `min-width` para asegurar el tamaño o el espaciado adecuado del contenedor del objetivo.
- Cumplir con al menos una de dos vías: tamaño mínimo de 24x24 px, o espaciado suficiente entre objetivos más pequeños.
- Verificar elementos como ítems de menú o íconos agrupados, que suelen fallar por falta de espaciado cuando son más chicos que el mínimo.
**Ejemplos/notas:** Tres botones de 24x24 px pasan automáticamente; botones de 20x20 px con 4 píxeles de separación entre ellos pasan por la excepción de espaciado; los mismos botones sin espaciado fallan; ítems de menú de 24 px de alto pasan, pero de 18 px apilados sin espacio fallan; los enlaces de texto en línea están exentos.
