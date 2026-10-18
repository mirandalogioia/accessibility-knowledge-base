---
title: "Módulo 2 — WCAG para diseñadores"
status: draft
source: "raw-inputs/modulo-02-raw.txt (audio de las lecciones) + raw-inputs/modulo-02-contenido-escrito-raw.txt (texto escrito de la plataforma)"
last_updated: 2026-10-16
---

# Módulo 2 — WCAG para diseñadores

Resumen consolidado del Módulo 2, fusionando la explicación en video con el contenido escrito de cada lección en la plataforma. Cubre las 11 lecciones completas (2.1 a 2.11) más la guía de proyecto post-módulo.

## 2.1 — Cómo está estructurado WCAG 2.2

**Origen**: WCAG lo desarrolla el **W3C** (consorcio que publica los estándares de la web) a través de la **WAI** (Web Accessibility Initiative), uno de sus grupos de trabajo. La WAI define varios estándares que cubren distintas piezas de la experiencia:

- **WCAG** — el contenido web (textos, imágenes, formularios, componentes, flujos). Es la referencia principal para revisar la interfaz que se diseña.
- **ATAG** (Authoring Tool Accessibility Guidelines) — herramientas con las que otras personas crean contenido (un gestor de contenidos, un editor, una red social). Exige dos cosas: que la herramienta misma sea accesible para quien publica, y que ayude a publicar contenido accesible (ej. pedir el alt text al subir una foto).
- **UAAG** (User Agent Accessibility Guidelines) — navegadores, extensiones, reproductores. Explica por qué cosas como el zoom del navegador o el tamaño de subtítulos del reproductor no dependen del diseño, y por qué el diseño no debe impedir que funcionen.
- **WAI-ARIA** — cómo un componente comunica función, estado y propiedades a la tecnología de apoyo cuando el HTML no alcanza. No hace falta saber su sintaxis para diseñar, pero sí que existe.
- **WCAG2ICT** — guía del W3C para trasladar los criterios de WCAG fuera de la web (apps, software, documentos).

**Versiones**: 1.0 (1999, estructura distinta a la actual) → 2.0 (2008, aparecen los 4 principios) → 2.1 (2018, amplía a baja visión, móvil, necesidades cognitivas) → 2.2 (2023, versión vigente recomendada por el W3C) → 3.0 (borrador, estructura y modelo de conformidad distintos — no sirve como referencia de cumplimiento hoy). Las versiones son **acumulativas**: cumplir 2.2 implica cumplir 2.1 y 2.0, con una única excepción — **4.1.1 Procesamiento** se retiró en 2.2 porque pedía código sin errores de sintaxis que los navegadores ya resuelven de forma estándar (la tecnología de apoyo trabaja con lo que interpreta el navegador, no con el código fuente). WCAG 2.2 es también **norma ISO/IEC 40500:2025** (idéntica a la versión de octubre 2023) — si un pliego cita la norma ISO, está citando WCAG 2.2.

Cada criterio tiene un **nivel: A, AA o AAA**. Para declarar AA hay que cumplir A + AA (son acumulativos). En el documento de un proyecto conviene anotar versión + nivel + alcance explícito: «WCAG 2.2, nivel AA, en todo el proceso de reserva».

**Documentos de apoyo de WCAG:**

| Qué necesitas saber | Qué consultar |
|---|---|
| Qué exige un criterio y sus excepciones | WCAG 2.2 (el estándar) |
| Por qué existe y a quién ayuda | Understanding WCAG 2.2 |
| Cómo cumplirlo y qué errores se conocen | Techniques for WCAG 2.2 |

Understanding y las técnicas ayudan a aplicar los requisitos pero no añaden otros nuevos — no hay que copiar literalmente una técnica del W3C, cualquier solución vale si cumple el criterio. WCAG incluye un **glosario** normativo (las definiciones sí forman parte del requisito).

