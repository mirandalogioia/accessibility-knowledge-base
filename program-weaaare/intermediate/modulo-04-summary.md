---
title: "Módulo 4 — Formas de interacción y fundamentos de accesibilidad"
status: draft
source: "raw-inputs/modulo-04-raw.txt (audio de las lecciones, Carlos) + raw-inputs/modulo-04-contenido-escrito-raw.txt (texto escrito de la plataforma, transcrito de capturas)"
last_updated: 2026-10-31
---

# Módulo 4 — Formas de interacción y fundamentos de accesibilidad

Resumen consolidado del Módulo 4, que fusiona el video (Carlos recorre una tienda de ejemplo con cada forma de interacción) con el texto escrito de cada lección (tablas de criterios, "lo que no pide", prácticas y cuestionarios). Cubre las lecciones 4.1 a 4.6. La **tutoría en vivo del módulo 4** está en [`clase-05-summary.md`](clase-05-summary.md).

## Cómo leer este resumen

- **Este módulo es sobre todo de exploración de herramientas.** Lo central para el repo son (1) las definiciones de cada **criterio WCAG** y de las **barreras** que lo incumplen, y (2) **cómo usar cada herramienta** de prueba. Lo segundo vive en una guía propia: [`resources/herramientas-prueba-interaccion.md`](../../resources/herramientas-prueba-interaccion.md) (Mac, Windows, Linux, Android, iPhone/iPad).
- **Las misiones de la tienda "Mercado Verde" son prácticas hechas por la alumna** en su propia computadora (Luis, Ana, Óscar, Lucía). Aquí solo se resumen como contexto; lo que se retiene es el criterio y la barrera que ilustran.
- **Audio y texto se complementan, no se repiten.** El audio muestra cada barrera en la tienda y explica el porqué; el texto agrega, por criterio, la columna **"qué pide / lo que no pide"**, las tablas de herramientas por sistema operativo y los cuestionarios. Lo que dice una fuente y no la otra no es una contradicción. Solo se señalan conflictos reales con la WCAG (ver "Contraste con la WCAG").
- **Referencia de verdad para los criterios:** [`resources/wcag22-understanding/`](../../resources/wcag22-understanding/README.md) (operable, comprensible, robusto, perceptible).
- **Metodología del módulo (audio):** en cada lección se navega la tienda con una forma de interacción; cada vez que aparece una barrera se pausa y se analiza: **criterio WCAG, qué pide, a quién afecta, cómo se comprueba y lo que no pide** (donde "más errores se cometen, sobre todo al diseñar o auditar"). Todas las formas de interacción terminan haciendo al producto las mismas preguntas: *¿qué hay aquí? ¿qué es cada cosa? ¿en qué estado está? ¿qué puedo hacer con ella?*

## Mapa del módulo

| Lección | Tema | Criterios principales |
|---|---|---|
| 4.1 | Introducción: la tienda Mercado Verde y cómo son las prácticas | — |
| 4.2 | Teclado (1): llegar a las cosas | 2.4.3, 2.4.7, 2.4.1, 2.1.1, 2.1.2, 2.1.4 |
| 4.3 | Teclado (2): qué pasa cuando interactúas | 2.4.3, 3.2.1, 3.2.2 |
| 4.4 | Puntero y táctil | 2.5.2, 2.5.7, 2.5.1, 1.3.4, 1.4.13, 2.5.4 |
| 4.5 | Control por voz y pulsador (número inferido; el audio no la anuncia) | 2.5.3, 2.2.1, 2.2.2, 2.3.3, 2.3.1 |
| 4.6 | Lector de pantalla | 2.4.4, 2.4.9, 4.1.2, 1.3.1, 1.1.1, 1.3.2 (y 2.5.3) |

### Índice de criterios del módulo

| Criterio | Nivel | Lección | Resumen en `resources/` |
|---|---|---|---|
| 1.1.1 Contenido no textual | A | 4.6 | [01-perceivable](../../resources/wcag22-understanding/01-perceivable.md) |
| 1.3.1 Información y relaciones | A | 4.6 | 01-perceivable |
| 1.3.2 Secuencia con sentido | A | 4.6 | 01-perceivable |
| 1.3.4 Orientación | AA | 4.4 | 01-perceivable |
| 1.4.13 Contenido en hover o foco | AA | 4.4 | 01-perceivable |
| 2.1.1 Teclado | A | 4.2 | [02-operable](../../resources/wcag22-understanding/02-operable.md) |
| 2.1.2 Sin trampas de teclado | A | 4.2 | 02-operable |
| 2.1.4 Atajos de teclado de un solo carácter | A | 4.2 | 02-operable |
| 2.2.1 Tiempo ajustable | A | 4.5 | 02-operable |
| 2.2.2 Pausar, detener, ocultar | A | 4.5 | 02-operable |
| 2.3.1 Tres destellos o por debajo del umbral | A | 4.5 | 02-operable |
| 2.3.3 Animación provocada por interacciones | **AAA** | 4.5 | 02-operable |
| 2.4.1 Evitar bloques | A | 4.2 | 02-operable |
| 2.4.3 Orden del foco | A | 4.2, 4.3 | 02-operable |
| 2.4.4 Propósito del enlace (en contexto) | A | 4.6 | 02-operable |
| 2.4.7 Foco visible | AA | 4.2 | 02-operable |
| 2.4.9 Propósito del enlace (solo enlace) | **AAA** | 4.6 | 02-operable |
| 2.5.1 Gestos del puntero | A | 4.4 | 02-operable |
| 2.5.2 Cancelación del puntero | A | 4.4 | 02-operable |
| 2.5.3 Etiqueta en el nombre | A | 4.5, 4.6 | 02-operable |
| 2.5.4 Activación por movimiento | A | 4.4 | 02-operable |
| 2.5.7 Movimientos de arrastre | AA | 4.4 | 02-operable |
| 3.2.1 Al recibir el foco | A | 4.3 | [03-understandable](../../resources/wcag22-understanding/03-understandable.md) |
| 3.2.2 Al recibir entradas (en el módulo: "Al introducir datos") | A | 4.3 | 03-understandable |
| 4.1.2 Nombre, rol, valor (en el módulo: "Nombre, función y valor") | A | 4.6 | [04-robust](../../resources/wcag22-understanding/04-robust.md) |

