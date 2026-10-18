---
title: "WCAG 2.2 Understanding — Principio 3: Comprensible (Understandable)"
status: in_progress
last_updated: 2026-10-13
---

# 3. Comprensible (Understandable)

> La información y el manejo de la interfaz de usuario deben ser comprensibles.

Fuente: [W3C WAI — Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/)

## 3.1 Legible

### 3.1.1 Idioma de la página (Nivel A)
**Qué pide:** Que se identifique programáticamente el idioma humano predominante de cada página web, de modo que los agentes de usuario y las tecnologías de asistencia puedan presentar correctamente el contenido lingüístico (pronunciación, visualización de caracteres, subtítulos sincronizados, etc.).
**Por qué importa:** Beneficia a usuarios de lectores de pantalla y tecnologías de texto a voz, que necesitan que se aplique la pronunciación correcta; a personas con dificultades de fluidez lectora que tienen problemas para reconocer caracteres y decodificar palabras; a personas con discapacidades cognitivas, de lenguaje y de aprendizaje que usan texto a voz; y a quienes dependen de subtítulos en medios sincronizados.
**Cómo cumplirlo:**
- Usar el atributo `lang` en el elemento `html` (método principal).
- En archivos PDF, establecer el idioma por defecto mediante la entrada `/Lang` del catálogo del documento.
- Especificar el idioma de pasajes específicos dentro de un PDF cuando corresponda.
- Opcionalmente, declarar el idioma también en encabezados HTTP.
**Ejemplos/notas:** Una página producida en Alemania, escrita en HTML, con contenido mayormente en alemán pero con fragmentos en inglés: el idioma humano por defecto se identifica como alemán (de) mediante el atributo `lang` en el elemento `html`.

### 3.1.2 Idioma de las partes (Nivel AA)
**Qué pide:** Que se identifique programáticamente el idioma de cada frase o pasaje del contenido cuando difiera del idioma predominante de la página, de modo que los agentes de usuario puedan presentarlo correctamente (pronunciación, dirección del texto, alfabeto, etc.). Se exceptúan nombres propios, términos técnicos, palabras de origen incierto y préstamos lingüísticos ya incorporados al idioma vernáculo.
**Por qué importa:** Permite a lectores de pantalla y herramientas de texto a voz aplicar las reglas de pronunciación correctas al cambiar de idioma, mejora el manejo de texto de derecha a izquierda frente a izquierda a derecha y distintos alfabetos, y hace el contenido más inteligible para usuarios con discapacidad que comprenden todos los idiomas presentes. También beneficia a personas con dificultades de fluidez lectora y a quienes dependen de subtítulos para detectar cambios de idioma en medios sincronizados.
**Cómo cumplirlo:**
- Usar atributos de idioma (`lang`) para marcar los cambios de idioma humano dentro del contenido.
- En PDF, especificar el idioma de pasajes o frases mediante entradas `Lang`.
- No es necesario marcar palabras o frases que ya forman parte del vocabulario vernáculo.
**Ejemplos/notas:** Una frase en alemán ("Treppenwitz der Weltgeschichte") incluida dentro de un texto en inglés debe marcarse con el atributo de idioma correspondiente; enlaces de navegación a versiones en otro idioma llevan su propio atributo `lang`; la palabra "podcast" usada en un texto en francés no necesita marcarse por estar aceptada como vernácula.

### 3.1.3 Palabras poco usuales (Nivel AAA)
**Qué pide:** Proporcionar una forma de identificar el significado específico de palabras o frases usadas de manera inusual, idiomática o especializada (jerga), especialmente cuando el contenido especializado está dirigido a lectores no especialistas.
**Por qué importa:** Ayuda a personas con discapacidades cognitivas, de lenguaje y de aprendizaje que tienen dificultades para decodificar o comprender palabras, y a personas con discapacidad visual que usan magnificación de pantalla, ya que el zoom aísla las palabras del contexto circundante que de otro modo ayudaría a aclarar su significado.
**Cómo cumplirlo:**
- Para palabras con un único significado especial: ofrecer una definición en la primera aparición, mediante enlaces a definiciones, glosarios, definiciones en línea o funciones de búsqueda.
- Para palabras con múltiples significados: ofrecer la definición correspondiente en cada aparición, usando listas de descripción, el elemento HTML `dfn`, o glosarios.
- Explicaciones entre paréntesis o notas al pie también son formas válidas de implementación.
**Ejemplos/notas:** Enlazar un término técnico ("StickyKeys") a su definición en un glosario; usar la definición de WCAG del término "texto" enlazada a un glosario; proporcionar definiciones estilo nota al pie al final de la página con enlaces internos correspondientes.

