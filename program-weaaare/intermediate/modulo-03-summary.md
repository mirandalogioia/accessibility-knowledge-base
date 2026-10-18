---
title: "Módulo 3 — Diseño visual accesible"
status: draft
source: "raw-inputs/modulo-03-raw.txt (audio de las lecciones, Consuelo) + raw-inputs/modulo-03-contenido-escrito-raw.txt (texto escrito de la plataforma, transcrito de capturas)"
last_updated: 2026-10-18
---

# Módulo 3 — Diseño visual accesible

Resumen consolidado del Módulo 3, fusionando la explicación en video de la profesora con el contenido escrito de cada lección en la plataforma. Cubre las 10 lecciones (3.1 a 3.10). No incluye guía de proyecto post-módulo (no apareció en el material entregado).

## Cómo leer este resumen

- **Audio y texto se complementan, no se repiten.** En los videos, la profesora presenta y explica los términos apoyándose en pantallas de ejemplo (en este módulo, sobre todo una reserva de tren Madrid–Valencia con tarjeta, pestañas y menú); el texto de la plataforma profundiza con tablas, criterios, enlaces a referencias y ejercicios. Esas pantallas son material visual que no se transcribió (el audio solo las narra), y no hacen falta para entender los conceptos. Cada lección indica qué aporta cada fuente; lo que dice una y no la otra no es una contradicción.
- **El audio es una transcripción automática** con errores. Los que se detectaron: «web AIM» = WebAIM; «WIAR» = WAI; «responsabilidad» = responsividad / diseño responsivo; «preset» = estado pulsado (pressed); «ticket» = tic (✓); «área chica» probablemente modismo (fútbol), sin contenido técnico.
- **Decisión del repo sobre contraste de controles:** el contraste de **componentes de interfaz y sus estados** (botones, bordes de campos, indicadores de foco) es de **3:1** y lo regula **1.4.11 Contraste no textual (AA)**; **1.4.3 Contraste (mínimo)** regula solo el **texto** (4,5:1 normal, 3:1 grande). El resumen automático que viene en el encabezado de `modulo-03-raw.txt` atribuye los 3:1 de los controles al 1.4.3: es un error de ese resumen y no se usa. Coincide con el texto escrito del módulo y con [`resources/wcag22-understanding/`](../../resources/wcag22-understanding/01-perceivable.md).
- Los criterios WCAG se resumen en [`resources/wcag22-understanding/`](../../resources/wcag22-understanding/README.md) y las técnicas en [`resources/wcag22-techniques/`](../../resources/wcag22-techniques/README.md).

## Mapa del módulo

| Lección | Tema | Criterios / recursos principales |
|---|---|---|
| 3.1 | Contraste de color y WCAG | 1.4.3 (AA), 1.4.11 (AA); WebAIM, Stark, Colour Contrast Analyser |
| 3.2 | Texto normal y texto grande | 1.4.3 (AA) |
| 3.3 | El color como único medio para comunicar información | 1.4.1 (A); Vision Simulator de Stark |
| 3.4 | Estados visuales de los elementos interactivos | 2.4.7 (AA), 1.4.11 (AA); patrón de pestañas de la APG |
| 3.5 | Indicadores visuales de interacción (foco) | 2.4.11 (AA), 2.4.12 (AAA), 2.4.13 (AAA), 1.4.11 |
| 3.6 | Tipografía y legibilidad | 1.4.8 (AAA), 1.4.12 (AA); técnica C36 |
| 3.7 | Jerarquía visual y jerarquía semántica | 1.3.1 (A); tutorial de encabezados de WAI |
| 3.8 | Zoom y reflow | 1.4.4 (AA), 1.4.10 (AA) |
| 3.9 | Diseño responsivo y accesibilidad | 1.4.10, 1.4.4 |
| 3.10 | Imágenes, iconografía e información no textual | tutoriales de imágenes y de imágenes funcionales de WAI |

---

## 3.1 — Contraste de color y WCAG

**Idea central**: el contraste es una **relación entre dos colores** (se expresa como 4,5:1), no una propiedad de un color aislado. Un gris no «tiene» contraste suficiente: depende de lo que tenga al lado. La WCAG permite defender decisiones de color con un número comprobable en vez de decidirlas «por cómo se ve en mi pantalla».

