---
title: "Guía de herramientas para probar formas de interacción (teclado, puntero, voz, pulsador, lector de pantalla)"
status: in_progress
last_updated: 2026-10-31
---

# Guía de herramientas para probar formas de interacción

Cómo encender y usar cada herramienta con la que el **Módulo 4 de weAAAre** ("Formas de interacción y fundamentos de accesibilidad") simula cómo usan un producto digital distintas personas. Fuentes: el audio de las lecciones (Carlos, demos en Mac) y el texto escrito de la plataforma (que agrega Windows, Android, iPhone/iPad y Linux). Resumen del módulo en [`program-weaaare/intermediate/modulo-04-summary.md`](../program-weaaare/intermediate/modulo-04-summary.md).

**Importante:** son **simulaciones didácticas**. Sirven para detectar barreras y entender el esfuerzo que implican, pero quedan lejos de la experiencia real de quien usa esas tecnologías a diario. No reemplazan el testeo con personas con discapacidad.

## 1. Quién usa qué (para no mezclar formas de interacción)

| Forma de interacción | Quién la usa | Cómo percibe la página | Idea clave |
|---|---|---|---|
| **Solo teclado** | Personas con discapacidad motriz que no pueden usar ratón (temblor, poca fuerza, lesión temporal) | **Ve** la página tal como se diseñó | Necesita llegar a cada elemento interactivo, saber dónde está (foco) y activarlo |
| **Lector de pantalla** | Personas ciegas; baja visión con fatiga de lectura; dificultades de lectura; sordociegas (con línea braille) | **Escucha** (o lee en braille); no ve la página | Usa teclado **y** sonido; no navega de forma lineal (rotor, atajos) |
| **Puntero con poca precisión** | Temblor, poca fuerza, poca precisión; ratón de cabeza o de mirada; lápiz; un solo dedo | Ve la página | Todo debe poder hacerse con **un solo punto**: clics o toques sueltos, sin precisión |
| **Control por voz** | Quien no puede usar las manos (lesión medular, ELA, amputación, dolor) | Ve la página | "Dice lo que ve": el nombre accesible debe contener el texto visible |
| **Pulsador (control por botón)** | Quien tampoco puede hablar con claridad; un único botón (cabeza, pie, soplido) | Ve la página | El sistema recorre la pantalla y se pulsa al llegar; todo lleva mucho más tiempo |
| **Ampliador de pantalla** | Baja visión | Ve una porción pequeña de la pantalla | Lo que aparece al pasar el puntero o al recibir el foco debe poder leerse |

El módulo remarca el error frecuente de mezclar **solo teclado** con **lector de pantalla**: son personas y necesidades distintas. Las demás tecnologías de apoyo (voz, pulsador, soplido, mirada…) en última instancia dependen del teclado; por eso probar con teclado y lector de pantalla cubre mucho (idea de la Clase 4).

## 2. Cobertura por sistema operativo

| Herramienta | Mac | Windows | Linux | Android | iPhone / iPad |
|---|---|---|---|---|---|
| Teclado (Chrome, Edge, Firefox) | Sí | Sí | Sí ("funciona igual" según las prácticas) | — | — |
| Control por voz | Control por voz | Acceso por voz (Win 11 22H2+) | No cubierto | Voice Access | No cubierto |
| Control por botón (pulsador) | Control por botón | Solo aproximación con teclado en pantalla | No cubierto | Accesibilidad con interruptores | Control por botón |
| Ampliador | Zoom | Lupa | No cubierto | No cubierto | No cubierto |
| Reducir movimiento | Sí | Sí | No cubierto | No cubierto | No cubierto |
| Lector de pantalla | VoiceOver, **Control** | NVDA, JAWS, Narrador | Orca | TalkBack | VoiceOver |

"No cubierto" = el módulo no da instrucciones; no significa que no exista. Para **Linux** solo aparece: las prácticas de teclado funcionan igual en Linux y el lector de pantalla del sistema es **Orca** (no hay teclas ni pasos). Se completará si los módulos siguientes lo tratan.

## 3. Herramientas de Chrome (y Edge)

Útiles en cualquier sistema.