Para cada criterio, la columna "Lo que no pide" del texto de la plataforma es la que evita auditar de más; está en las tablas de abajo.

---

## 4.1 — Introducción

- **Mercado Verde** es una tienda online de fruta y verdura hecha para el curso, con un e-commerce completo: buscador, landing, ofertas, parrilla de productos, fichas, cesta, selección de envío. **Con el ratón funciona bien**; las barreras aparecen al usarla como otra persona (solo teclado, temblor, móvil fijo en horizontal, lector de pantalla). También tiene cosas bien hechas a propósito, para distinguir lo que falla de lo que cumple.
- **Orden del módulo:** teclado (navegar, luego interactuar) → puntero y táctil → voz y pulsador → lector de pantalla (con VoiceOver; hay equivalencias con NVDA).
- **Cada práctica:** persona + objetivo + enlaces; hay que hacer la misión completa con la forma de interacción de esa persona y anotar dónde se atasca, se pierde o gasta más esfuerzo. El enunciado **no dice** dónde están las barreras ni qué criterio incumplen. Luego se responde con las mismas preguntas del video: qué le pasa y cuándo; qué criterio pide que no pase y qué **no** pide; cómo se comprobaría en otro producto; qué debería haber decidido el diseño.
- **Antes de empezar (texto):** usar Chrome en ordenador (Safari con ajuste de fábrica se salta los enlaces al pulsar Tab); la tienda no guarda nada fuera del navegador, la cuenta es de prueba y no pide contraseña (no escribir datos reales); al empezar de cero, aceptar cookies con el ratón.
- **Dirección de la tienda:** algunas prácticas usan `?reiniciar` (vuelve a estado inicial: cesta con tres productos, favoritos y pedidos vacíos, aviso de cookies) o variantes como `?salto=visible` (la versión "arreglada" de una lección anterior). Una variante queda activa en esa pestaña; se limpian con `?reiniciar`.

---

## 4.2 — Teclado (1): llegar a las cosas