**Texto — 1.4.3 Contraste (mínimo), AA**: texto normal **4,5:1**; texto grande **3:1** (excepciones: logotipos, decoración, texto incidental, componentes inactivos).
- Ejemplo del audio (tarjeta del tren, texto de 16 px): gris a **2,85:1** → no cumple; gris intermedio justo en **4,5:1** → cumple («¿es el mejor? Lo podemos discutir, pero cumple»); **7:1** en «andén 6». Decisión de diseño: apostar por 4,5:1 o ir por un margen mayor con 7:1 (el 7:1 es el nivel AAA de 1.4.6 Contraste (mejorado), que la lección no nombra).
- Ejemplo del texto escrito (botón «Guardar cambios», 16 px): letras blancas sobre #999999 ≈ **2,85:1** (no cumple) y sobre #595959 ≈ **7:1** (cumple).

**Qué se compara con qué**: las letras contra **el relleno del botón** (es el fondo que tienen detrás), no el relleno contra la página. Medir el relleno contra la página responde a otra pregunta (¿se distingue la forma del control?) y no dice si se lee el texto.

**Controles — 1.4.11 Contraste no textual, AA**: los elementos de interfaz (botón contra fondo, borde del input) necesitan **3:1** contra el fondo que los rodea, solo si son lo que permite identificar el control.
- Ejemplo del audio: el botón negro sobre blanco y el borde del campo «Valencia».
- Ejemplo escrito (campo «Nombre del equipo»): borde #B8B8B8 sobre blanco **no llega a 3:1**; #767676 **sí**. Oscurecer la etiqueta no arregla el borde: la etiqueta ya se leía y el espacio para escribir seguiría costando encontrar.
- **No todo adorno necesita 3:1**: un separador decorativo no equivale al borde necesario para identificar un campo; tampoco hace falta añadir un rectángulo a un botón si su texto y contexto ya lo hacen reconocible.

**Herramientas (las tres aparecen en ambas fuentes)**:

| Herramienta | Qué hace | Detalle |
|---|---|---|
| WebAIM Contrast Checker | Calcula la relación al ingresar dos colores | Muestra el valor y si aprueba para texto normal y grande |
| Stark (plugin de Figma) | Lo mismo, dentro de Figma; en su versión gratuita hace además otras comprobaciones de accesibilidad | **Sugiere alternativas parecidas** de color (orienta hacia dónde puede ir la paleta; no necesariamente encaja con el manual de marca) |
| Colour Contrast Analyser | App de escritorio con **cuentagotas** para medir cualquier cosa en pantalla | No genera recomendaciones |

**Buenas prácticas de medición (texto escrito)**: con cuentagotas, tomar el **interior del trazo** de la letra (el suavizado de los bordes mezcla color con fondo y altera la muestra); si se tienen los valores del diseño o los estilos de la web, introducirlos directamente. Con texto sobre foto o degradado el fondo cambia bajo cada palabra: medir una zona oscura no demuestra que se lea entero, hay que revisar las zonas de menor diferencia.

**Práctica**: abrir la portada inaccesible de CityLights (demo BAD del W3C), encontrar problemas de contraste y comprobarlos con Colour Contrast Analyser o WebAIM; luego comparar con la solución.

## 3.2 — Texto normal y texto grande

**Idea central**: la categoría (normal/grande) decide cuánto contraste pide el texto. Depende **solo de tamaño y peso**, no de que sea título, precio o aviso, ni de la importancia de la información.

La WCAG da los tamaños **en puntos**; el diseño necesita **píxeles CSS**. No fija un tamaño mínimo ni máximo recomendado: solo un límite a partir del cual es «grande».

| Cómo se muestra el texto | Categoría | Mínimo en AA (1.4.3) |
|---|---|---|
| 24 px o más (18 pt), **cualquier peso** | Grande | 3:1 |
| 18,67 px o más (14 pt), **en negrita** | Grande | 3:1 |
| Por debajo de esos límites | Normal | 4,5:1 |

- Un mismo componente puede tener dos requisitos: en el audio, el título de la ruta a 24 px en negrita es grande (3:1) y el horario es normal (4,5:1, «porque tiene menor visibilidad»).
- **Trampas** (texto escrito): un título de 23 px regular sigue siendo texto normal; un aviso de 20 px en negrita es grande; la negrita **no** habilita 3:1 a cualquier tamaño (a 18 px sigue siendo normal).

**Caso La Esquina (texto escrito)** — carta con cuatro estilos, mismo gris para dos de ellos:

| # | Texto | Estilo | Color / contraste | Mínimo | Resultado |
|---|---|---|---|---|---|
| 1 | Nombre de la sección | 24 px regular | #888888 → 3,54:1 | 3:1 | **Cumple** |
| 2 | Nombre y precio de la tostada | 20 px negrita | #AAAAAA → 2,32:1 | 3:1 | **No cumple** |
| 3 | Ingredientes | 16 px regular | #888888 → 3,54:1 | 4,5:1 | **No cumple** |
| 4 | Aviso de alérgenos | 18 px negrita | #595959 → ≈7:1 | 4,5:1 | **Cumple** |

La lección clave: **el mismo #888888 da la misma medida en 1 y 3, pero solo sirve para uno**. Primero se clasifica el estilo; después se interpreta la medida.

**Cómo corregir sin deshacer la carta**: oscurecer el gris de los ingredientes y conservar sus 16 px. No «resolver» agrandando todo hasta que cuente como grande: la carta crece y se pierde la diferencia entre nombre del plato y descripción.
- **24 px / 18,67 px no son un tamaño mínimo recomendado**: una nota de 12 px puede llegar a 4,5:1 y seguir siendo ilegible en un móvil. El contraste resuelve letras-contra-fondo; la elección del tamaño debe considerar la lectura real.
- Se evalúa el **tamaño con el que se entrega el texto**: ampliar la página no vuelve válida una pareja que no cumplía.
- Con capturas, recordar la **alta densidad de pantalla** (un píxel CSS = varios físicos): el ancho de la letra en la imagen no da el tamaño del estilo.

## 3.3 — El color como único medio para comunicar información

**Idea central**: **1.4.1 Uso del color (A)** pide que una información no dependa **únicamente** del color. Palabras, símbolos y formas conservan el significado cuando dos tonos se confunden.

**Cómo detectar la dependencia** (audio + texto): quitar el color y ver qué queda. Con el plugin **Stark** (Vision Simulator) se ve la pantalla como la verían personas con distintos tipos de daltonismo; la **escala de grises** también ayuda. La combinación **verde–rojo** es la que más problemas da porque tienden a verse similares. Las simulaciones permiten detectar dependencias del color; **no reproducen exactamente** la visión de cada persona. La comprobación real es si las otras señales permiten entender la información.

**Cómo corregir**:
- Conservar el color y **añadir texto** («Confirmado») y, si ayuda, un **icono** (tic; cruz en la cancelación). El audio agrega que el icono acelera la identificación, por ejemplo para personas con discapacidad cognitiva.
- **Errores de formulario** (texto escrito): un campo que solo cambia a rojo no dice qué pasa ni cómo seguir (y si no se distingue el rojo, puede parecer aceptado). La versión correcta mantiene el rojo y añade **símbolo de error + mensaje que permite corregir** («ana@» → qué falta y cómo escribirlo). El borde rojo ayuda a encontrar el error, pero ya no hay que interpretarlo; **un símbolo aislado tampoco explica cómo corregir**, por eso acompaña al mensaje.
- **Estados de un pedido** («En preparación» / «Entregado»): si solo hay dos puntos de color, la persona tiene que conocer y distinguir el código. El texto conserva el estado y el color lo refuerza.
- **Gráficos** (donde más errores aparecen, según el audio): barras y tortas no pueden distinguirse solo por color. Que las barras se distingan del fondo no garantiza poder relacionarlas con una leyenda de colores. Soluciones: **etiqueta directa junto a cada barra**, **patrones o texturas** (con su significado claro), **separar las áreas** de una torta, y una **tabla** como otra forma de consulta cuando hay muchos datos. En una torta, dos colores confundibles pueden parecer un 100 %.

## 3.4 — Estados visuales de los elementos interactivos

**Idea central**: **foco ≠ selección**. El **foco de teclado** indica qué control recibe las pulsaciones; la **selección** conserva una decisión. Una casilla puede estar marcada sin foco, o con foco y vacía.

**Teclado (audio + texto)**:
- **Tab** avanza por los elementos interactivos (formulario, botones, enlaces); **Mayús + Tab** retrocede.
- **Intro o Espacio** activan un botón; en una **casilla**, **Espacio cambia su selección**. Llegar con Tab **no activa** nada: recorrer las preferencias permite leerlas sin cambiarlas.
- **Pestañas** (ver [`resources/wai-aria-apg-tabs-pattern.md`](../../resources/wai-aria-apg-tabs-pattern.md)): Tab llega al grupo y las **flechas** mueven entre pestañas; una pestaña identifica el panel abierto y otra puede recibir el foco antes de activarse con Intro o Espacio (activación manual).