**Qué puede comprobar un validador automático**: una herramienta lee el código y hace comprobaciones binarias (¿existe un alt? ¿cuál es el contraste numérico?), pero no puede juzgar *calidad* — si el alt text realmente describe la imagen, si el orden de lectura conserva el significado, si la tarea se puede completar. «0 errores» solo significa que la herramienta no encontró los problemas que sabe buscar; además puede generar **falsos positivos** (ej. marcar como fallo de contraste el texto de un botón deshabilitado, que **1.4.3 Contraste (mínimo) AA** exime explícitamente). Siempre hace falta revisión humana además de la herramienta.

**Para comprobar una declaración de "cumple WCAG"**, preguntar: ¿qué versión? ¿qué nivel? ¿qué páginas/procesos se revisaron? ¿quién lo comprobó y cómo? Una respuesta verificable sería: «2.2, AA, el proceso de compra completo, una herramienta más revisión manual con teclado y lector de pantalla».

## 2.2 — Los 4 principios

Caso base: reservar 2 plazas en una ruta (selector de plazas, campo de teléfono, casilla de condiciones, botón "Reservar"). Cada principio mira la misma pantalla desde un ángulo distinto:

- **Perceptible** — ¿le llega la información a la persona (vista/oído/tacto)? Incluye lo que *cambia*: plazas restantes, un error, confirmación de éxito. Un aviso que aparece 2 segundos como ícono verde y se desvanece solo le llega a quien miraba justo ahí en ese momento.
- **Operable** — ¿puede hacer todo lo que la tarea pide, con cualquier forma de interacción (ratón, teclado, voz, táctil, pulsador)? No significa "se puede hacer clic" — significa que alguien sin mouse llega al selector, cambia el número, marca la casilla y reserva, con tiempo suficiente y sin gestos de precisión.
- **Comprensible** — ¿entiende qué se le pide y qué va a pasar? Etiquetas que explican el campo y formato, un botón con nombre de acción específico ("Reservar plaza", no "Continuar"), errores que explican cómo corregir, y **coherencia** (mismo control funciona igual en todas las pantallas).
- **Robusto** — ¿puede interpretarlo la tecnología que usa? No significa "funciona en todos los navegadores" — significa que un lector de pantalla, control por voz o sistema de barrido reciben qué es cada control, cómo se llama y en qué estado está, sin adivinar por su aspecto. Ejemplo concreto: una casilla marcada visualmente bien puede fallar si el lector solo recibe el texto ("Acepto las condiciones de la ruta") en vez de texto+función+estado ("Acepto las condiciones de la ruta, casilla, marcada").

Ejemplo complementario del audio (formulario de contacto simple): Perceptible = el error se percibe al intentar enviar vacío; Operable = llegar al botón "Enviar" con Tab/Shift+Tab y activarlo con Intro/Espacio; Comprensible = etiqueta clara + mensaje de error con el siguiente paso + comportamiento consistente; Robusto = nombre="Enviar", rol=botón, estado=disponible — **nombre, rol y estado** es el resumen técnico del principio Robusto.

**Verbos, barreras y principios — relación (no son lo mismo):**

| Forma de mirar la tarea | Dónde cae en WCAG | Matiz |
|---|---|---|
| Percibir · barrera de percepción | Perceptible | Encaje directo |
| Comprender · barrera de comprensión | Comprensible | Encaje directo |
| Actuar · barrera de interacción | Operable | Operable suma tiempo y navegación, que "actuar" no sugiere |
| Barrera de estructura | Repartida | Relaciones/orden de lectura → Perceptible (1.3); orden del foco/encabezados → Operable (2.4); que lleguen a la tecnología de apoyo → Robusto |
| — | Robusto | Sin equivalente: habla de la tecnología, no de capacidades de la persona |

**Los principios no son categorías excluyentes** — una misma barrera puede afectar a varios a la vez. Ejemplo: un campo de teléfono que marca error solo con borde rojo falla en Perceptible (no se distingue el rojo) y en Comprensible (no dice qué falló). Un botón solo dibujado (no construido como botón) falla en Operable (Tab no llega) y en Robusto (el lector no dice "botón"). **Describir primero qué falla** orienta dónde buscar — y conviene revisar la tarea completa: si el teclado permite rellenar pero no llegar al botón final, la persona sigue sin poder completarla.