### 3.1.4 Abreviaturas (Nivel AAA)
**Qué pide:** Ofrecer un mecanismo para identificar el significado completo de las abreviaturas usadas en el contenido. Quedan exentas las abreviaturas que ya se incorporaron al idioma como palabras propias (por ejemplo "láser") o nombres de organizaciones muy conocidos (IBM, NASA).
**Por qué importa:** Ayuda a personas con dificultad para decodificar palabras, a personas con discapacidad visual que usan magnificadores de pantalla (que reducen las pistas de contexto), y a quienes tienen memoria limitada o dificultad para usar el contexto como ayuda de comprensión.
**Cómo cumplirlo:**
- Si la abreviatura tiene un único significado: dar su expansión en la primera aparición (directamente junto a ella, con un enlace, glosario o función de diccionario en línea).
- Si tiene múltiples significados posibles: dar la expansión correspondiente en todas las apariciones relevantes.
- Como práctica recomendada (no obligatoria), usar el elemento HTML `<abbr>` para marcar abreviaturas.
**Ejemplos/notas:** La página del W3C muestra "W3C" con su expansión completa entre paréntesis; sitios médicos que ofrecen diccionarios especializados en cascada seguidos de recursos generales; servicios de búsqueda de acrónimos en línea que permiten consultar posibles expansiones.

### 3.1.5 Nivel de lectura (Nivel AAA)
**Qué pide:** Que cuando, tras quitar nombres propios y títulos, el texto requiera un nivel de lectura superior a la educación secundaria baja (aproximadamente nueve años de escolaridad), se ofrezca contenido suplementario o una versión alternativa que no exija ese nivel de lectura avanzado.
**Por qué importa:** Ayuda a personas con "dificultad para comprender e interpretar lenguaje escrito (por ejemplo, artículos, instrucciones o periódicos en texto o braille), con el propósito de obtener conocimiento general o información específica", incluyendo a personas muy instruidas que igualmente tienen discapacidades de lectura.
**Cómo cumplirlo:**
- Proporcionar resúmenes de texto con un nivel de lectura de educación secundaria baja.
- Incluir ilustraciones visuales, imágenes y símbolos de apoyo.
- Ofrecer versiones habladas del contenido textual.
- Simplificar la redacción del texto en general.
- Ofrecer interpretación en lengua de señas.
**Ejemplos/notas:** Revistas científicas que ofrecen resúmenes en lenguaje sencillo de artículos técnicos; sitios médicos que explican descubrimientos con lenguaje accesible y metadatos que indican el nivel educativo requerido; aplicaciones de e-learning que ofrecen contenido en múltiples formatos con metadatos que coinciden con la capacidad lectora del estudiante.

### 3.1.6 Pronunciación (Nivel AAA)
**Qué pide:** Ofrecer un mecanismo para identificar la pronunciación específica de palabras cuando el significado del texto es ambiguo sin conocer esa pronunciación (por ejemplo, heterónimos, o caracteres con múltiples lecturas posibles, como ciertos kanji japoneses) y el contexto por sí solo no permite resolver la ambigüedad.
**Por qué importa:** Ayuda a personas ciegas, con baja visión o con discapacidades de lectura que tienen dificultad para decodificar palabras, dificultad para usar pistas de contexto, o que dependen de tecnologías que leen el contenido en voz alta.
**Cómo cumplirlo:**
- Proporcionar la pronunciación inmediatamente después de la palabra ambigua.
- Enlazar a recursos externos de pronunciación.
- Incluir datos de pronunciación en glosarios.
- Usar marcas diacríticas estándar que puedan desactivarse si no se necesitan.
- Emplear el elemento HTML `ruby` para anotaciones fonéticas.
**Ejemplos/notas:** Contenido web en japonés que incluye kana (caracteres fonéticos) junto al kanji; uso del elemento HTML `ruby` para mostrar la pronunciación encima de los caracteres; enlaces a archivos de audio para palabras específicas; entradas de glosario con guía de pronunciación; texto multilingüe que indica la lectura correcta de caracteres compartidos entre idiomas.

## 3.2 Predecible