**Escenario de Nora (texto escrito)**: ya marcó «Por correo electrónico» y avanza a «Por SMS». El **tic** (azul oscuro, permanece) y el **contorno violeta** (el foco, se desplaza) deben dibujarse distinto; si ambos se dibujan igual, parece que la opción se activa al pasar.

**Estados que hay que diseñar** (audio): disponible, **inhabilitado**, **foco**, **hover** y **pulsado**.
- **El foco es lo que más se olvida.** Existe en cualquier elemento interactivo (y *solo* en ellos: la profesora ha visto encabezados sin función interactiva con estado de foco, «un error tremendo de diseño»).
- **Diseñar combinaciones, no solo estados sueltos**: ejemplo, error sin foco + error con foco en un input. Diseñar cada estado no garantiza que la combinación esté bien implementada.
- **Foco visible sobre cualquier fondo** (audio + texto): una solución es el **borde de dos colores** (blanco + negro): sobre fondo oscuro se ve el blanco, sobre claro el negro. Un contorno negro puede funcionar sobre blanco y perderse en una cabecera oscura. **2.4.7 Foco visible (AA)** exige poder reconocer el foco; un destello que desaparece no orienta a quien vuelve a mirar tras una pausa. El contraste del contorno lo trata **1.4.11**.
- **Hover** responde al puntero; el foco, al teclado. Si un botón solo cambia al pasar el ratón, eso no ayuda a encontrarlo con Tab.
- **Pulsado** (el audio transcribe «preset») es la respuesta breve mientras se mantiene presionado; una preferencia marcada permanece hasta que se cambia. El diseño debe distinguir ambas cosas.
- **Inhabilitado**: significa que no se puede usar; se usa típicamente cuando falta una condición previa (p. ej. completar un formulario). **No existen enlaces inhabilitados**: solo botones y elementos de formulario. Un botón inhabilitado necesita que **se entienda el motivo** («Guardar cambios» sin cambios que guardar); el aspecto atenuado por sí solo no lo explica.
- **Conservar el error al volver al campo**: si el campo muestra «Revisa el correo: falta el signo @», volver a él no debe borrar el mensaje; se conserva y se añade un contorno exterior de foco para reconocer ambas cosas.

## 3.5 — Indicadores visuales de interacción (foco)

**Idea central**: tres cosas distintas sobre el foco — que **no quede tapado**, que su **área** sea suficiente y que tenga **contraste**.

**1. Foco no oscurecido** (2.4.11 mínimo, AA / 2.4.12 mejorado, AAA):

| Qué parte del control queda visible | Qué exige el criterio |
|---|---|
| Ninguna (un componente fijo lo cubre entero) | No cumple 2.4.11 (AA) ni 2.4.12 (AAA) |
| Solo una parte | Puede cumplir 2.4.11 (AA), pero no 2.4.12 (AAA) |
| Todo el botón | La ocultación deja de ser el problema; falta distinguir su indicador |

- Ejemplo del audio: «descargar billete» con foco pero bajo un componente fijo de ayuda durante el viaje. Ejemplo del texto: «Confirmar cita» bajo un aviso de cookies. La mejor experiencia para todos es la tercera, **independientemente del nivel buscado**: «se trata de cumplir la WCAG, pero también de diseñar con criterio» (no todas las personas pueden deducir el texto que falta).
- Solución: **reservar espacio** para el aviso y ajustar el desplazamiento; debe funcionar al avanzar **y al volver con Mayús + Tab**. Acortar el botón no resuelve que otro elemento ocupe su sitio. Para quien ve solo una parte ampliada, la falta de referencia dificulta saber qué se va a activar.

**2. Área del indicador** (2.4.13 Apariencia del foco, AAA): el área importa. Para un botón de **100 × 40 px**, la referencia equivale a un perímetro de 2 px de grosor = **560 px²**. Una línea de 100 × 2 px en un solo lado ocupa **200 px²**: aunque sea negra sobre blanco, queda por debajo. Contorno completo → suficiente; solo una línea inferior → no basta para AAA (el audio añade que para AA «podría funcionar»; 2.4.7 solo exige que el foco sea visible).