| Para... | Cómo |
|---|---|
| Abrir las herramientas para desarrolladores | Clic derecho > **Inspeccionar**; o **Cmd + Opción + I** (Mac) / **Ctrl + Mayús + I** (Windows) |
| **Ver dónde está el foco** aunque la página no lo muestre | Pestaña **Consola** > icono del ojo (**Crear expresión en directo**) > escribir `document.activeElement`. Al pulsar Tab muestra el elemento con foco; al pasar el ratón por encima lo resalta en la página |
| **Ver el nombre accesible y la función** de un elemento | Clic derecho en el control > Inspeccionar > pestaña **Accessibility** > *Name* (sirve para comparar lo que se ve con el nombre, si el sistema no muestra los nombres o no puedes hablarle al ordenador) |
| Simular **móvil / táctil** | Con las herramientas abiertas, **Cmd + Mayús + M** (Mac) / **Ctrl + Mayús + M** (Windows) y elegir un teléfono. El ratón hace de dedo; **Mayús + arrastrar** simula el pellizco; el botón de girar de la barra cambia la orientación |
| **Zoom del navegador** | Cmd/Ctrl + `+`, `-`, `0` (ver Clase 4) |
| **Simular temblor** | Extensión **Funkify** (perfil "Trembling Trevor"): hace temblar el puntero |

Navegador: usar **Chrome** en ordenador (el de los videos). **Safari**, con su ajuste de fábrica, se salta los enlaces al pulsar Tab, así que recorre la página de otra forma. Las prácticas también valen en Edge o Firefox.

## 4. Teclado

| Tecla | Qué hace |
|---|---|
| **Tab** | Avanza al siguiente elemento interactivo |
| **Mayús + Tab** | Retrocede al elemento interactivo anterior |
| **Intro (Enter)** | Activa un enlace o un botón |
| **Espacio** | Activa un botón o marca una casilla |
| **Flechas** | Mueven dentro de un componente de grupo (opciones tipo radio o chips, menús, pestañas); arriba/abajo también hacen scroll de la página |
| **Escape** | Cierra (ventana modal, menú, contenido emergente) |

- Solo los elementos **interactivos** reciben foco (enlaces, botones, controles de formulario); no los títulos, párrafos ni imágenes.
- Cada pulsación de Tab cuesta para quien tiene temblor o usa un pulsador.
- Probar con el teclado "como lo haría otra persona": el ratón puede funcionar perfecto y el teclado no.

## 5. Control por voz

Idea: la persona dice **lo que ve en pantalla** y el sistema pulsa. Tres ideas comunes: pulsar algo diciendo lo que pone, pedir números cuando no sabes qué decir y ver cómo se llama cada control por dentro.

| Sistema | Dónde se activa |
|---|---|
| **Mac** — Control por voz | Ajustes del Sistema > Accesibilidad > Control por voz |
| **Windows 11** — Acceso por voz | Configuración > Accesibilidad > Voz > Acceso por voz (desde 22H2; entiende español; funciona sin conexión) |
| **Android** — Voice Access | Se descarga gratis de Google Play; se enciende en Ajustes > Accesibilidad > Voice Access |

| Para... | Mac | Windows 11 | Android |
|---|---|---|---|
| Pulsar algo por lo que pone | «Hacer clic en Añadir» | «Hacer clic en Añadir» o «Pulsar Añadir» | «Tocar Añadir», o solo «Añadir» |
| Poner un número en cada control | «Mostrar números» | «Mostrar números» | «Mostrar números» |
| Ver cómo se llama cada control | «Mostrar nombres» | No tiene esta orden | «Mostrar etiquetas» |
| Apuntar a una zona de la pantalla | «Mostrar cuadrícula» | «Mostrar cuadrícula» | «Mostrar la cuadrícula» |
| Saber qué puedes decir | «Mostrar comandos» | «¿Qué puedo decir?» | «Mostrar todos los comandos» |