### 3.2.1 Al recibir el foco (Nivel A)
**Qué pide:** Garantizar que la funcionalidad del contenido sea predecible cuando los componentes reciben el foco. No deben producirse cambios de contexto no solicitados (envío automático de formularios, apertura de nuevas ventanas, desplazamiento del foco a otros controles) por el simple hecho de que un elemento reciba el foco del teclado.
**Por qué importa:** Ayuda a personas con discapacidades visuales, limitaciones cognitivas y discapacidades motrices, reduciendo la probabilidad de que un cambio de contexto ocurra de forma inesperada mientras navegan con teclado o tecnología de asistencia.
**Cómo cumplirlo:**
- Usar la "activación" (presionar Enter/espacio o hacer clic) como disparador de cambios de contexto, nunca el simple hecho de recibir el foco.
- Un menú desplegable solo debe navegar cuando el usuario lo activa explícitamente, no al enfocarlo.
**Ejemplos/notas:** Un diálogo de ayuda que se abre automáticamente al recibir el foco constituye un fallo de este criterio; en cambio, un menú que requiere activación explícita (Enter/espacio) para navegar lo cumple.

### 3.2.2 Al recibir entradas (Nivel A)
**Qué pide:** Que introducir datos o seleccionar un control de formulario tenga efectos predecibles; los cambios en la configuración de un componente no deben provocar cambios de contexto inesperados sin advertencia previa.
**Por qué importa:** Las personas con discapacidades visuales o cognitivas pueden desorientarse gravemente ante cambios de contexto inesperados. Quienes tienen baja visión no siempre detectan cambios visuales (como ventanas emergentes), por lo que anticipar estos cambios reduce la confusión.
**Cómo cumplirlo:**
- Proporcionar un botón de envío explícito para iniciar cambios de contexto, en vez de que ocurran automáticamente.
- Describir con anticipación qué ocurrirá antes de que se produzca un cambio de contexto.
- Permitir eventos `onchange` en elementos `select` sin que disparen cambios de contexto por sí mismos.
**Ejemplos/notas:** Un formulario de calendario que muestra campos adicionales según el tipo de evento (reunión, cita, recordatorio) sin alterar la estructura general; o campos de teléfono que desplazan el foco automáticamente entre área, prefijo y número, siempre que este comportamiento se explique previamente al usuario.

### 3.2.3 Navegación coherente (Nivel AA)
**Qué pide:** Que los mecanismos de navegación repetidos en múltiples páginas aparezcan en el mismo orden relativo cada vez que se presentan, salvo que el usuario inicie un cambio.
**Por qué importa:** Favorece a personas con baja visión que usan ampliación de pantalla, usuarios con buena memoria visual-espacial y personas ciegas que navegan de forma secuencial, así como a quienes tienen limitaciones cognitivas o discapacidades intelectuales. Les permite predecir la ubicación del contenido que buscan y encontrarlo más rápido.
**Cómo cumplirlo:**
- Presentar los componentes repetidos (menús, barras de navegación, buscadores) en el mismo orden relativo en todas las páginas del conjunto.
**Ejemplos/notas:** Un campo de búsqueda ubicado siempre en la última posición de cada página; un menú de navegación expandible con subnavegación consistente; un enlace "saltar navegación" presente siempre como primer enlace del sitio.

### 3.2.4 Identificación coherente (Nivel AA)
**Qué pide:** Que los componentes con la misma funcionalidad dentro de un conjunto de páginas se identifiquen de manera consistente (mismas etiquetas, nombres o textos alternativos), para que los usuarios reconozcan de inmediato funcionalidades ya conocidas.
**Por qué importa:** Permite reutilizar el conocimiento adquirido en interacciones previas, reduciendo el esfuerzo cognitivo necesario para ubicar y comprender funcionalidades familiares. Beneficia especialmente a personas con discapacidades cognitivas y a usuarios de tecnologías de asistencia, para quienes la presentación predecible facilita entender y operar el contenido.
**Cómo cumplirlo:**
- Usar etiquetas, nombres y alternativas de texto consistentes para componentes con la misma función.
- No es necesario que los identificadores sean idénticos palabra por palabra, siempre que reflejen adecuadamente el contexto.
**Ejemplos/notas:** Un botón "Buscar" identificado igual en todo el sitio; íconos de "guardar" con el mismo texto alternativo en distintas páginas; un enlace "Página 4" que en la siguiente página se llama "Página anterior" — las etiquetas difieren pero la funcionalidad se reconoce igual.