**3. Contraste del indicador**: el audio lo plantea como **3:1** (ejemplo: borde negro sobre blanco, 21:1, «más que cumple»). El texto escrito lo precisa:
- En **2.4.13 (AAA)** el cambio de contraste se compara entre **los mismos píxeles antes y después de recibir el foco** (≥ 3:1).
- Es **distinto** del contraste con los colores adyacentes que exige **1.4.11 (AA)** para identificar el estado diseñado.
- Un contorno visible sobre página blanca puede perderse alrededor de un botón oscuro: el indicador se diseña **para los fondos y estados** donde tendrá que orientar.

**Argumentos para stakeholders** (audio): muchas veces creen que el foco «arruina la experiencia visual»; está diseñado justamente para quienes navegan con teclado. Además **orienta en navegación por voz** (las tecnologías de apoyo dependen del teclado/foco).

## 3.6 — Tipografía y legibilidad

**Idea central**: la tipografía influye en **reconocer una letra**; la composición en **seguir una frase, pasar de línea y reencontrar un dato**.

- **Prueba de legibilidad de familia tipográfica** (audio + texto): escribir **«I l 1 0 O»** (I mayúscula, l minúscula, 1, 0, O). Si se distinguen, la fuente funciona. Importa donde **no se puede deducir por contexto** (códigos de recogida, localizadores): en una palabra conocida se anticipa una letra, en un código hay que reconocer cada carácter. Elegir con o sin serifa no garantiza por sí solo la legibilidad; después hay que comprobar tamaño, peso y contenidos reales.
- **No más de dos familias** (audio); la jerarquía se construye con **peso, tamaño y espacio** (en el ejemplo del audio: solo espacio → más tamaño → tamaño + peso).
- **Alinear a la izquierda, no justificar** (audio + texto): en digital no se controla el ancho de la columna (móvil o televisor gigante); justificar abre huecos grandes en columnas estrechas. Alinear al inicio mantiene regular el espacio y el comienzo de las líneas. Una columna demasiado ancha dificulta encontrar el inicio de la línea siguiente: **1.4.8 Presentación visual (AAA)** incluye líneas de **hasta 80 caracteres** en español y texto sin justificar (no obliga a llenar cada línea).
- **1.4.12 Espaciado del texto (AA)** — el contenido debe admitir que la persona sobrescriba el espaciado (por herramientas del navegador) sin perder texto ni controles. Valores de prueba aplicados **juntos**:

| Propiedad | Valor de prueba | Con fuente de 16 px |
|---|---|---|
| Altura de línea | 1,5 × tamaño de fuente | 24 px |
| Espacio después del párrafo | 2 × | 32 px |
| Espacio entre letras | 0,12 × | 1,92 px |
| Espacio entre palabras | 0,16 × | 2,56 px |

  Son valores **para comprobar**; **no** obligan a publicar con ellos ni a añadir un panel de preferencias («lo único que tenemos que hacer es no entorpecer»). La **técnica C36** del W3C explica cómo comprobarlo (no fijar alturas en los contenedores de texto).
- **El espacio también transmite organización** (texto): fecha y horario forman un grupo; materiales, otro. Separar el horario de su fecha puede asociarlo al taller equivocado aunque cada letra se lea bien. Por eso se comprueba con la ficha completa, no con una lista de tamaños.

## 3.7 — Jerarquía visual y jerarquía semántica

**Idea central**: la jerarquía visual (espacio, negrita, indentación) debe **transmitirse también en la estructura** para quien usa tecnología de apoyo. Un **encabezado** identifica una sección; su **nivel** expresa cómo se relaciona con las demás. El lector de pantalla permite consultar la **lista de encabezados** o saltar entre ellos: esa lista funciona como un **índice**. Criterio relacionado: **1.3.1 Información y relaciones (A)**. Recurso: [`resources/wai-tutorial-page-structure-headings.md`](../../resources/wai-tutorial-page-structure-headings.md).