Notas de la demo en Mac (audio):
- "Mostrar números" y "Mostrar nombres" alternan el modo; quienes lo usan a diario suelen tener los nombres **ocultos** (la pantalla llena de rótulos es caótica). También se usa "desplazar abajo".
- Si la acción no responde ("hacer clic en Añadir" no hace nada), **mostrar nombres** revela el nombre accesible real (ej. el botón decía «Añadir» y por dentro se llamaba «Comprar»).
- Con varios controles con el mismo nombre, el sistema asigna **números** para elegir ("uno").
- A veces la pantalla se actualiza y los nombres no se refrescan al instante: volver a decir "mostrar nombres".
- Criterio relacionado: **2.5.3 Etiqueta en el nombre**.

## 6. Pulsador (control por botón)

Un control por botón recorre la pantalla resaltando un elemento o una zona cada vez; la persona pulsa cuando llega a lo que quiere. No hace falta pulsador real: casi todos los sistemas permiten usar una **tecla como botón**.

| Para... | Mac | iPhone y iPad | Android | Windows |
|---|---|---|---|---|
| Encenderlo | Accesibilidad > Control por botón | Ajustes > Accesibilidad > Control por botón | Ajustes > Accesibilidad > Accesibilidad con interruptores | Configuración > Accesibilidad > Teclado > Teclado en pantalla > Opciones > **Examinar las teclas** |
| Qué sirve de botón | Una tecla o un pulsador | Pulsador externo, pantalla entera, un sonido o movimiento de cabeza ante la cámara | Teclas de un teclado USB/Bluetooth, un pulsador, gestos de la cara ante la cámara | Una tecla, un mando o un clic |
| Qué recorre | Elementos de la pantalla, o la pantalla con dos líneas | Elementos de la pantalla | Elementos de la pantalla | Solo las teclas del teclado en pantalla |

- **Mac (demo del audio):** se usó la **barra espaciadora** como botón. En el panel **Puntero** se elige **«Mover y hacer clic»**: una línea vertical barre la pantalla (se pulsa para fijarla), luego una horizontal (se pulsa otra vez) y una última pulsación hace el clic. Es lento por diseño.
- **Windows:** no hay control por botón de sistema. El teclado en pantalla con "Examinar las teclas" sirve para notar la lentitud y cómo aprieta un reloj; con él se pulsa Tab, Intro o Espacio y se recorre la web como con el teclado, pero **no llega** a lo que el teclado no alcanza (ej. elementos hechos con `div`). Para un control por botón completo hacen falta programas de terceros.
- Medir **cuánto tardas** en cada tarea con voz o botón: es la mejor forma de entender por qué un temporizador de uno o tres minutos no deja terminar. Criterios: **2.2.1**, **2.2.2**.

## 7. Menos movimiento (preferencia del sistema)

| Sistema | Dónde |
|---|---|
| Mac | Ajustes del Sistema > Accesibilidad > Movimiento > **Reducir movimiento** |
| Windows 11 | Configuración > Accesibilidad > Efectos visuales > **Efectos de animación**, desactivado |

Una página que escucha esta preferencia deja de deslizar, de hacer zoom o de moverse sola (técnica: `prefers-reduced-motion`). Criterio: **2.3.3 (AAA)**; según el audio es "una línea de código", barato de implementar y conviene dejarlo escrito en el traspaso.

## 8. Ampliador de pantalla

| Sistema | Cómo |
|---|---|
| **Mac — Zoom** | Ajustes del Sistema > Accesibilidad > Zoom; activar los atajos y encender con **Opción + Cmd + 8**. Se amplía/reduce y se mueve por la pantalla acercando el puntero a las esquinas |
| **Windows — Lupa** | Tecla **Windows + signo más** |

Con un ampliador solo se ve una porción de pantalla: sirve para comprobar que lo que aparece al pasar el puntero o al recibir el foco no desaparece ni queda fuera de vista. Criterio: **1.4.13**.

## 9. Lectores de pantalla

Un lector convierte la página en voz (o braille con línea braille). Dice, en cada parada, **cómo se llama** la cosa, **qué es** (rol) y a veces **cómo está** (estado): «Productos, contraído, botón». VoiceOver y NVDA construyen las mismas listas a partir del mismo código: lo que se oye con uno se oye, con otras palabras, con el otro.