**A quién afecta:** personas que solo pueden usar teclado o pulsador (discapacidad motriz, temblor, poca fuerza, lesión temporal). **Quien navega solo con teclado suele ver la página tal como se diseñó**; no es lo mismo que el usuario de lector de pantalla (que escucha). Cada parada de Tab cuesta para quien tiene temblor o usa un pulsador. Teclas básicas y cómo probarlas: ver [guía de herramientas § Teclado](../../resources/herramientas-prueba-interaccion.md#4-teclado).

### Criterios de la lección

| Criterio | Qué pide | Lo que no pide |
|---|---|---|
| **2.4.3 Orden del foco (A)** | Que el foco recorra la página en un orden que conserve el sentido de lo que ves | Un único orden correcto: varios órdenes pueden tener sentido |
| **2.4.7 Foco visible (AA)** | Que, al llegar con el teclado a un elemento, se vea dónde está el foco | Diseñar un foco propio: el contorno del navegador sirve si no lo quitas |
| **2.4.1 Saltar bloques (A)** | Una forma de saltarse lo que se repite en todas las páginas, como la cabecera | Un enlace de salto delante de cada bloque largo |
| **2.1.1 Teclado (A)** | Que cada tarea hecha con ratón se pueda hacer con teclado | Lo que depende del trazo de la mano (firmar, dibujar a mano alzada) |
| **2.1.2 Sin trampas de teclado (A)** | Que, si entras en algo con el teclado, puedas salir con el teclado | Que el foco nunca se quede dentro: una ventana abierta puede retenerlo si se cierra con Escape |
| **2.1.4 Atajos con una sola tecla (A)** | Que un atajo de una letra, número o signo se pueda desactivar, cambiar o limitar a cuando el foco está en ese componente | Nada sobre atajos con Ctrl, Alt o Cmd |

**Lo que decide el diseño en cada pantalla:** en qué orden se recorre, cómo se ve el foco, dónde está el enlace para saltar al contenido, cómo se llega con el teclado a cada cosa tocable y cómo se sale de cada ventana o panel.

### Barreras encontradas en la tienda (audio) y qué enseñan

| Barrera observada | Criterio | Qué enseña |
|---|---|---|
| Con Tab desde el inicio, el foco salta casi al final de la página (al campo de búsqueda/inputs) en vez de a "Productos" | **2.4.3** | El orden esperado es el lógico: de izquierda a derecha y de arriba abajo (en árabe, de derecha a izquierda). Se comprueba recorriendo con Tab. Hay excepciones (se verán en el módulo de componentes) pero la regla es respetar lo que espera la persona |
| Al seguir con Tab no se ve el foco en varios elementos | **2.4.7** | El resaltado debe estar en todos los elementos interactivos para que no se pierda quien navega con teclado |
| El menú "Productos" (elemento interactivo) no recibe foco; tampoco los favoritos; se puede añadir una card a la cesta pero no entrar a su ficha | **2.1.1** | Todo lo que se hace con ratón debe hacerse con teclado |
| Ocho Tab para pasar la cabecera, repetidos en todas las páginas | **2.4.1** | Debe existir un mecanismo para saltar bloques repetidos. Se resolvió con un botón/enlace **"Saltar al contenido principal"** oculto que aparece al recibir foco (primer Tab) |
| El botón de "Te ayudamos" (chat) es **el último** elemento de la página, después del footer | **2.4.3** | El orden debería ser más lógico (ej. tras el primer elemento de la navegación principal); aquí hay cierta subjetividad porque es un elemento de posición absoluta |
| Al abrir el chat con Intro el foco va al campo de texto | — (cumple) | Mover el foco a una posición lógica y esperable, sin perderlo, es correcto |
| Dentro del chat: Tab cicla y la X (arriba a la derecha) no es alcanzable; Escape no cierra | **2.1.2** | Trampa de teclado. **Un bucle de foco dentro de una ventana modal no es un incumplimiento** (se espera que quede atrapado; se ve en el módulo 5); lo que falla es no tener salida |
| La tecla **"/"** salta al buscador sin aviso y sin forma de desactivarla | **2.1.4** | Quien dicta por voz o roza una tecla por temblor, o tiene sus propias teclas rápidas, dispara acciones que no pidió. Opciones: **desactivar**, **cambiar por un atajo con meta-tecla** (Control, Alt, Command) o **que solo funcione con el foco en el elemento** |

### Foco nativo del navegador (audio)

- El navegador (*user agent*; en una app móvil, el sistema operativo) añade un **foco nativo** a botones, enlaces e inputs, que **no hace falta diseñar**; se adapta al fondo (ej. doble capa blanca y azul sobre una foto).
- Según el audio, si no se toca el estilo del foco nativo "siempre se cumple", aunque en una auditoría estricta el contraste del indicador parezca flojo; hay incumplimiento si el foco se **corta o se pierde por mala implementación propia**. El texto de la plataforma coincide en que el contorno del navegador sirve si no se quita. (La responsabilidad según quién define el foco se aclaró en la tutoría; ver "Contraste con la WCAG".)

### Truco de depuración (ambas fuentes)

Para ver dónde está el foco aunque la página no lo muestre: Chrome > Inspeccionar > Consola > icono del ojo ("Crear expresión en directo") > `document.activeElement`. Ver [guía de herramientas § Chrome](../../resources/herramientas-prueba-interaccion.md#3-herramientas-de-chrome-y-edge).

### Cuestionario (lo que consolida)

- `outline: none` sin otro estilo → **2.4.7**. Treinta y cinco enlaces antes de cada noticia sin forma de saltarlos → **2.4.1**. Valoración por estrellas solo con clic → **2.1.1**. Vídeo incrustado de otra plataforma del que no se sale → **2.1.2** (está dentro de la página, también aplica).
- **Cumple:** un mapa donde el foco queda dentro pero un texto avisa "Pulsa Ctrl + M para salir" (2.1.2 permite una salida no estándar si la página dice cuál); ventana que retiene el foco y se cierra con Escape; atajo de una tecla (J) que solo funciona con foco en la lista de reproducción (2.1.4); firma dibujada con el dedo sin alternativa de teclado (excepción de 2.1.1 por depender del trazo).
- Atajo S sin ajuste para desactivarlo → **2.1.4**.

---

## 4.3 — Teclado (2): qué pasa cuando interactúas

**Idea central:** con el teclado **el foco es donde está la persona**. Con el ratón, si algo cambia en pantalla se mueve el puntero y se sigue; con el teclado se depende de que el foco siga en un sitio con sentido tras cada acción y de que **nada cambie sin haberlo pedido**. (El audio de esta lección aparece **duplicado** en la transcripción, de 29:49 a 42:55 y de 42:55 a 56:03.)

### Criterios de la lección

| Criterio | Qué pide | Lo que no pide |
|---|---|---|
| **2.4.3 Orden del foco (A)**, cuando la página cambia | Que, al borrar, abrir, cerrar o cambiar de paso, el foco vaya a un sitio con sentido y no se pierda | Que el foco no se mueva nunca: llevarlo al primer campo con error o al título del paso nuevo es moverlo bien |
| **3.2.1 Al recibir el foco (A)** | Que llegar a un elemento no cambie el contexto: no abrir ventanas, no navegar, no mover el foco, no enviar nada | Que no cambie nada: resaltar el campo o mostrar una ayuda junto a él está permitido |
| **3.2.2 Al introducir datos (A)** | Que cambiar un valor (elegir opción, marcar casilla, escribir) no cambie el contexto, salvo que se avise antes | Que la página se quede quieta: filtrar una lista en la misma página, sin sacar a la persona de donde está, está permitido |

El **orden de los campos de un formulario** también es 2.4.3: cuando el orden natural de lectura (izquierda→derecha, arriba→abajo) no coincide con el que tiene sentido para la tarea, manda el de la tarea (en un formulario de dos columnas, primero todos los datos de una y luego los de la otra). A nivel de código se puede lograr sin cambiar lo visual.

### Barreras en la tienda (audio)

| Barrera observada | Criterio | Qué enseña |
|---|---|---|
| Al eliminar una línea de la cesta (pan de masa madre), el foco desaparece y el siguiente Tab vuelve al inicio de la página | **2.4.3** | El elemento enfocado desapareció y nadie decidió adónde va el foco; el navegador lo manda al principio. Hay que repetir todo el recorrido para eliminar otra línea. Lo esperable: la línea anterior/siguiente o el título de la cesta |
| En el formulario de contacto vacío, al enviar el foco va al **primer campo con error** | — (cumple) | Es la forma correcta de mover el foco |
| En el pedido, el Tab pasa de **nombre → dirección → apellidos** | **2.4.3** | Orden natural ≠ orden lógico: no tiene sentido pedir nombre, luego dirección y volver a apellidos |
| Al llegar con Tab al **código postal** (sin escribir nada) se abre una ventana "¿recoger en tienda?" y el foco salta a ella | **3.2.1** | Cambio de contexto sorpresivo; desorienta a quien usa teclado, lector o ampliador. Debería ser una opción elegida (una casilla o un botón al lado) |
| En los chips "Mostrar" (grupo tipo radio, se mueven con flechas), cambiar con la flecha recarga la lista y se pierde el foco | **3.2.2** ("caso especial") | Cambiar un valor cambia el contexto automáticamente y el foco se pierde. Debe avisarse antes o no cambiar el contexto |

**Decisión de diseño (audio):** para **cada acción que hace aparecer o desaparecer algo, hay que decidir dónde queda el foco**. Es algo que "se suele olvidar" y pesa mucho en la experiencia.

### Dónde va el foco: decisiones de diseño (texto)

| Cuando la persona... | El foco va a... |
|---|---|
| Elimina una línea de una lista | La línea siguiente, o el título de la lista si era la última |
| Envía un formulario con errores | El primer campo con error, con el error escrito junto a él |
| Pasa al siguiente paso de un proceso | El título del paso nuevo |
| Cierra una ventana o un panel | El botón que lo abrió |

### Cuestionario (lo que consolida)

- Borrar un correo y que el siguiente Tab lleve al principio → **2.4.3** (lo esperable es el mensaje siguiente). Al desmarcar/marcar «Con ascensor» la lista se repinta y el foco se pierde → **2.4.3** (filtrar en la misma página está permitido, pero el foco debe seguir en la casilla).
- Abrir una encuesta y mover el foco solo por llegar a «Mis tarjetas» → **3.2.1**. Recargar la página en otro idioma al elegir país en un desplegable sin avisar → **3.2.2** (con teclado cada flecha puede recargarla).
- **Cumple:** devolver el foco al botón que abrió una ventana (2.4.3); un calendario que se despliega junto al campo sin mover el foco ni abrir otra página (3.2.1); un texto que avisa "Al elegir un país, la página se cargará en su idioma" (3.2.2 permite el cambio si se avisa antes); rellenar campos de facturación al marcar «Usar la misma dirección» en la misma página (cambia contenido, no contexto); al pasar al paso 3 llevar el foco a su título «Pago» (2.4.3).

---

## 4.4 — Puntero y táctil

**A quién afecta:** un puntero es cualquier cosa con la que se señala (ratón, trackpad, dedo, lápiz, ratón de cabeza o de mirada). Quien tiene temblor, poca fuerza o poca precisión puede no poder **mantener pulsado, arrastrar sin soltar ni hacer gestos con varios dedos**. Diferencia con la lección de teclado: estas personas **sí usan puntero**, pero sin precisión. La pregunta de la lección: *¿lo que pide la página se puede hacer con un solo punto, un clic o un toque sencillo y sin precisión?*

### Criterios de la lección

| Criterio | Qué pide | Lo que no pide |
|---|---|---|
| **2.5.2 Cancelación del puntero (A)** | Que una acción no se haga al **pulsar** sino al **soltar**, de modo que si se sale del control antes de soltar no pase nada; o que se pueda deshacer | Que cambien los controles nativos (botones y enlaces del navegador ya actúan al soltar). Tampoco lo esencial hacer al pulsar, como las teclas de un piano |
| **2.5.7 Movimientos de arrastre (AA)** | Que todo lo que se hace arrastrando se pueda hacer también con **un solo puntero sin arrastrar**: un clic, un toque | Que se quite el arrastre. Y **no vale el teclado** como alternativa: tiene que ser con el puntero |
| **2.5.1 Gestos con el puntero (A)** | Que lo que se hace con varios dedos (pellizcar) o siguiendo un trazo (deslizar) se pueda hacer con un solo puntero y sin trazo | Que se quite el gesto. Tampoco cubre el zoom del navegador o del sistema, ni lo esencial (firmar) |
| **1.3.4 Orientación (AA)** | Que el contenido se vea y use en **vertical y horizontal**, sin obligar a girar el dispositivo | Un diseño distinto para cada orientación. Excepción si una es esencial (un piano, un cheque) |
| **1.4.13 Contenido al pasar el puntero o al recibir el foco (AA)** | Que lo que aparece al pasar el puntero o recibir el foco se pueda **cerrar sin moverlos** (Escape), se pueda **recorrer con el puntero sin que desaparezca** y **se quede hasta que se cierre** (o deje de ser válido) | Nada sobre el globo nativo del navegador (atributo `title`): lo controla el navegador |
| **2.5.4 Activación por movimiento (A)** | Que lo que se activa moviendo el dispositivo (agitar, inclinar) se pueda hacer también con un control, y que el movimiento se pueda desactivar | Nada sobre lo que mide el movimiento por naturaleza (un cuentapasos) |

**Decisiones de diseño (texto):** las acciones van **al soltar**; lo que borra algo tiene «Deshacer» o pide confirmación; lo que se arrastra o se pellizca tiene un botón o campo equivalente; las pantallas funcionan en ambas orientaciones, también con altura muy pequeña; la especificación de cada globo o menú dice **cómo se cierra y cuánto dura**.

### Barreras en la tienda (audio)

| Barrera observada | Criterio | Qué enseña |
|---|---|---|
| Con temblor simulado (Funkify), "eliminar" en la cesta se dispara **al pulsar**, sin posibilidad de cancelar | **2.5.2** | Con un botón nativo, si uno pulsa y arrastra fuera antes de soltar, la acción se cancela. Para acciones más delicadas conviene además modal/confirmación ("una confirmación nunca viene de más") |
| Slider de precio que solo responde al arrastre (hacer clic en un punto de la barra no hace nada) | **2.5.7** | El tirador mide 24×24 (válido para el tamaño del objetivo AA) pero arrastrar sigue siendo casi imposible con temblor. Solución simple: **clic en cualquier punto de la barra mueve el indicador**. Lo mismo vale para drag & drop; "sin reinventar la rueda" |
| En el móvil, la galería se desliza, pero hay miniaturas clicables | — (cumple) | Un gesto de trazo con alternativa de un toque cumple |
| El zoom de la imagen solo se hace pellizcando | **2.5.1** | No incumple por existir el pellizco sino por **no tener alternativa**: un botón de ampliar/lupa |
| En horizontal la web funciona, pero chat de ayuda y elementos sticky (cabecera + botón fijo abajo) dejan casi sin viewport; el header del chat con su cierre se pierde | **1.3.4** | La orientación horizontal se pensó para quien tiene el móvil fijo en una silla de ruedas. El viewport de altura mínima es donde más se falla. Solución: p. ej. **cabecera no sticky** con altura pequeña; no hace falta diseñar cada pantalla en horizontal, pero sí revisar los componentes problemáticos (modales, sticky, bottom sheets) y probar en producción. **No bloquear la orientación** (hay muchas apps nativas que lo hacen); única excepción: funcionalidad que requiera una orientación |
| Icono (i) "kilómetro cero" cuyo tooltip desaparece al mover el ratón hacia él (hay un hueco entre icono y globo); con el Zoom de macOS ni siquiera se puede leer | **1.4.13** | Se incumple si no se puede cerrar con Escape, si desaparece al pasar el puntero encima o si no persiste. Beneficia a quien usa ampliador o tiene poca precisión. **El diseño debe especificar** cómo funciona (p. ej. que no desaparezca a los 3 segundos por decisión del desarrollador) |

### Cuestionario (lo que consolida)

- Tarjetas que solo cambian de columna arrastrándolas → **2.5.7**; con menú «Mover a…» además → **cumple**. Mapa solo con pellizco → **2.5.1** (botones + y −); carrusel con deslizar y botones → **cumple**. «Comprar ahora» que confirma al tocar y no se puede anular → **2.5.2**; piano que suena al tocar → **cumple** (esencial). Agitar para deshacer sin botón ni ajuste → **2.5.4**; podómetro → **cumple**. Ayuda de un campo que se cierra a los 2 segundos con el puntero encima → **1.4.13**; icono con `title` → **cumple** (lo controla el navegador; aunque no sea buena idea porque no aparece con teclado ni en móvil).

---

## 4.5 — Control por voz y pulsador *(número inferido)*

**A quién afecta:** quien no puede usar las manos (lesión medular, ELA, amputación, dolor) usa **control por voz**: dice lo que quiere pulsar y el sistema lo pulsa. Quien tampoco puede hablar con claridad usa un **pulsador** (un único botón: cabeza, pie, soplido) mientras el sistema recorre la pantalla. A las dos **todo les lleva más tiempo**. Dos preguntas: *1) ¿lo que se ve se llama igual por dentro? (quien habla dice lo que ve) 2) ¿la página deja ir a su ritmo o pone un reloj / se mueve sola?* Instrucciones de cada sistema: [guía § Control por voz](../../resources/herramientas-prueba-interaccion.md#5-control-por-voz) y [§ Pulsador](../../resources/herramientas-prueba-interaccion.md#6-pulsador-control-por-botón).

### Criterios de la lección

| Criterio | Qué pide | Lo que no pide |
|---|---|---|
| **2.5.3 Etiqueta en el nombre (A)** | Que, si un control tiene texto visible, su **nombre accesible contenga ese texto**. Lo recomendable es que empiece por él | Que sea idéntico: se puede añadir contexto detrás («Añadir naranjas de zumo a la cesta»). No aplica a **iconos sin texto**; su problema es no tener nombre (otro criterio, **4.1.2**) |
| **2.2.1 Tiempo ajustable (A)** | Ante cualquier límite de tiempo: poder **desactivarlo** antes de empezar, **ajustarlo a ≥10 veces** o recibir un **aviso con ≥20 s** para ampliarlo con una acción sencilla, ≥10 veces. Basta una de las tres | Que no haya límites. Quedan fuera los de **tiempo real** (subasta), los **esenciales** (examen cronometrado) y los de **más de 20 horas** |
| **2.2.2 Pausar, detener, ocultar (A)** | Que lo que se mueve, parpadea o se desplaza solo durante **más de 5 s**, junto a otro contenido, se pueda pausar, detener u ocultar. Lo que se actualiza solo (cuenta atrás) también, o poder elegir cada cuánto cambia | Quitar el movimiento ni parar lo esencial. Una animación de carga mientras no se puede hacer nada no entra |
| **2.3.3 Animación por interacción (AAA)** | Que la animación de movimiento provocada por una interacción (deslizamiento al pulsar una flecha) se pueda **desactivar**, salvo que sea esencial | Es **AAA** (no entra en auditoría AA). No cubre cambios de color u opacidad |
| **2.3.1 Tres destellos o por debajo del umbral (A)** | Que nada destelle más de **3 veces por segundo**, o que los destellos queden por debajo de los umbrales de tamaño y contraste | Movimiento en general: habla solo de destellos (epilepsia fotosensible) |

**Decisiones de diseño (texto):** el nombre de cada botón **empieza por la palabra visible** y el contexto extra va detrás; si un proceso tiene reloj, el diseño dice cómo se avisa antes de que acabe, cómo se pide más tiempo con una sola acción y qué pasa con lo ya escrito; si un carrusel avanza solo, lleva botón de pausa visible y fácil de alcanzar (y conviene preguntarse si una cuenta atrás aporta algo); en el traspaso queda escrito qué hace cada animación cuando el sistema pide menos movimiento.

### Barreras en la tienda (audio)

| Barrera observada | Criterio | Qué enseña |
|---|---|---|
| Botón visible «**Añadir**» cuyo nombre accesible es «**Comprar**»: "hacer clic en Añadir" no hace nada; solo "mostrar nombres" revela que se llama Comprar | **2.5.3** | **Lo que se ve debe ser coherente con lo que es.** Si el nombre accesible incluye la palabra visible («Añadir naranjas de zumo») cumple y además informa mejor al lector; **no vale sustituirla** («Comprar»). En iconos sin texto, el nombre es la acción funcional (visto con Consuelo) y quien usa voz tiene que mostrar nombres o números |
| En "Tramitar pedido", un temporizador de reserva (1 min en la demo; 3 min en la tienda) sin aviso, sin opción de ampliar ni desactivar; con pulsador no alcanza ni a escribir un carácter y el formulario se vacía | **2.2.1** | Se debe poder desactivar antes de empezar, ajustar ≥10 veces (si la base son 10 minutos, 100 minutos ≈ 1 h 40) o recibir aviso con ≥20 s. **Toasts con «Deshacer» que desaparecen solos a los 5 s** también incumplen cuando esa acción no está en otra parte; en cambio un toast "Correo enviado" cumple porque se puede comprobar en otro lugar (Enviados) |
| Carrusel de portada que avanza solo, sin pausa; con pulsador se escapa antes de poder actuar | **2.2.2** | Todo lo que se mueve solo necesita pausa. Beneficia también a personas con déficit de atención, mareos o náuseas |
| El carrusel sigue moviéndose con "Reducir movimiento" activado en el sistema | **2.3.3** (AAA) | Una línea de código para escuchar la preferencia del sistema (`prefers-reduced-motion`) y desactivar animaciones; el carrusel no es esencial. No se exige en una auditoría AA, pero es barato y conviene dejarlo como nota para desarrollo |

### Cuestionario (lo que consolida)

- Botón «Enviar» con nombre «Mandar solicitud» → **2.5.3** (quien dice «Hacer clic en Enviar» no obtiene respuesta). **Cumple:** «Leer más sobre…» + título; lupa sin texto llamada «Buscar» (2.5.3 solo aplica a controles con texto visible).
- Sesión de banco que caduca a los 5 min sin aviso → **2.2.1**; aviso 1 min antes con «Necesito más tiempo» enfocado y ampliable sin límite → **cumple**; subasta con hora fija igual para todos → **cumple** (tiempo real).
- Franja de logotipos que se desplaza sin parar junto al texto → **2.2.2**; círculo de carga mientras se procesa un pago → **cumple**. Parallax con «Reducir movimiento» activado → **2.3.3**.

---

## 4.6 — Lector de pantalla

**A quién afecta:** sobre todo personas ciegas; también baja visión con fatiga de lectura (prefieren escuchar), dificultades de lectura y sordociegas (línea braille). **No ve la página: la escucha, y no de arriba abajo**: usa el **rotor** (VoiceOver) o la lista de elementos (NVDA) para saltar por listas que el lector construye a partir del **código** (enlaces, encabezados, controles de formulario, regiones). En cada parada el lector dice **nombre, rol y, a veces, estado** («Productos, contraído, botón»): si falta el nombre o no dice nada, la persona no sabe qué tiene delante. Lectores por sistema, atajos y cómo instalarlos: [guía § Lectores de pantalla](../../resources/herramientas-prueba-interaccion.md#9-lectores-de-pantalla).

> Diseño: el lector de pantalla **también es una experiencia de usuario**. El diseñador tiene la responsabilidad de dejar escrito en el traspaso (*handoff*) lo que las personas oyen.

### Criterios de la lección

| Criterio | Qué pide | Lo que no pide |
|---|---|---|
| **2.4.4 Propósito de los enlaces, en contexto (A)** | Que se entienda adónde lleva cada enlace por su texto, **o por su texto junto con su contexto** (misma frase, párrafo, elemento de lista o celda) | No prohíbe textos cortos ni repetidos («Ver grabación» en cada tarjeta) si el contexto los explica. Solo aplica a enlaces |
| **2.4.9 Propósito de los enlaces, solo enlaces (AAA)** | Que el texto del enlace diga **por sí solo** adónde lleva («Ver grabación de la masterclass…») | Es **AAA** (no entra en AA). Un plus para quien repasa la lista de enlaces |
| **4.1.2 Nombre, función y valor (A)** | Que cada control exponga **nombre, función (botón, enlace, casilla) y estado o valor**, y avise cuando cambian | No juzga si el nombre es bueno: un enlace llamado «3» cumple 4.1.2 aunque falle 2.4.4 |
| **1.3.1 Información y relaciones (A)** | Que lo que se entiende mirando esté también en el código: títulos y su nivel, listas, regiones, precio tachado | No pide ARIA (basta HTML: `h1`, `ul`, `header`, `nav`, `main`, `footer`). No juzga si un título está bien escrito |
| **1.1.1 Contenido no textual (A)** | Que cada imagen tenga alternativa en texto que cumpla su función, o se marque decorativa para que el lector la salte. El nombre del archivo no es alternativa | Describir todas las imágenes: si una foto no añade nada al nombre del producto, lo correcto es **decorativa** |
| **1.3.2 Secuencia con sentido (A)** | Que, si el orden de lectura cambia el significado, el código tenga el orden correcto | Que todo se lea igual que se ve: leer el descuento antes que el nombre confunde, pero si el sentido no cambia, es buena práctica, no fallo |

**Diferencia 4.1.2 vs 2.4.4 (audio):** 4.1.2 es **técnico** ("¿el control tiene nombre y se lo pasa a la tecnología de apoyo? sí/no") y vale para **cualquier** control; 2.4.4 va un paso más y solo es para **enlaces**: ¿se entiende su propósito? Un enlace «3» cumple 4.1.2 y falla 2.4.4; un botón solo «botón», sin nombre, falla 4.1.2.

**Decisiones de diseño en el traspaso (texto):** cada icono-botón lleva su **acción** como nombre («Buscar»); cada icono-enlace, **adónde lleva** («Cesta, 3 productos», «Mi cuenta»); en cada pantalla se marcan los **títulos y su nivel** (también los que no lo parecen y los que solo oye el lector, como un título principal oculto); se anotan las **regiones** (cabecera, navegación —con nombre si hay varias—, búsqueda, contenido principal y pie); en las tarjetas se decide el **orden de lectura** (nombre primero) y que el **precio anterior** se diga en texto y no solo tachado.

### Barreras en la tienda (audio)

| Lo que dice el lector | Criterio | Corrección |
|---|---|---|
| Botón de la lupa: «botón» (sin nombre) | **4.1.2** | Nombre = acción: «**Buscar**» (no «lupa») |
| «Cuenta HTML» y enlace «tres» | **2.4.4** | «Mi cuenta»/«Perfil» y «**Cesta, 3 productos**» (con esto, además, cumple el plus AAA **2.4.9**) |
| `Productos, contraído, botón` | — (bien) | Muestra **nombre + rol + estado**; es el patrón a esperar |
| Rotor de enlaces: varios «Ver grabación» (tarjetas de la web de weAAAre) | cumple 2.4.4 en contexto; 2.4.9 (AAA) pide más | Cada enlace puede tener nombre accesible más largo («Ver grabación de la masterclass…»); en el rotor se ve ese nombre completo |
| Rotor de encabezados: solo 3 (H2 «Ofertas de la semana», H3 «de temporada», H3 «23 cuartas») aunque visualmente hay más secciones | **1.3.1** | Marcar como encabezados las secciones con "peso de capítulo" (destacados, ofertas, productos de cada oferta). Ver estructura propuesta abajo |
| Rotor de puntos de referencia: vacío | **1.3.1** | Añadir regiones (ver abajo) |
| Imagen leída como «naranjas-zumo.jpg, imagen» | **1.1.1** | Marcarla decorativa (o informativa si aporta, ej. «caja de naranjas»); el audio la considera **decorativa** |
| Card: lee «-18% eco kilómetro cero» sin contexto | **1.3.1** | Convertir en **lista de etiquetas**: «Descuento del 18%», «Ecológico», «Kilómetro cero» |
| El título «Naranjas de zumo» no es enlace | **4.1.2 / 2.1.1 / 2.4.4** (el audio dice "otro incumplimiento", sin criterio) | El **título** es un encabezado H3 y a la vez un **enlace** a la ficha (doble semántica compatible) |
| Precios «11,40 € 9,40 €» sin indicar cuál es el anterior (visualmente uno está tachado) | **1.3.1** | «Precio anterior 11,40 €. Ahora 9,40 €» |
| Botón «Añadir» con nombre «Comprar» | **2.5.3** | «Añadir naranjas de zumo» (contiene «Añadir») |
| Orden: `-18%` antes del nombre | **1.3.2** (buena práctica) | Cambiar el **orden de lectura** (no el de foco) para que el nombre vaya primero |

**Estructura de encabezados propuesta (audio):** H1 oculto con el título de la página («Mercado Verde, fruta, verdura y despensa de la huerta»; el carrusel no puede ser H1: es una sección de destacados); sección oculta **«Destacados» (H2)** con los elementos del carrusel como **H3** (mismo nivel de importancia que «Ofertas de la semana», H2); las cuatro cards de ofertas como **H3**; «Cesta de temporada» y «Huertas» como H2, etc. Un H1 que no se ve visualmente es válido cuando visualmente y conceptualmente el contexto se entiende pero un lector no tiene cómo ubicarse; es un caso extremo, **no la norma**. Si hay dudas entre H2 o H3, entra la subjetividad de experiencia de usuario más que un criterio.

**Regiones (puntos de referencia) — cómo identificarlas (audio):**

| Región | Qué es |
|---|---|
| `header` (el lector dice **banner**) | Lo de arriba que se repite |
| `nav` | Navegación. Puede haber varias; **si hay varias hay que darles nombre accesible** (ej. «Principal»). En la web de la Sagrada Familia el rotor mostraba ocho «navegación» sin nombre |
| búsqueda | Región de búsqueda |
| `main` | El contenido: *quita header y footer y lo que queda es el main* |
| `footer` | Pie de página |
| `aside` (complementario) | p. ej. filtros laterales |
| sección / región | Con nombre accesible, si tiene mucha importancia |

Método del audio: **primero** header, **luego** footer, **lo que queda** es main, **después** localizar navegaciones (nombrarlas si hay más de una) y por último complementarios y regiones relevantes. Header, main y footer: la opinión de Carlos es que deben ser **únicos por página** (admite que hay discusión en la comunidad); `nav` puede repetirse. Los puntos de referencia permiten saltar rápido, p. ej. directo al pie, sin recorrer todo el menú.

**Nombre, rol y estado** (concepto que se profundiza en el módulo de componentes): rol = función del elemento; nombre = nombre accesible; estado = ej. contraído/expandido. En el audio el lector anuncia primero el rol y luego el nombre.

**Alt informativo vs decorativo (audio, con la card de naranjas):** las tres tipologías (informativa, decorativa, funcional) ya vistas con la profesora; el criterio del alt informativo es ser **concreto** y mencionar solo la información adicional que aporta. Si la imagen no aporta más que el título, es decorativa. Y **no hace falta crear nombres accesibles para todo lo visual**: normalmente lo visual basta; el sobre-contexto es una buena práctica para pequeños detalles, no un criterio obligatorio.

### Cuestionario (lo que consolida)

- Aspa sin texto leída como «botón» → **4.1.2** (nombre: «Cerrar aviso»). Diez «Haz clic aquí» al final de un párrafo que no dice adónde llevan → **2.4.4**. Títulos que son párrafos en negrita (el rotor no encuentra encabezados) → **1.3.1**. Gráfico leído como «grafico-ventas-final2.png» → **1.1.1**. Casilla «Acepto las condiciones» sin decir si está marcada → **4.1.2** (falta estado).
- **Cumple:** «Leer más» dentro del mismo elemento de lista que el título (2.4.4; para 2.4.9 tendría que decirlo solo); web con cabecera, menú, contenido y pie marcados y dos navegaciones con nombres «Principal» y «Pie» (1.3.1 y ayuda a orientarse); foto de producto decorativa porque el nombre está al lado (1.1.1).

---

## Contraste con la WCAG

Puntos del módulo comparados con [`resources/wcag22-understanding/`](../../resources/wcag22-understanding/README.md) (que se toma como verdad). El cuerpo del resumen ya refleja lo que coincide.

- **2.4.7 y el foco nativo (resuelto en la tutoría):** el audio dice que, si no se toca el estilo del foco nativo, "siempre se cumple" aunque el contraste parezca flojo. La referencia (1.4.11) exige 3:1 al indicador de foco, pero **no aplica a presentaciones que determina el agente de usuario fuera del control del autor**. Es decir, el foco nativo **sin modificar** no es responsabilidad del diseño; si se **personaliza**, sí hay que cumplir 3:1 (ver [`clase-05-summary.md`](clase-05-summary.md)).
- **2.5.3 "debe empezar":** el texto de la plataforma y el audio dicen "lo recomendable/mejor si empieza" por el texto visible; la referencia indica que el nombre accesible "puede ampliar la etiqueta, pero **debe empezar por ella**". Criterio práctico seguro: que **empiece** por el texto visible.
- **2.2.2 y sus excepciones:** el audio dice que se puede omitir la pausa si "no está en loop, no empieza automáticamente **y** dura menos de 5 segundos". La referencia da como excepciones **dura menos de 5 segundos** o **es parte de una actividad esencial**, y el texto de la plataforma agrega que el criterio aplica al movimiento que dura más de 5 s **junto a otro contenido**; los indicadores de carga que son el único contenido visible no necesitan controles.
- **Nombre del criterio 3.2.2:** el módulo lo llama "Al introducir datos"; en `resources/` se llama "Al recibir entradas". Mismo criterio. Igual 4.1.2: "Nombre, función y valor" (módulo) / "Nombre, rol, valor" (`resources/`).
- **Orden del foco al borrar o cambiar contenido:** la referencia de 2.4.3 no menciona literalmente los casos de borrar una línea o cambiar de paso; la lección los incluye como parte de 2.4.3 (el foco debe ir a un sitio con sentido). Se mantiene tal cual está en la lección.
- **Título del enlace «Naranjas de zumo» sin semántica de enlace:** el audio lo califica como "otro incumplimiento" sin nombrar criterio; el más cercano es 4.1.2 (rol) / 2.1.1 (no operable por teclado).

## Notas de transcripción (audio)

- «Wispr», «Wiccard» = **WCAG**; «JOS» = **JAWS**; «Tolba» = **TalkBack**; «FunkyFi» = **Funkify**; «Max» = **Mac**; «Nintendo» (en "por si tenéis Nintendo") = **Windows**; «aside» aparece como «a side»; «toas» = **toast**; «hanof/hanos» = **handoff**; «encabezamientos» = **encabezados**; «cuenta HTML» y «tres» son los nombres accesibles malos del ejemplo; «la página de War» = la plataforma weAAAre.
- Slips de numeración del audio: «2.1.2.2.1» = **2.2.1**; «1311» = **1.3.1**; «244» = **2.4.4**; «412» = **4.1.2**. Frases como «no itens en menú puntos de referencia» y «visitado, enlace» son salidas del propio VoiceOver captadas por el micrófono.
- La lección 4.3 aparece **duplicada** en la transcripción (29:49–42:55 y 42:55–56:03). La lección de voz y pulsador no se anuncia con número (se infiere 4.5).
- El audio llama "botón" y "enlace" indistintamente al elemento "Saltar al contenido principal" (en 4.6 el lector lo dice como botón).

## Pendiente

- La **tutoría del módulo 4** quedó registrada como [`clase-05-summary.md`](clase-05-summary.md) (raw: `raw-inputs/clase-05-raw.txt`).
- Completar la guía de herramientas con Linux (Orca) y otros sistemas si los módulos siguientes lo cubren.
- Los recursos citados que no tienen resumen propio en `resources/` (Funkify, NV Access): el texto de la plataforma los enlaza pero las URL no estaban visibles en las capturas.