- **Niveles** (audio): **H1** = título de la página; **H2** = título de sección; **H3** = título de subsección. Ejemplo del audio (ficha de producto): «Producto» H1; «Características» y «Especificaciones» H2; «Materiales» y «Dimensiones» (hijos de «Características») H3. Los H van del 1 al 6, siendo el 6 el de menor jerarquía.
- **El índice debe conservar las agrupaciones** (texto): si «Si tienes menos de 14 años» se marca h2, queda al nivel de «Quién puede pedirlo» en vez de dentro de él.
- **Hermanos** (audio, analogía de la familia): dos encabezados hermanos ocupan el mismo nivel aunque uno se vea más grande que otro, igual que los hermanos no tienen que ser gemelos.
- **Un texto destacado no siempre abre una sección** (texto): «Gratis y válido en las 12 bibliotecas de la red» puede seguir siendo un **párrafo con énfasis**. Convertir cada frase destacada en encabezado alarga el índice con entradas que no son apartados y obliga a recorrer anuncios antes de llegar al contenido.
- **Nivel y tamaño son decisiones diferentes** (texto + audio): el título de una portada puede ser de 48 px y el de una página interior de 24 px; ambos pueden ser h1. El tamaño responde a la composición; el nivel, al lugar del contenido en el esquema.
- **Implicación para el sistema de diseño**: si «H1» siempre significa 48 px, quien necesita un título menor elige «H3» para conseguir 24 px y rompe la estructura. Solución (audio + texto): **no diseñar los H como tamaños fijos, sino estilos con nombres neutros** («Título L», «Título S») que se pueden asignar a cualquier nivel. Anotación para desarrollo: **«h1 · Título S»** comunica ambas decisiones (nivel y estilo).
- **Ejercicio de la plataforma («Organiza otra página de Biblioteca Norte»)**: «Reserva una sala de estudio» → **h1 · Título S** (24 px no lo vuelve h3); «Horarios» → **h2** (hermano de «Condiciones de uso»); «Reservas en grupo» → **h3**, apartado de «Condiciones de uso»; «Todas las salas tienen wifi» → **párrafo con énfasis**, no encabezado. Sobra «h3 · cualquier texto que mida 24 px».

## 3.8 — Zoom y reflow

**Idea central**: el **zoom** amplía; el **reflow** (reajuste) asegura que la información y las acciones **sigan disponibles** al ampliar.

- **Quién lo usa**: personas con baja visión (en todas las interfaces) **y** personas con discapacidad cognitiva que no pueden entender el orden del contenido: el zoom lo reorganiza «como un celular gigante», en columna.
- **Cómo se hace**: zoom de página del navegador (menú, o **Comando/Control + «+» / «−»**, **Comando/Control + 0** restaura el 100 %). La lupa del sistema o el pellizco ampliarían una zona **sin provocar el mismo reajuste**; para comprobar se usa el zoom de página.
- **Qué se comprueba**:
  - **1.4.4 Cambio de tamaño del texto (AA)**: texto ampliable hasta **200 %** sin perder contenido ni funcionalidad. Algunas personas usan una opción que aumenta **solo el texto**; las letras crecen y otros elementos no, lo que puede revelar recortes. *(El audio habla de «200 % y 400 %» sin nombrar este criterio.)*
  - **1.4.10 Reflow (AA)**: página de lectura vertical funcionando con un ancho equivalente a **320 px CSS**, sin pérdida de información/funciones y **sin scroll en dos direcciones**. Una zona de **1280 px CSS al 100 %** ofrece ese ancho al **400 %**. Para medir exactamente los 320 px hay que controlar también el ancho de partida.
- **Excepciones** (audio + texto): contenido que **necesita dos dimensiones** (mapa, tabla de datos: conservan la relación espacial o de filas/columnas). La excepción es para esa zona; **no justifica** que los párrafos que la acompañan se salgan del ancho. Un **carrusel** puede conservar su desplazamiento propio si cada tarjeta se lee dentro del ancho disponible; el patrón de navegación no justifica cortar frases.
- **Para el diseño y el desarrollo**: **no fijar alturas** con valores exactos; el contenedor debe ajustarse al contenido (una altura fija corta las últimas palabras). Dos columnas → una; menú extenso → botón que despliega.
- **Guion de prueba** (audio): recorrer la página al **200 %** y luego al **400 %**; verificar textos completos, controles disponibles, que **no se pierde información al reorganizar**, que las acciones son alcanzables **con teclado** con el comportamiento esperado, y que la lectura de izquierda a derecha sigue cada línea.
- **Práctica (CityLights, BAD del W3C)**: ampliar al 200 % y 400 % y ver si se puede leer un párrafo de principio a fin sin desplazarse hacia los lados. En la portada, el párrafo de bienvenida conserva una columna más ancha que la zona disponible: parte de cada línea queda fuera y la lectura exige desplazamiento en dos direcciones (causa: anchos fijos; solución: que el texto se ajuste y apilar columnas). Ver **menos contenido a la vez** al ampliar es esperable; la barrera aparece cuando **una frase no cabe**.