## 2.3 — Las pautas de WCAG

Las **13 pautas** agrupan los criterios por objetivo (no se "comprueban" en sí mismas — "¿es Distinguible esta pantalla?" no tiene sí/no). Perceptible tiene 4 pautas, Operable 5, Comprensible 3, Robusto 1.

| Pauta | Qué agrupa |
|---|---|
| 1.1 Alternativas textuales | Texto que sustituye imágenes/iconos/gráficos |
| 1.2 Medios tempodependientes | Subtítulos, audiodescripción, transcripciones |
| 1.3 Adaptable | Estructura/relaciones/orden independientes de la presentación |
| 1.4 Distinguible | Contraste, color, tamaño de texto, espaciado, zoom |
| 2.1 Accesible por teclado | Todo funciona sin ratón, sin trampas de foco |
| 2.2 Tiempo suficiente | Límites de tiempo, contenido que se mueve/actualiza solo |
| 2.3 Convulsiones y reacciones físicas | Destellos y animaciones dañinas |
| 2.4 Navegable | Orientarse: títulos, encabezados, enlaces, foco |
| 2.5 Modalidades de entrada | Puntero, gestos, arrastre, voz, tamaño de objetivos |
| 3.1 Legible | Idioma y comprensión del texto |
| 3.2 Predecible | Comportamiento sin sorpresas, coherencia |
| 3.3 Asistencia para entrada de datos | Etiquetas, errores, prevención, autenticación |
| 4.1 Compatible | Lo que cada componente comunica a la tecnología de apoyo |

Se busca **según el problema de la persona**, no al revés: sesión que se cierra sola → 2.2 Tiempo suficiente; no se puede completar con teclado → 2.1 Accesible por teclado; video de fondo sin pausa → 2.2 (no poder detener el movimiento); animación que marea al abrir un menú → 2.3. En esta etapa interesa reconocer el tema, no memorizar números ni excepciones.

## 2.4 — De una pauta a un criterio

**Describir antes de buscar** — una barrera bien descrita cabe en una frase de 4 piezas: **[Elemento] [qué pasa] para [quién/forma de uso] cuando [condición]**. "El texto gris no cumple" → mejor: «El aviso "Te enviaremos la confirmación en 24h" apenas se distingue del fondo para quien tiene baja visión o mira el móvil al sol, cuando se muestra en gris claro (#999999) sobre blanco» — el problema no era "ser gris", era que ese gris específico es insuficiente. El verbo de "qué pasa" ya apunta al principio (no llega → Perceptible; no se alcanza/no da tiempo → Operable; llega pero no se entiende → Comprensible; la tecnología de apoyo no lo recibe → Robusto).

**Encontrar el criterio en 3 pasos**: 1) **Principio** (lo da el verbo), 2) **Pauta** (dentro del principio, el objetivo que encaja), 3) **Criterio** (dentro de la pauta, leer las *condiciones*, no solo el nombre — en 1.4 hay 13 criterios).

Herramientas de búsqueda: **How to Meet WCAG 2.2** (referencia rápida, filtra por nivel/etiqueta temática/perfil), **índice de Understanding** (ordenado por principio y pauta), **buscar en WCAG 2.2** (Ctrl/Cmd+F con términos en inglés: label, error, contrast, focus, target — no hay traducción oficial al español). El nombre de un criterio puede confundir: "Encabezados y etiquetas" (2.4.6) no exige que existan etiquetas (eso lo pide 3.3.2), solo que las que hay describan su propósito.

**Un componente, varias barreras, varias correcciones** — ejemplo del formulario de Biblioteca Norte con 4 barreras simultáneas, cada una con su criterio y decisión propia:

| Barrera | Criterio | Decisión |
|---|---|---|
| «Dato» no dice qué se pide y desaparece al escribir | 3.3.2 Etiquetas o instrucciones (A); 2.4.6 Encabezados y etiquetas (AA) | Mantener la etiqueta fuera del campo |
| El marcador del correo apenas se lee | 1.4.3 Contraste (mínimo) (AA) | Color que se distinga del fondo |
| «Algo ha fallado» no identifica el error | 3.3.1 Identificación de errores (A); 3.3.3 Sugerencias ante errores (AA) | Indicar junto al campo qué falla y cómo corregir |
| Tab no alcanza «Teléfono» | 2.1.1 Teclado (A) | Incluir el campo en el recorrido de teclado |

Mejorar una barrera no resuelve las demás — registrar cada una por separado.

## 2.5 — Cómo leer un criterio

El nombre de un criterio es solo un resumen — hay que leer el texto completo para saber cuándo se aplica y qué excepciones tiene. **Partes de un criterio**: número y nombre, nivel (A/AA/AAA), la frase principal (el requisito), listas (cuidado con "al menos una de las siguientes" vs. "todas las siguientes" — cambian cómo se lee), excepciones, notas (informativas, no añaden requisitos), y términos enlazados al glosario (esos sí son normativos). Cuando no hay contenido al que aplicar un criterio, se considera **satisfecho** igual que si cumpliera — pero conviene distinguir "no aplica" de "cumple" al documentar.

**Las 5 preguntas para leer cualquier criterio:**
1. ¿A qué contenido afecta? (si tu caso no es de ese tipo, el criterio no es el tuyo)
2. ¿Cuándo aplica? (muchos tienen disparador: "si hay un límite de tiempo...")
3. ¿Qué condición exige? (aquí suele esconderse la diferencia con el título)
4. ¿Qué excepciones tiene?
5. ¿Qué nivel tiene?

Aplicadas a **3.2.6 Ayuda coherente (A)** (el enlace de ayuda se repite en varias páginas de Biblioteca Norte): afecta solo a 4 tipos de ayuda (datos de contacto, contacto con persona, autoayuda, mecanismo automatizado — la ayuda contextual de un campo no entra); aplica solo si la ayuda está y se repite en un **"conjunto de páginas web"** (término del glosario: mismo propósito y autor) — no obliga a ofrecer ayuda ni a ponerla en todas; exige que aparezca en el **mismo orden respecto al resto del contenido** (orden de lectura en secuencia, no posición en píxeles); la excepción es que el cambio lo inicie la persona usuaria (zoom, orientación, reordenar preferencias — cambiar de página NO cuenta como ese tipo de cambio); nivel A. Mantener el orden de *código* cumple el criterio, pero Understanding recomienda también mantener la ubicación *visual* coherente para que sea fácil de encontrar.

## 2.6 — Cómo cumplir un criterio

**1.4.1 Uso del color (A)** exige una alternativa visual al color — que el lector de pantalla anuncie el estado (ej. "Disponible") resuelve un problema distinto (que la info llegue a la tecnología de apoyo); hacen falta ambas cosas.

**Distintas soluciones válidas para el mismo problema de color** (agenda con horas libres en verde / ocupadas en rojo): añadir la palabra "Libre"/"Ocupada" (cumple, pero la persona sigue leyendo y descartando opciones), añadir ícono/textura (cumple si la diferencia se ve sin color, pero hay que aprender su significado), **mostrar solo las horas libres** (cumple y además reduce lo que hay que recorrer — "no se puede reservar lo que no está disponible, mejor no mostrarlo"), o agruparlas en franjas ("Mañana"/"Tarde" — la organización también informa). WCAG no elige la solución, solo fija la condición que debe cumplirse — el cómo sigue siendo decisión de diseño.

**Consultar Techniques for WCAG 2.2** — 3 tipos: **técnicas suficientes** (formas fiables, a veces combinadas con "AND"), **técnicas recomendadas** (mejoras que no bastan solas), **fallos documentados** (si tu diseño coincide, no cumple, salvo versión alternativa). No es una lista cerrada — se puede resolver de otra forma si se cumple el requisito.