### 3.2.5 Cambio a petición (Nivel AAA)
**Qué pide:** Dar a los usuarios control total sobre los cambios de contexto, de modo que estos solo ocurran cuando el usuario los solicita explícitamente (nunca de forma automática o inesperada).
**Por qué importa:** Elimina la confusión causada por cambios inesperados (ventanas emergentes, envíos automáticos de formularios), que afectan particularmente a personas con discapacidades motrices, visuales o cognitivas. Quienes no pueden detectar cambios de contexto tienen menos probabilidad de desorientarse si son ellos quienes lo inician.
**Cómo cumplirlo:**
- Para actualizaciones automáticas de contenido, ofrecer un botón "Actualizar ahora" en vez de refrescar sin aviso.
- Usar redirecciones del lado del servidor en lugar de redirecciones automáticas del cliente.
- Abrir ventanas emergentes únicamente cuando el usuario lo solicita de forma explícita.
- Evitar que los elementos `select` disparen cambios de contexto al cambiar de opción.
**Ejemplos/notas:** En vez de actualizar contenido automáticamente, el autor ofrece un botón "Actualizar ahora" que solicita el refresco del contenido cuando el usuario lo decide.

### 3.2.6 Ayuda coherente (Nivel A)
**Qué pide:** Garantizar que, cuando existan mecanismos de ayuda (contacto, chat, FAQ) repetidos en varias páginas de un mismo conjunto, aparezcan en el mismo orden relativo respecto al resto del contenido, salvo que el usuario inicie un cambio.
**Por qué importa:** Las personas que tienen dificultad para localizar ayuda tienen más probabilidades de encontrarla si está ubicada de forma consistente. Permite que usuarios con discapacidades cognitivas reserven su energía para la tarea en sí, en lugar de tener que buscar el soporte, posibilitando completar tareas incluso ante dificultades.
**Cómo cumplirlo:**
- Ubicar un enlace de contacto ("contáctenos") en la misma posición a través de todo el sitio.
**Ejemplos/notas:** Un formulario de empleo con información de contacto siempre en el mismo lugar permite a los solicitantes aclarar dudas; una opción de chat ubicada consistentemente en un sistema de agendamiento médico facilita la interacción; una página "Cómo hago..." siempre accesible desde el mismo sitio ayuda a empleados a localizar procedimientos.

## 3.3 Asistencia para la entrada de datos

### 3.3.1 Identificación de errores (Nivel A)
**Qué pide:** Que cuando se detecta automáticamente un error de entrada, se identifique el elemento erróneo y el error se describa al usuario mediante texto (no solo mediante color o volver a mostrar el formulario sin indicación de fallo).
**Por qué importa:** Las personas con discapacidad visual necesitan descripciones textuales para percibir que ocurrió un error; quienes tienen deficiencias en la percepción del color no pueden depender de indicaciones solo cromáticas; y las personas con discapacidades cognitivas y de aprendizaje necesitan esa información para comprender por qué falló el envío.
**Cómo cumplirlo:**
- Ante campos obligatorios no completados, proporcionar descripciones textuales que identifiquen esos campos, y usar `aria-invalid` para marcarlos.
- Cuando se requiere un formato o valor específico, usar descripciones textuales del error o un `alertdialog`/región viva de ARIA.
**Ejemplos/notas:** Un formulario de reserva de aerolínea que, ante campos incompletos o incorrectos, muestra una alerta señalando específicamente cuáles presentan problemas.

### 3.3.2 Etiquetas o instrucciones (Nivel A)
**Qué pide:** Presentar etiquetas o instrucciones que identifiquen los controles de un formulario, para que el usuario sepa qué dato se espera en cada campo, equilibrando que no falte información pero tampoco sature la página.
**Por qué importa:** Ayuda a todos los usuarios, especialmente a quienes tienen discapacidades cognitivas, del lenguaje y de aprendizaje, a ingresar la información correctamente. Proporcionar etiquetas e instrucciones claras evita envíos incompletos o incorrectos y la necesidad de volver a navegar para corregir errores.
**Cómo cumplirlo:**
- Asociar el elemento `label` con su control mediante atributos.
- Proporcionar etiquetas descriptivas.
- Agrupar controles relacionados con `fieldset` y `legend`.
- Indicar el formato de dato esperado junto con ejemplos.
**Ejemplos/notas:** Un campo de estado con lista desplegable de abreviaturas; un campo de fecha con instrucciones de formato explícitas; un campo de teléfono dividido en tres partes agrupadas con `fieldset` y etiquetas ocultas mediante el atributo `title`.