## 3.9 — Diseño responsivo y accesibilidad

**Idea central**: el diseño responsivo reorganiza según el espacio disponible, y ese espacio cambia con el dispositivo, **al estrechar la ventana o al ampliar con el navegador**. No basta con «tener una versión mobile»: la adaptación debe **conservar la tarea y los datos necesarios para completarla**.

- **Caso del texto**: en el ordenador aparecen títulos, sede y último día de recogida; en el móvil sigue «Confirmar reserva» pero **la fecha límite desapareció**. La acción funciona, falta la información para decidir si se llegará a tiempo.
- **Puntos de quiebre** (audio + texto): definirlos para que el contenido siga fluyendo en cualquier ancho (ancho o estrecho), **sin etiquetas como «móvil» o «tableta»** que dejan muchos tamaños sin resolver (p. ej. un portátil grande con media pantalla para cada tarea). Los grupos de la reserva pasan a una columna cuando sus textos dejan de caber con comodidad.
- **Qué se puede omitir** (audio): solo lo que es una **decisión de diseño** legítima, como una **imagen decorativa** que no aporta información en 320 px. Lo relevante se mantiene **sin pérdida de información**.
- **Nombres largos** (texto): «Sede del Parque» vs «Biblioteca de San Sebastián de los Reyes»: permitir varias líneas en vez de encoger la letra o esconder parte del nombre.
- **Mantener relaciones al apilar**: «18 de octubre» junto a «Recogida desde», «25 de octubre» junto a «Último día». No colocar primero todas las etiquetas y luego todas las fechas.
- **Navegación**: el menú se vuelve **botón «Menú» (hamburguesa)** pero sus destinos deben seguir disponibles. Hay que comprobar en la interfaz real que se pueda **abrir, recorrer y cerrar con teclado** y que el foco permita reconocer la opción; una ilustración estática no permite evaluarlo.
- **Prueba por tarea** (audio): pedir a alguien que, con zoom, **localice el billete y lea los datos**, y luego verificar que **la misma tarea** es posible con teclado.
- Criterios: **1.4.10** y **1.4.4**. Estrechar una ventana ayuda a detectar problemas de maquetación pero **no sustituye** las comprobaciones de aumento del texto.

## 3.10 — Imágenes, iconografía e información no textual

**Idea central**: las imágenes y los iconos pueden **informar, orientar o permitir una acción**. Antes de escribir una alternativa hay que **reconocer qué función cumple** en ese contexto: la forma del dibujo, por sí sola, no determina qué debe contarse. (Criterio relacionado de WCAG: 1.1.1 Contenido no textual, A; la lección no lo nombra.)

- **Imágenes que contienen información** (audio + texto): un instructivo de montaje (cinco pasos: piezas, posición, orden) o un plano (por dónde entrar, dónde está el ascensor, cómo llegar a una sala) deben poder entenderse sin la imagen. «Plano de la biblioteca» identifica el documento pero no permite seguir el recorrido. El audio recalca no asumir que una persona ciega «no arma muebles»: la información debe transmitirse de otra manera.
- **Procedimientos ilustrados**: una ilustración para ajustar un casco necesita conservar qué correa se mueve, en qué dirección y cómo se comprueba el ajuste. Quien redacta debe **conocer** las instrucciones; no puede deducirlas ni inventarlas a partir de una imagen pequeña.
- **La misma imagen cambia de función según el contexto** (audio + texto): una foto de verduras como fondo de bienvenida junto a un mensaje completo puede ser **decorativa**; en una ficha de producto a la venta debe transmitir la frescura/qué se vende; la cubierta de un libro en una portada decora, en una ficha de edición distingue la edición, y como único contenido de un enlace debe comunicar **adónde lleva**.

| En este contexto… | Hace falta comunicar… | Solo identificar el dibujo deja fuera… |
|---|---|---|
| Un plano de acceso | El recorrido y las referencias necesarias | Por dónde entrar y cómo llegar |
| Un icono que elimina una reserva | La acción y la reserva afectada | Qué ocurrirá al pulsarlo |
| Un gráfico de préstamos | Los datos y las relaciones relevantes | Qué resultado muestran los datos |
| Un cartel de actividades | El mensaje y los detalles para participar | Cuándo, dónde y cómo apuntarse |