| Lector | Sistema | Costo / notas |
|---|---|---|
| **VoiceOver** | Mac, iPhone, iPad | Incluido en el sistema |
| **NVDA** | Windows | Gratuito y de código abierto; habla en español |
| **JAWS** | Windows | De pago. En España la mayoría de las personas ciegas lo usan porque lo financia la ONCE; conviene probar con el lector que use tu público |
| **Narrador** | Windows | Viene con el sistema; poco usado convencionalmente |
| **TalkBack** | Android | Incluido en el sistema |
| **Orca** | Linux | Mencionado solo como el lector de Linux; el módulo no da instrucciones |

### VoiceOver en Mac

| Para... | Cómo |
|---|---|
| Encender / apagar | **Cmd + F5** |
| Callarlo en el momento | **Control** |
| Tecla VO | **Control + Opción** (casi todas las órdenes empiezan por ella) |
| Moverse al siguiente / anterior | **VO + flecha derecha / izquierda** (el audio lo muestra con Control + Opción + flechas) |
| Abrir el **rotor** | **VO + U**. Flechas derecha/izquierda cambian de lista (enlaces, encabezados, controles de formulario, puntos de referencia, ventanas); arriba/abajo la recorren; **Intro** va al elemento; **Escape** cierra |
| Pulsar lo que tienes delante | **VO + Espacio** |

### NVDA en Windows

1. Descargar desde la página de **NV Access** (propone donar; es opcional y se puede omitir).
2. Abrir el instalador (NVDA empieza a hablar al arrancar). Se puede **instalar** en el equipo o ejecutar una **copia temporal** sin instalar.
3. Al instalar se crea un atajo: **Control + Alt + N** lo arranca desde cualquier sitio.

- La **tecla NVDA** es **Insert** por defecto; si el portátil no la tiene, elegir **Bloq Mayús** en las opciones de teclado.
- En páginas web NVDA está en **modo exploración** (flechas leen la página; **una letra** salta al siguiente elemento de un tipo). Al llegar a un campo pasa a **modo foco** para escribir; **NVDA + Espacio** cambia de modo.

### La misma tarea con uno y con otro

| Para... | VoiceOver (Mac) | NVDA (Windows) |
|---|---|---|
| Encender el lector | Comando + F5 | Control + Alt + N |
| Callarlo un momento | Control | Control |
| Ir al elemento siguiente | VO + flecha derecha | Flecha abajo |
| Pulsar lo que tienes delante | VO + Espacio | Intro |
| Ver las listas de la página | VO + U, el rotor | NVDA + F7, la lista de elementos |
| Saltar al encabezado siguiente | VO + Comando + H | H |
| Saltar al enlace siguiente | VO + Comando + L | K |
| Saltar al control siguiente de un formulario | VO + Comando + J | F |
| Saltar a la región siguiente | Rotor, lista de puntos de referencia | D |

La lista de elementos de NVDA hace lo mismo que el rotor (enlaces, encabezados, campos de formulario, botones o puntos de referencia). Con **Mayús** delante de cualquiera de las letras, NVDA vuelve al anterior de ese tipo.

### Otros lectores

- **Narrador (Windows):** Windows + Control + Intro lo enciende. Su tecla es Bloq Mayús o Insert; Narrador + Espacio activa el **modo de examen**, el que sirve para leer páginas web.
- **TalkBack (Android):** Ajustes > Accesibilidad > TalkBack, o mantener pulsados unos segundos los dos botones de volumen. Para saltar de encabezado en encabezado o de enlace en enlace, elegir ese control de lectura y deslizar un dedo hacia abajo o arriba.
- **VoiceOver (iPhone):** Ajustes > Accesibilidad > VoiceOver. Su rotor se mueve **girando dos dedos** sobre la pantalla, como un dial, y luego se desliza un dedo hacia arriba o abajo.

### Cómo probar con lector

- Probar primero con la pantalla a la vista, para entender qué dice el lector en cada sitio; luego **bajar el brillo del todo** y repetir.
- Mirar el código sin lector: Chrome/Edge > Inspeccionar > pestaña **Accessibility**.
- Cuando se abre el rotor, los **enlaces** se ven con su nombre accesible: ahí se nota si un enlace como «Ver grabación» se repite varias veces sin contexto o si dice «3» sin explicar que es la cesta.