**Patrones conocidos** — usar componentes y patrones ya conocidos (ej. controles nativos del navegador) aprovecha gratis su comportamiento de teclado y su info para tecnología de apoyo. Heurística de Nielsen **"reconocer antes que recordar"** (#6) + pauta 3.2 Predecible (coherencia de navegación/nombres). Heurísticas 5 (prevenir errores) y 9 (ayudar a reconocer/corregir errores) orientan el diseño de formularios.

**Qué debe explicar un mensaje de error** — 6 decisiones: **dónde** (junto al campo; + resumen al inicio si hay varios), **cómo se marca** (texto + ícono + borde más grueso, no solo color — contraste del borde ≥3:1, por 1.4.1 + 1.4.11), **qué falló** (nombrar el campo y describir en texto — 3.3.1), **cómo se arregla** (decir la corrección con ejemplo de formato válido — 3.3.3), **qué se conserva** (todo lo escrito, incluido el erróneo, para corregir sin reescribir), **con qué tono** (sin jerga, sin culpar a la persona). Un mismo texto puede cumplir 3.3.1 y 3.3.3 a la vez: «Al correo le falta la @. Escríbelo así: ana@ejemplo.com». 3.3.3 **no** exige sugerir corrección si compromete seguridad o el propósito del contenido (ej. login, exámenes).

## 2.7 — Niveles de conformidad

Los 3 niveles son **acumulativos**: A exige todos los A; AA exige A+AA (55 criterios en WCAG 2.2); AAA exige los tres. Reglas clave: **no hay conformidad parcial por nivel** (fallar un solo criterio AA hace que la página no sea AA — no existe "casi AA"), y **un criterio superior no compensa uno inferior** (un botón de 180×48px supera el tamaño AAA pero la página puede seguir sin ser AA si el contraste del texto falla — cumplir AAA en una cosa no borra un fallo A/AA en otra). Si un proceso cumple todos los A pero falla uno AA, declara nivel A.

**Qué páginas/procesos entran**: la conformidad se evalúa en procesos *completos* — no se puede declarar AA en una compra dejando fuera el pago. Contenido de terceros (ej. una pasarela de pago) también cuenta como parte del proceso, aunque la haya construido otra empresa.

**Por qué un criterio es AAA**: los niveles no ordenan necesidades por importancia — simplemente hay requisitos AAA difíciles de aplicar a *todo* un sitio (por eso el W3C desaconseja exigir AAA global). Un alcance AA puede sumar compromisos AAA puntuales si el equipo los acuerda y los puede comprobar (ej. "44×44px en los botones principales de la app, aunque el alcance general sea AA") — un compromiso vago como "intentaremos cumplir algunos AAA" no es verificable.

**Documentar el alcance** (antes de diseñar/evaluar) — plantilla con: estándar+versión, nivel, qué entra (páginas/procesos completos/estados/tamaños), compromisos por encima del nivel (criterio+lugar+motivo), contenido de terceros, exclusiones (solo justificadas, una por una), cómo se comprueba (método+momento), fecha y responsable.

## 2.8 — WCAG y el diseño

**El proceso de 6 pasos** para organizar el trabajo desde la tarea de la persona: **necesidad → barrera → requisito → decisión → implementación → evaluación**. Ejemplo (Teresa, usa pulsador con barrido, quiere añadir una cesta a su compra): necesidad = frase sin soluciones; barrera = describe el *diseño*, no a la persona ("el botón Añadir solo aparece al pasar el ratón; el barrido nunca llega"); requisito = 2.1.1 Teclado (A); decisión = comportamiento observable ("el botón siempre visible, alcanzable con teclado, con el nombre del producto en su nombre accesible"); implementar = componente nativo + criterios de aceptación con desarrollo; evaluar = prueba con resultado ("¿se añade la cesta sin ratón, recorriendo con teclado y con barrido?").

Este mismo proceso aparece en el audio con terminología casi idéntica: identificar la necesidad real de la persona usuaria (no la del diseñador), observar la barrera desde el diseño, encontrar el requisito relacionado, traducirlo en decisión de diseño documentada, implementar y evaluar.

**De un criterio a una decisión comprobable**: "Los errores no dependerán solo del color" recoge el requisito pero deja la solución abierta; "Todo campo con error muestra un ícono de alerta, un mensaje en texto debajo del campo y un borde rojo #B3261E de 2px" es comprobable por cualquiera del equipo.

**Estados combinados**: un campo puede tener error *y* foco a la vez — si el indicador de foco se dibuja *sustituyendo* el borde (en vez de sumándose), el borde rojo de error desaparece justo cuando la persona vuelve a corregirlo, perdiendo la señal. Hay que diseñar y comprobar las combinaciones de estados, no cada estado por separado (el audio lo confirma: "normalmente no diseñamos las combinaciones, asumir que se van a combinar de la manera correcta no es la mejor alternativa").

**Relaciones del formulario que hay que documentar** (código ↔ tecnología de apoyo): etiqueta↔campo (sin ella, el lector solo dice "editar texto"), instrucción↔campo (formato esperado anunciado al llegar, sin tener que recorrer toda la página antes), error↔campo (el mensaje queda asociado, no hay que buscarlo). Técnicamente esto es el `label for=/id=` que vincula etiqueta e input (mencionado en el audio como ejemplo de HTML semántico básico que como diseñador conviene entender, sin necesidad de programarlo). Esto satisface **1.3.1 Información y relaciones (A)**.

**Cuándo validar** (WCAG no fija un único momento): al salir del campo (bueno para formato comprobable: correo, CP, fecha — riesgo: marcar "obligatorio" en un campo recién tabulado), al enviar (bueno para campos vacíos/checkboxes — riesgo: descubrir todos los errores juntos al final, exige resumen + llevar el foco al primero), mientras se escribe (solo para ayudas de progreso: fuerza de contraseña, caracteres restantes — riesgo: marcar error antes de terminar de escribir). Combinación recomendada: validar al salir del campo, y una vez mostrado el error, revalidar mientras se escribe para que desaparezca en cuanto se corrige.

**WCAG como argumento de revisión** — un comentario de revisión útil tiene 5 piezas: qué ves (localizado), a quién afecta y cómo, criterio+condición (número/nombre/nivel), la medida (contraste, píxeles, pasos), una propuesta (no definitiva, pero que demuestre que hay salida). Esto convierte "esto no es accesible" en algo específico y accionable, y da un lenguaje común con producto/desarrollo/QA (mencionado también en audio). **Reutilizar la solución**: si el mismo campo aparece en varias pantallas, reutilizar la solución y comprobar que sigue funcionando — 3.2.4 Identificación coherente (AA).

## 2.9 — Requisito y buena práctica

**3 preguntas para clasificar cualquier decisión**: (1) ¿lo pide un criterio en mi alcance? (si es A/AA dentro del alcance acordado = requisito; si es AAA fuera del alcance o no hay criterio = no lo es, por útil que sea); (2) ¿quién queda fuera si no lo hago?; (3) ¿cuánto cuesta y cuándo? (incluirlo ahora vs. cambiarlo después de publicado). Una preferencia estética (ej. redondear esquinas por marca) es otra categoría — no se propone para resolver una barrera.

**Tamaño de objetivo**: **2.5.8 (mínimo) AA = 24×24px CSS**; **2.5.5 (mejorado) AAA = 44×44px**. Si el alcance es AA y ya se cumple, ampliar a 44×44 es una mejora opcional del equipo, no una exigencia adicional del nivel AA (aunque si se adopta como compromiso, pasa a tener que cumplirse). El audio aporta un matiz práctico: en mobile, quedarse en 24×24 puede ser corto para la experiencia real aunque cumpla el mínimo.

**Contexto de un enlace — 2.4.4 (A)**: el propósito debe entenderse por el texto del enlace o por su "contexto determinable por programa" (la misma frase/párrafo/celda de tabla — no "lo que hay visualmente cerca"). Un "Más información" al final de un párrafo que describe un taller sí cumple; tres "Más información" sin relación textual con su contexto no cumplen; si cada uno sí tiene relación con su párrafo, cumplen 2.4.4 pero quien navega por lista de enlaces oirá 3 textos iguales — ahí entra **2.4.9 (AAA)**, que exige que el propósito se entienda solo por el texto del enlace mismo. El texto de *botones* lo cubre **2.4.6 (AA)**, no 2.4.4. Cambiar "Continuar" por "Confirmar reserva" en un diálogo es **buena práctica** (dice exactamente qué pasará), no corrección de un incumplimiento — si se adopta, conviene volverla regla del sistema de diseño.

**Plazos sin cálculo** (buena práctica, no requisito WCAG): decir "puedes cambiarla hasta el lunes 14 a las 10:00" en vez de "hasta 24h antes" — evita que la persona tenga que calcular. Referencia: *Making Content Usable for People with Cognitive and Learning Disabilities* (W3C).

## 2.10 — Diseñar con WCAG

Ejemplo completo aplicando el proceso de 6 pasos a un caso real: **Nerea** (dislexia, usa lectura en voz alta) necesita saber qué documentos reunir para una solicitud de ayuda al alquiler, pero la lista solo existe dentro de una infografía (imagen con texto dibujado) — no la lee su herramienta, no se puede ampliar sin pixelarse, no se puede copiar.

1. **Necesidad**: "Nerea quiere saber qué documentos tiene que reunir antes de empezar la solicitud" (sin soluciones todavía).
2. **Barrera**: describe el diseño, no a la persona — "la lista solo existe como texto dentro de una imagen". Afecta también a Andrés (lector de pantalla, no recibe nada) e Inés (ampliador, la ve borrosa) — la misma barrera golpea a perfiles distintos.
3. **Requisito**: **1.1.1 Contenido no textual (A)** (la imagen transmite información sin equivalente en texto) + **1.4.5 Imágenes de texto (AA)** (se usa imagen para presentar texto que podría ser texto real).
4. **Decisión**: la lista pasa a ser texto real en la página (componente de lista del sistema de diseño), no una imagen exportada; si se mantiene la infografía, no debe aportar información que no esté también en el texto.
5. **Implementar**: se acuerda con desarrollo y con quien redacta el contenido quién mantiene la lista y cómo se publica (como texto, no como imagen).
6. **Evaluar**: no solo comprobar el criterio técnico, sino la tarea original — ¿puede Nerea, con su lectura en voz alta, obtener la lista sin ayuda? Si no, se vuelve al paso 2.

**3 preguntas para auditar si la persona completa cada paso de un flujo** (más allá de los criterios técnicos del alcance): (1) **¿Encuentra lo que necesita?** (la info/control está a la vista con un nombre reconocible), (2) **¿Sabe cómo hacerlo?** (queda claro qué hacer y qué pasará), (3) **¿Reconoce el resultado?** (la pantalla deja claro si funcionó o qué falló). Aplicado al caso: en "Convocatoria", una respuesta-problema sería que Nerea tenga que pedirle a alguien que le lea la lista; en "Subir documentos", que los campos se llamen genéricamente "Documento 1"/"Documento 2"; en "Justificante", que diga "Operación realizada" sin número de registro ni fecha. Las preguntas se hacen desde la tarea y las herramientas de una persona *concreta*, no en abstracto — el equipo puede usarlas para preparar pruebas reales con personas usuarias de tecnología de apoyo.

## 2.11 — Documentar decisiones de accesibilidad

**Una decisión documentable tiene 4 piezas**: **Qué** (comportamiento observable), **Por qué** (necesidad + criterio con número/nivel si aplica), **Dónde** (componente/patrón/pantalla), **Cómo se comprueba** (prueba concreta). "Los errores del formulario serán accesibles" no es comprobable por nadie que no estuvo en la reunión; la versión con las 4 piezas sí lo es.

**Dónde documentar según el tipo de decisión**: regla general → sistema de diseño (ficha del componente/patrón); excepción de una pantalla puntual → especificación de esa pantalla; pregunta abierta/decisión con alternativas → registro de decisiones del equipo (con fecha y responsable). La especificación de pantalla también es donde se anota lo que el diseño no muestra visualmente pero desarrollo necesita (nombre de un botón de solo ícono, orden de recorrido, qué se anuncia al aparecer un error).

**Caso: etiqueta flotante** — si el nombre del campo solo vive en el placeholder, desaparece al escribir (viola **3.3.2**). Una etiqueta flotante (empieza dentro, sube al escribir — patrón tipo Material Design, mencionado también en audio) debe documentarse con: nunca desaparece; reducida sigue siendo legible (contraste 4,5:1 si es texto normal); el campo vacío no debe confundirse con uno lleno; las instrucciones de formato van *fuera* de la caja, visibles antes de escribir (no solo en el mensaje de error); el nombre accesible debe contener el texto visible (**2.5.3**, si no, el control por voz no lo encuentra).

**Caso: mensaje de error de login** — regla general: ser preciso (decir qué campo falla y cómo corregir), pero **3.3.3 (AA)** exime de sugerir corrección cuando compromete seguridad. En login, un mensaje único "El usuario o la contraseña no son correctos" (sin precisar cuál) se justifica por el riesgo de revelar si una cuenta existe — pero ese mismo riesgo *no* justifica esconder, por ejemplo, un error de formato en un código postal o una fecha. Aun con el mensaje genérico, debe seguir habiendo texto que diga que algo falló y un camino documentado para recuperar el acceso.

**Guion de 6 pasos para probar lo documentado** (en prototipo o producto real): 1) enviar mal a propósito (vacío, correo sin @, fecha con otro formato) y ver si aparece mensaje claro junto al campo; 2) mirar en escala de grises/blanco y negro para comprobar que el error no depende solo del color; 3) comprobar que los datos escritos se conservan tras un error; 4) recorrer solo con teclado (Tab, Shift+Tab, Intro, Espacio) verificando que se llega a todo y que el foco va al primer error al enviar; 5) comprobar que el formato esperado estaba visible *antes* de escribir, no solo al fallar; 6) preguntar lo que no se puede ver directamente (qué anuncia el lector de pantalla al aparecer/volver al error) — si no se puede probar, dejarlo como pregunta documentada para desarrollo con el resultado esperado.