### 3.3.3 Sugerencia ante errores (Nivel AA)
**Qué pide:** Que, si se detecta automáticamente un error de entrada y se conocen sugerencias de corrección, estas se proporcionen al usuario (salvo que comprometan la seguridad o el propósito del contenido).
**Por qué importa:** Las personas con limitaciones cognitivas o discapacidades visuales tienen dificultades para comprender cómo corregir un error en un formulario, lo que puede llevarlas a abandonar el proceso sin orientación clara. También reduce, para personas con limitaciones motrices, la necesidad de corregir un valor varias veces.
**Cómo cumplirlo:**
- Cuando se requiere un formato específico, usar descripciones textuales del error, un `alertdialog` de ARIA, o sugerir el texto de corrección.
- Cuando el valor pertenece a un conjunto limitado de opciones válidas, ofrecer la lista de valores aceptables o una interpretación del dato ingresado.
**Ejemplos/notas:** Si un campo pide el nombre del mes y el usuario ingresa "12", se puede ofrecer la lista completa de meses o una sugerencia interpretativa del tipo "¿Quisiste decir 'diciembre'?".

### 3.3.4 Prevención de errores (legales, financieros, de datos) (Nivel AA)
**Qué pide:** Para páginas que generan compromisos legales, transacciones financieras, o que permiten modificar/eliminar datos controlables por el usuario, o que envían respuestas a pruebas, asegurar que las acciones sean reversibles, se verifiquen y permitan corregir errores, o se puedan confirmar/revisar antes de finalizar.
**Por qué importa:** Las personas con discapacidades tienen mayor probabilidad de cometer errores; por ejemplo, quienes tienen dislexia pueden transponer números, y quienes tienen discapacidades motrices pueden presionar teclas por accidente. Proveer salvaguardas ayuda a usuarios con todas las discapacidades a evitar consecuencias graves.
**Cómo cumplirlo:**
- Para transacciones legales/financieras: permitir revisar y corregir antes de enviar, dar una ventana de tiempo para enmendar la solicitud, o usar casillas de confirmación junto al botón de envío.
- Para eliminación de datos: permitir recuperar información eliminada o solicitar confirmación antes de continuar.
- Para pruebas/exámenes: facilitar la revisión de respuestas o solicitar confirmación antes del envío final.
**Ejemplos/notas:** Un comercio minorista que muestra el detalle del pedido para que el cliente lo inspeccione antes de confirmar la compra; un sistema de venta de acciones que advierte sobre operaciones fuera de horario de mercado y ofrece cancelar o confirmar.

### 3.3.5 Ayuda (Nivel AAA)
**Qué pide:** Ofrecer ayuda contextual sensible al contenido, disponible para cada paso de un proceso, de modo que el usuario comprenda cómo completar una acción sin perder el hilo de lo que estaba haciendo. Solo debe proporcionarse cuando las etiquetas por sí solas no sean suficientes.
**Por qué importa:** Algunos usuarios con discapacidades tienen más probabilidades de cometer errores que quienes no las tienen. Ayuda especialmente a personas con discapacidades de escritura y lectura (que a menudo tienen dificultad para redactar texto en formularios) y a personas mayores con dificultades similares de entrada de texto o manejo del ratón.
**Cómo cumplirlo:**
- Para entrada de texto general: ofrecer enlaces de ayuda en la página, asistentes integrados, corrección ortográfica con sugerencias, o instrucciones de texto al inicio del formulario.
- Para formatos de datos específicos: indicar el formato esperado con ejemplos e instrucciones descriptivas.
**Ejemplos/notas:** Una solicitud de empleo en línea que incluye enlaces de ayuda junto a cada pregunta compleja, ofreciendo instrucciones y explicaciones contextuales.