- **Regla resumida** (audio): si es parte de un **botón** → transmitir la **acción**; si es un **gráfico** → los **datos relevantes y sus relaciones**; si es un **cartel/afiche** → el **mensaje** y qué propone hacer.
- **No todo cabe en una alternativa breve**: un gráfico puede necesitar una explicación **y una tabla de datos** en la propia página; un icono-botón necesita un **nombre corto** que permita reconocer su acción.
- **Nombre accesible**: el nombre con el que una tecnología de apoyo identifica un control. En una lista de reservas, «**Eliminar reserva de Viajes por el mundo**» (no «Papelera», que describe la forma pero no identifica la reserva afectada). Mostrar **texto junto al icono** también ayuda a quien lo ve y desconoce el símbolo (en el audio: botón con papelera vs botón con texto «Eliminar archivo»).
- **El contexto manda**: una papelera que abre la carpeta de elementos eliminados **no** debe anunciarse como «Eliminar reserva»: prometería otra acción. Antes de nombrar un control hay que conocer su comportamiento real.
- **Ejercicio de la plataforma** (feedback visible): cartel de Encuadernación japonesa → mensaje y datos para participar («Cartel de actividades» no basta); gráfico Préstamos → datos y relaciones (explicación de la tendencia + tabla); papelera en la reserva de Bosques → acción sobre esa reserva; hojas en la cabecera Actividades de otoño → **decoración, se puede ignorar**.
- Recursos de WAI citados: tutorial de imágenes (alternativas según propósito) y tutorial de imágenes funcionales (alternativa de una imagen que permite actuar).

---

## Checklist para el proyecto final (derivado del módulo)

Lista de verificación armada a partir de las lecciones; no es una entrega oficial del programa.

**Color y contraste**
- Clasificar cada estilo de texto (normal/grande) **antes** de medir; texto normal 4,5:1, grande 3:1. Medir letras contra el **fondo real** (relleno del botón, no la página).
- Bordes y rellenos necesarios para identificar controles: 3:1 contra lo que los rodea (1.4.11).
- Nada que dependa **solo** del color: estados, errores, gráficos (texto + icono/patrón/etiqueta). Probar en escala de grises y con simulación (Stark).

**Estados y foco**
- Diseñar **todos** los estados de cada componente interactivo (disponible, inhabilitado, foco, hover, pulsado) **y combinaciones** (p. ej. error con y sin foco).
- Foco **distinto de la selección**; visible sobre cada fondo donde aparezca (borde de dos colores); con área suficiente; no tapado por elementos fijos (aviso de cookies, ayudas).
- Un botón inhabilitado explica por qué; no existen enlaces inhabilitados.
- Documentar el teclado de componentes complejos (p. ej. pestañas: Tab entra al grupo, flechas entre pestañas, Intro/Espacio activan si es manual).

**Tipografía y estructura**
- Probar la familia con «I l 1 0 O»; máximo dos familias; alineado a la izquierda, líneas de hasta ~80 caracteres.
- Admitir 1,5 / 2 / 0,12 / 0,16 sin cortar contenido (no fijar alturas).
- Estilos de título con **nombres neutros** (Título L/S) y anotación de **nivel + estilo** («h1 · Título S»); el énfasis no es encabezado; el índice de encabezados refleja la organización real.

**Zoom, adaptación e imágenes**
- Probar al **200 % y 400 %**: nada se pierde, todo es alcanzable con teclado; sin alturas fijas; excepciones solo para mapas/tablas.
- Puntos de quiebre por contenido, no por «dispositivo»; mantener datos y su relación al apilar; menú colapsado operable con teclado.
- Para cada imagen/icono: definir su **función** (informa, orienta, actúa, decora) y escribir la alternativa/nombre accesible según ella.

## Pendientes / puntos a confirmar

- Las pantallas de ejemplo visuales de los videos (p. ej. la tarjeta del tren) no están transcritas; solo existen en el repo las partes que Consuelo narra.
- Los **títulos de lección** salen de cómo los anuncia la profesora en el audio, no necesariamente del título literal de la plataforma.
- El **enunciado del ejercicio de 3.10** y las imágenes de las versiones del campo de 3.3 no estaban en las capturas; solo se transcribió el feedback visible.
- El material entregado **no incluye guía de proyecto post-módulo** (el Módulo 2 sí la tenía).
- Los recursos citados que **aún no tienen resumen** en `resources/`: tutorial de imágenes de WAI y tutorial de imágenes funcionales de WAI (solo enlazados en [`links.md`](../../resources/links.md)).