---

## Guía de proyecto — después del Módulo 2

Para la tutoría de este módulo, el objetivo es tener avanzada la **matriz de requisitos** y haber **elegido las pantallas del flujo** (no hace falta tener todas las respuestas — se puede seguir completando en los próximos módulos):

1. **Preparar el archivo**: copia propia de la plantilla de Figma (no modificar la compartida), con la ficha de producto/briefing del Módulo 1.
2. **Delimitar el flujo**: una tarea concreta con inicio y final claros (ejemplos dados: pagar una factura, encontrar/reservar un viaje, pedir una cita médica). Orientación: **no más de 4 pantallas** por flujo — si crece, separar en flujos distintos.
3. **Completar la matriz de requisitos**: por cada barrera — qué problema, a quién afecta y en qué situación, qué criterio WCAG se relaciona (si ya se puede identificar), qué requisito exige la solución, qué decisión de diseño se propone. Si todavía no se puede asociar una barrera a un criterio, dejarlo pendiente y volver después — no hay que rellenar de memoria.
4. **Explorar el recorrido con bocetos** antes de pasar al acabado visual en Figma.
5. **Elegir los componentes a documentar en detalle**: **2 simples + 1 complejo** (ejemplos: botón o campo de formulario / calendario o pestañas), para **un solo dispositivo** (no hace falta cubrir escritorio+tablet+móvil todavía).
6. **Documentar conforme se avanza**: la interfaz y su recorrido (navegación por teclado, orden de foco, estructura de encabezados, info para lector de pantalla) + los 3 componentes elegidos (estados y comportamiento).

**Entrega**: enlace del archivo de Figma a soporte@weaaare.com, Discord, el grupo del intensivo o mensaje privado a Carlos — comprobando antes que el archivo tiene permisos de visualización.

**Recursos mencionados**: WAVE de WebAIM (estructura de encabezados/regiones), ATAG/UAAG (ya vistos en 2.1), COGA (accesibilidad cognitiva y del aprendizaje), WCAG-EM (metodología para definir alcance y muestra de evaluación), plantillas VPAT de ITI (para generar un informe de conformidad / ACR).