### 3.3.6 Prevención de errores (todos) (Nivel AAA)
**Qué pide:** Extender las mismas salvaguardas del criterio 3.3.4 (reversibilidad, verificación o confirmación) a todos los formularios que requieren que el usuario envíe información, no solo a los de naturaleza legal, financiera o de datos.
**Por qué importa:** Proporcionar salvaguardas beneficia a usuarios con todas las discapacidades que puedan ser más propensos a cometer errores: personas con discapacidades de lectura pueden transponer números y letras, y personas con discapacidades motrices pueden presionar teclas accidentalmente.
**Cómo cumplirlo:**
- Aplicar las mismas técnicas suficientes del criterio 3.3.4 a cualquier formulario con envío de datos.
- Garantizar que los envíos sean reversibles, se verifiquen automáticamente con oportunidad de corrección, o se puedan revisar y confirmar antes de finalizar.
**Ejemplos/notas:** Se apoya en los mismos ejemplos y técnicas que 3.3.4, pero sin limitarse a contextos legales/financieros/de datos.

### 3.3.7 Entrada redundante (Nivel A)
**Qué pide:** En procesos de varios pasos, no solicitar información que el usuario ya haya proporcionado previamente en el mismo proceso, salvo que sea necesario por razones de seguridad, haya dejado de ser válida, o la información ya no sea necesaria.
**Por qué importa:** Reduce el esfuerzo cognitivo de recordar datos ya ingresados; beneficia a personas con dificultades de memoria a corto plazo (típicas de ciertas discapacidades cognitivas), que de otro modo sufrirían fatiga mental y mayor riesgo de error, y a personas con discapacidades motrices al reducir la necesidad de reescribir texto.
**Cómo cumplirlo:**
- Reutilizar automáticamente los datos de un paso anterior del proceso, por ejemplo precompletando el campo.
- No solicitar dos veces la misma información.
**Ejemplos/notas:** Un formulario que pide el ID corporativo en el paso 1 y lo vuelve a mostrar precompletado (editable) en el paso 3; una tienda en línea que permite marcar que la dirección de envío es igual a la de facturación; un buscador que precompleta el término de búsqueda previo dentro del mismo proceso.

### 3.3.8 Autenticación accesible (mínimo) (Nivel AA)
**Qué pide:** Para procesos de autenticación de usuarios ya existentes (no de alta de cuenta), ofrecer al menos un método que no dependa de una prueba de función cognitiva (memorizar una contraseña, resolver un puzle, transcribir texto), salvo excepciones como reconocimiento de objetos o contenido provisto por el propio usuario.
**Por qué importa:** Memorizar un nombre de usuario y contraseña impone una carga muy alta, a veces imposible, para personas con ciertas discapacidades cognitivas relacionadas con la memoria, la lectura (p. ej. dislexia), los números (p. ej. discalculia) o el procesamiento perceptual. Permite autenticarse sin importar el nivel de habilidad cognitiva.
**Cómo cumplirlo:**
- Etiquetar correctamente los campos de correo/contraseña para habilitar gestores de contraseñas.
- No bloquear la función de copiar y pegar en los campos de login.
- Implementar WebAuthn (autenticación biométrica o por dispositivo).
- Ofrecer inicio de sesión mediante terceros con OAuth.
- Permitir autenticación multifactor con múltiples opciones.
**Ejemplos/notas:** El navegador del usuario o una extensión de gestor de contraseñas puede identificar el propósito de los campos y rellenarlos automáticamente.

### 3.3.9 Autenticación accesible (mejorado) (Nivel AAA)
**Qué pide:** Igual que 3.3.8, pero sin ninguna excepción: se prohíbe por completo exigir reconocimiento de imágenes, video o audio (incluso contenido provisto por el propio usuario) como parte del proceso de autenticación.
**Por qué importa:** El propósito es asegurar un método de inicio de sesión accesible, fácil de usar y seguro para acceder a contenido y realizar tareas. Beneficia a personas con problemas cognitivos de memoria, lectura (dislexia), números (discalculia) o procesamiento perceptual, permitiéndoles autenticarse sin importar su nivel de habilidad cognitiva.
**Cómo cumplirlo:**
- Usar campos de correo y contraseña correctamente marcados que permitan autocompletado.
- No bloquear la funcionalidad de pegado para permitir gestores de contraseñas.
- Implementar WebAuthn para autenticación sin contraseña.
- Ofrecer login por terceros mediante OAuth.
- Proveer múltiples opciones de autenticación de dos factores.
**Ejemplos/notas:** Autorrelleno de credenciales, gestores de contraseñas, autenticación biométrica vía WebAuthn, OAuth, autenticación por llave USB con botón, y códigos QR para confirmar identidad.
