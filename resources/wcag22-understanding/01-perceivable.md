---
title: "WCAG 2.2 Understanding — Principio 1: Perceptible (Perceivable)"
status: in_progress
last_updated: 2026-10-13
---

# 1. Perceptible (Perceivable)

> La información y los componentes de la interfaz de usuario deben poder presentarse a los usuarios de formas que puedan percibir.

Fuente: [W3C WAI — Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/)

## 1.1 Alternativas textuales

### 1.1.1 Contenido no textual (Nivel A)
**Qué pide:** Que todo contenido no textual que se presenta al usuario tenga una alternativa textual que cumpla el mismo propósito, de modo que la información pueda renderizarse por cualquier canal sensorial (visual, auditivo o táctil) según las necesidades de la persona. El objetivo es que el contenido pueda reformatearse y presentarse de distintas maneras sin perder su función.
**Por qué importa:** Beneficia a personas ciegas o con baja visión que usan lectores de pantalla o líneas braille; a personas con dificultades auditivas que necesitan texto en lugar de audio; a personas con discapacidades cognitivas o de aprendizaje que se benefician de múltiples formas de presentación; y en general permite que el contenido se pueda buscar, traducir o reutilizar con mayor facilidad.
**Cómo cumplirlo:**
- Imágenes y gráficos simples: usar atributo `alt`, etiquetas ARIA o texto adyacente que describa el propósito y contenido.
- Diagramas o gráficos complejos: combinar una etiqueta corta con una descripción larga (texto cercano, documento enlazado o `aria-describedby`).
- Elementos interactivos (botones, mapas de imagen): dar nombres descriptivos que identifiquen propósito y función.
- Contenido decorativo: marcarlo como decorativo (alt vacío o CSS de fondo) para que la tecnología asistiva lo ignore.
- CAPTCHAs: ofrecer alternativas en otra modalidad (visual y auditiva) junto con una descripción del propósito.
**Ejemplos/notas:** Gráficos de barras acompañados de tablas de datos; discursos en audio enlazados a transcripciones completas; planos interactivos con etiquetas descriptivas; fotografías con descripciones contextuales acordes a su uso; animaciones con una breve descripción que remite a un texto tutorial de apoyo.

## 1.2 Medios tempodependientes (audio y video)

### 1.2.1 Solo audio y solo video (grabado) (Nivel A)
**Qué pide:** Para contenido grabado de solo audio, ofrecer una alternativa textual; para contenido grabado de solo video, ofrecer una alternativa textual o una pista de audio que describa la información visual importante. Reconoce que el texto puede rendirizarse en cualquier modalidad sensorial según la necesidad del usuario.
**Por qué importa:** Permite a personas ciegas o con baja visión acceder mediante tecnología asistida que lee, muestra o convierte a braille el texto; ayuda a personas con discapacidades cognitivas, de lenguaje o aprendizaje gracias a presentaciones paralelas en texto; permite a personas sordas o con hipoacusia leer alternativas textuales; y a personas sordociegas acceder en braille. También facilita la búsqueda y reutilización del contenido.
**Cómo cumplirlo:**
- Solo audio: proporcionar una alternativa textual del medio tempodependiente (transcripción).
- Solo video: proporcionar una alternativa textual O una pista de audio que describa la información visual relevante.
**Ejemplos/notas:** Un clip de audio con un enlace a la transcripción inmediatamente después; la grabación de una conferencia de prensa con transcripción literal que identifica a los oradores y señala sonidos relevantes; una animación muda con una breve descripción que remite a un texto tutorial; una película muda a la que se añade una pista de audio que describe la acción visual.

### 1.2.2 Subtítulos (Prerecorded) (Nivel A)
**Qué pide:** Proporcionar subtítulos para todo contenido de audio pregrabado dentro de medios sincronizados, de modo que las personas sordas o con hipoacusia puedan acceder a la información auditiva. Los subtítulos deben incluir no solo los diálogos sino también la identificación de hablantes y efectos sonoros significativos.
**Por qué importa:** El principal grupo beneficiado son las personas sordas o con pérdida auditiva, que pueden acceder así a la información del audio sincronizado.
**Cómo cumplirlo:**
- Subtítulos abiertos: siempre visibles, incrustados en el video.
- Subtítulos cerrados: activables/desactivables por el usuario, mediante SMIL, el elemento `<track>` de HTML5, o reproductores multimedia estándar compatibles con subtítulos.
**Ejemplos/notas:** Un tutorial de nudos con subtítulos del tipo "(música) Usar cuerda para hacer nudos era una habilidad importante para marineros, soldados..."; interpretaciones de orquesta que subtitulan música no vocal con el compositor, el título y frases descriptivas como "♪ Melodía calma con tempo lento ♪".

### 1.2.3 Audiodescripción o alternativa en medios (grabado) (Nivel A)
**Qué pide:** Ofrecer una alternativa para que personas ciegas o con discapacidad visual accedan a la información visual de medios sincronizados: ya sea audiodescripción (que se añade en las pausas del diálogo) o una alternativa textual completa (tipo guion) que describa secuencialmente todo el contenido visual y auditivo. La alternativa textual completa ofrece una cobertura más amplia que la sola audiodescripción.
**Por qué importa:** Beneficia principalmente a personas ciegas, con baja visión o con dificultad para percibir o comprender imágenes en movimiento, ayudándolas a seguir contenido de video u otros medios sincronizados.
**Cómo cumplirlo:**
- Proporcionar audiodescripción mediante una pista de audio seleccionable o una versión separada del video.
- Crear una alternativa textual completa tipo guion para el medio tempodependiente.
- Incorporar audiodescripciones usando tecnología SMIL.
- Proporcionar audiodescripción extendida cuando las pausas estándar no alcanzan.
**Ejemplos/notas:** Video educativo en el que un docente muestra formas de picos de aves con palitos de madera; un narrador añade descripciones como "Un docente muestra fotografías de aves con picos largos y delgados" durante las pausas del diálogo, completando la información visual para quienes no pueden verla.

### 1.2.4 Subtítulos (en directo) (Nivel AA)
**Qué pide:** Proporcionar subtítulos para todo el audio en directo de medios sincronizados, permitiendo a personas sordas o con hipoacusia acceder a presentaciones en tiempo real. Se aplica a medios sincronizados transmitidos, pero excluye llamadas multimedia bidireccionales entre personas a través de aplicaciones web.
**Por qué importa:** Permite a personas sordas o con pérdida auditiva acceder a la información auditiva de video en directo, haciendo accesibles presentaciones y transmisiones en vivo.
**Cómo cumplirlo:**
- Crear subtítulos para medios sincronizados en directo, abiertos (siempre visibles) o cerrados (activables) usando SMIL 1.0/2.0 u otros formatos compatibles con subtitulado cerrado.
- Usar servicios de subtitulado en tiempo real como CART (Communication Access Realtime Translation) para capturar diálogos, letras y descripciones de sonido al instante.
**Ejemplos/notas:** Un noticiero que transmite en vivo con subtítulos; una orquesta que usa subtitulado CART durante presentaciones web en vivo, identificando letras, diálogos, y títulos y compositores de las piezas musicales.

### 1.2.5 Audiodescripción (grabado) (Nivel AA)
**Qué pide:** Proporcionar audiodescripción para todo contenido de video pregrabado en medios sincronizados, de modo que personas ciegas o con baja visión accedan a la información visual (acciones, personajes, cambios de escena, texto en pantalla) mediante narración añadida en las pausas naturales del diálogo. Si la información visual importante ya se transmite por el audio existente, no es necesaria descripción adicional.
**Por qué importa:** Beneficia a personas ciegas o con baja visión, y también a personas con limitaciones cognitivas que tienen dificultad para interpretar contenido visual, dándoles acceso a detalles visuales esenciales mediante narración descriptiva.
**Cómo cumplirlo:**
- Proporcionar una pista de audio seleccionable con las descripciones.
- Crear una versión alternativa del video con las audiodescripciones integradas.
- Usar SMIL para incrustar las descripciones.
- Incorporar la narración directamente en la pista de sonido.
- Proporcionar audiodescripción extendida con pausas de video cuando sea necesario.
- Usar el elemento `track` de HTML para las audiodescripciones.
**Ejemplos/notas:** Mismo video educativo del criterio 1.2.3: un narrador describe "El docente entrega a cada estudiante dos palitos de madera planos y delgados" mientras el instructor habla, intercalando la descripción en las pausas naturales.

### 1.2.6 Lengua de señas (grabado) (Nivel AAA)
**Qué pide:** Hacer accesibles los medios sincronizados a personas sordas o con hipoacusia cuya lengua principal es la lengua de señas, reconociendo que esta transmite matices emocionales y entonación que los subtítulos escritos no pueden capturar, y que suele procesarse más rápido que la lectura para quienes la dominan.
**Por qué importa:** Beneficia principalmente a personas cuya lengua principal es la lengua de señas, en especial aquellas con competencia lectora limitada, que de otro modo no podrían comprender los subtítulos y necesitan interpretación en lengua de señas para acceder al contenido.
**Cómo cumplirlo:**
- Incluir directamente a un intérprete de lengua de señas visible dentro de la transmisión de video.
- Proporcionar al intérprete como un video separado y sincronizado, mostrado en una superposición o ventana aparte, coordinado mediante tecnología SMIL.
**Ejemplos/notas:** Una empresa transmite un comunicado a empleados con un intérprete de lengua de señas superpuesto en una esquina de la pantalla; una universidad graba una clase incorporando en posproducción interpretación en lengua de señas sincronizada con la presentación del profesor.

### 1.2.7 Audiodescripción extendida (grabado) (Nivel AAA)
**Qué pide:** Dar a personas ciegas o con baja visión un acceso más profundo a medios sincronizados permitiendo que el video se pause temporalmente mientras se proveen audiodescripciones detalladas, en lugar de depender solo de descripciones breves comprimidas en las pausas del diálogo.
**Por qué importa:** Beneficia a personas ciegas, con baja visión, o con dificultades cognitivas para interpretar información visual, cuando la audiodescripción estándar resulta insuficiente por exceso de diálogo, aportando "la información adicional necesaria para comprender el video".
**Cómo cumplirlo:**
- Crear audiodescripciones extendidas usando SMIL (implementaciones SMIL 1.0 y 2.0).
- Como técnica recomendada (no suficiente por sí sola), usar el elemento `track` de HTML para audiodescripciones.
**Ejemplos/notas:** Una clase de física en la que el profesor dibuja rápidamente en un pizarrón mientras habla: el video se pausa entre problemas para proveer audiodescripción extendida de los dibujos y gestos antes de reanudar la reproducción.

### 1.2.8 Alternativa a los medios (grabado) (Nivel AAA)
**Qué pide:** Hacer accesible contenido audiovisual a personas con discapacidad visual y auditiva combinadas, proporcionando toda la información del medio sincronizado (visual y auditiva) en formato texto, de manera que se pueda leer de forma secuencial como un libro, describiendo todos los detalles visuales, acciones, expresiones, sonidos no verbales y diálogos.
**Por qué importa:** Beneficia principalmente a personas sordociegas que no pueden leer subtítulos de forma confiable ni oír el diálogo, a personas con pérdida severa de visión y audición que necesitan formatos alternativos, y a usuarios que acceden al contenido a su propio ritmo mediante líneas braille u otra tecnología asistida.
**Cómo cumplirlo:**
- Para medios sincronizados: proporcionar una alternativa textual completa, enlazada junto al contenido.
- Para contenido de solo video: crear alternativas en formato texto del medio tempodependiente.
- Enlazar transcripciones completas que incluyan descripciones, diálogos y elementos de audio no verbal.
**Ejemplos/notas:** Un centro comunitario ofrece un video de capacitación sobre nueva tecnología y crea una alternativa textual completa para que personas con discapacidad visual y auditiva combinada puedan comprender las demostraciones y explicaciones que las personas videntes/oyentes perciben directamente.

### 1.2.9 Solo audio (en directo) (Nivel AAA)
**Qué pide:** Hacer accesible el contenido de audio en directo a personas sordas, con hipoacusia o que no puedan oír el audio de otra manera, preferentemente mediante subtitulado en tiempo real (en lugar de una transcripción fija), ya que los subtítulos en vivo avanzan al mismo ritmo que el audio y se adaptan a desviaciones del guion.
**Por qué importa:** Permite a personas que no pueden percibir o comprender audio en tiempo real acceder a información equivalente mediante texto, facilitando la participación en eventos en vivo como conferencias web, discursos y transmisiones radiales.
**Cómo cumplirlo:**
- Incorporar un servicio de subtitulado en vivo (taquígrafos o servicios de captioning) que genere texto en tiempo real durante la transmisión del audio.
- Proveer una transcripción textual cuando el contenido sigue un guion establecido (opción menos preferida que el subtitulado en vivo).
- Usar tecnología de transmisión de medios accesible que combine audio con texto o gráficos sincronizados.
**Ejemplos/notas:** Agencias de relaciones públicas que usan servicios de subtitulado web para eventos en vivo mostrados en subframes de la página; producciones teatrales que enlazan el guion cuando los actores siguen un texto preparado; servidores de streaming con subtítulos en vivo generados por taquígrafos; comunicados de prensa distribuidos simultáneamente como transcripción cuando no se puede organizar subtitulado en vivo.

## 1.3 Adaptable

### 1.3.1 Información y relaciones (Nivel A)
**Qué pide:** Que la información, estructura y relaciones transmitidas mediante la presentación visual o auditiva puedan determinarse programáticamente o estén disponibles en texto, de modo que el contenido se pueda adaptar a distintos formatos sin perder su significado.
**Por qué importa:** Da flexibilidad a usuarios con discapacidad para adaptar el contenido a sus necesidades preservando el significado; beneficia a personas ciegas cuando la información transmitida por color también se expresa en texto (por ejemplo, símbolos de moneda junto a los precios); y a personas sordociegas que usan líneas braille y necesitan que la información no dependa únicamente del color.
**Cómo cumplirlo:**
- Usar marcado semántico apropiado (encabezados, listas, tablas) o roles/landmarks ARIA para transmitir la estructura programáticamente.
- Asociar las etiquetas a los controles de formulario mediante `<label>` o atributos ARIA; marcar los campos obligatorios con indicador visual y texto.
- Usar `<th>` con `scope` o `id` en tablas para que la relación entre celdas y encabezados sea interpretable por tecnología asistiva.
- Cuando la tecnología no soporte relaciones programáticas, aportar una descripción textual clara cerca del contenido relevante.
**Ejemplos/notas:** Campos de formulario obligatorios marcados con texto rojo y asterisco, explicando que ambos indicadores señalan obligatoriedad; una tabla de horarios de ómnibus donde los encabezados de fila y columna están identificados programáticamente; etiquetas de casillas de verificación asociadas programáticamente a sus controles para usuarios de lector de pantalla.

### 1.3.2 Secuencia significativa (Nivel A)
**Qué pide:** Que cuando la secuencia en que se presenta el contenido afecte su significado, se pueda determinar programáticamente un orden de lectura correcto, permitiendo que agentes de usuario u otras tecnologías ofrezcan una presentación alternativa sin perder el sentido original.
**Por qué importa:** Beneficia a usuarios de tecnología asistida que reciben el contenido leído en voz alta: el significado evidente en la secuencia de la presentación por defecto debe mantenerse igual cuando el contenido se presenta en forma hablada, evitando confusión.
**Cómo cumplirlo:**
- Ordenar todo el contenido en una secuencia significativa usando marcado estructural.
- Alinear el posicionamiento CSS con el marcado estructural.
- Asegurar que el orden del DOM coincida con el orden visual.
- Usar marcado direccional para texto bidireccional.
- Definir correctamente el orden de tabulación y de lectura en archivos PDF.
- Evitar fallas comunes: uso de espacios en blanco para dar formato, tablas de maquetación que no se "linealizan" bien, y posicionamiento CSS que altera el significado.
**Ejemplos/notas:** Documentos a varias columnas que fluyen de arriba hacia abajo dentro de cada columna y luego pasan a la siguiente; disposiciones con posicionamiento CSS (navegación, contenido principal, barra lateral) donde el orden visual difiere del orden programático pero el significado se preserva igual.

### 1.3.3 Características sensoriales (Nivel A)
**Qué pide:** Que las instrucciones para comprender y operar el contenido no dependan únicamente de características sensoriales de los componentes, como su forma, tamaño, ubicación visual, orientación o sonido, dado que esa información puede no estar disponible para usuarios de tecnología asistida.
**Por qué importa:** Las personas ciegas o con baja visión no pueden comprender instrucciones basadas solo en forma y ubicación; proveer información adicional más allá de las señales sensoriales permite que todos los usuarios accedan y operen el contenido correctamente, garantizando que existan métodos de instrucción no visuales junto a las señales visuales.
**Cómo cumplirlo:**
- Proporcionar identificación textual para los elementos que de otro modo dependerían solo de información sensorial.
- Evitar identificar contenido exclusivamente por forma o ubicación.
- Evitar usar símbolos gráficos solos para transmitir información necesaria.
**Ejemplos/notas:** Falla: un cronograma usa íconos de colores (rombo azul, círculo verde) sin alternativa textual para indicar sedes, dependiendo únicamente de características sensoriales. Cumple: una encuesta usa una flecha verde con la etiqueta "Siguiente" en la esquina inferior derecha; como las instrucciones se refieren tanto a la etiqueta como a la posición, no dependen solo de lo sensorial.

### 1.3.4 Orientación (Nivel AA)
**Qué pide:** Que el contenido no restrinja su visualización a una sola orientación de pantalla (vertical u horizontal), salvo que una orientación específica sea esencial, de modo que se adapte a la orientación que el dispositivo del usuario soporte o tenga fija.
**Por qué importa:** Beneficia a personas con discapacidades motoras que tienen dispositivos montados en posición fija (por ejemplo, en sillas de ruedas motorizadas) y no pueden reposicionar el equipo; y a personas con baja visión, que ganan flexibilidad para elegir la orientación que optimice la legibilidad, como el modo horizontal para aumentar el tamaño del texto.
**Cómo cumplirlo:**
- Ofrecer controles que permitan acceder al contenido en ambas orientaciones cuando de otro modo estaría restringido.
- Evitar bloquear el contenido exclusivamente en modo vertical u horizontal.
- Evitar mostrar mensajes que exijan reorientar el dispositivo.
- Contemplar excepciones legítimas cuando una orientación específica sea esencial por el significado del contenido o restricciones tecnológicas.
**Ejemplos/notas:** Sitios de video que se muestran tanto en vertical como en horizontal; aplicaciones de mensajería compatibles con ambas orientaciones; lectores de libros electrónicos con disposición flexible; una app bancaria que exige modo horizontal específicamente para capturar la imagen de un cheque (considerado esencial); una app de piano que necesita modo horizontal por el espacio funcional de las teclas (también esencial).

### 1.3.5 Identificar el propósito de la entrada (Nivel AA)
**Qué pide:** Que el propósito de los campos de entrada que recogen información sobre el usuario se pueda determinar programáticamente, permitiendo que agentes de usuario y tecnologías asistidas presenten ese propósito mediante distintas modalidades. Busca superar las limitaciones de atributos de tipo genéricos (como `type="email"`) habilitando una identificación más precisa mediante valores estandarizados (por ejemplo, distinguir el correo propio del de un tercero).
**Por qué importa:** Beneficia a personas con discapacidades cognitivas o de memoria, que se ven aliviadas cuando el navegador autocompleta datos personales como nombre o dirección sin necesidad de recordarlos; a personas con discapacidades de comunicación que prefieren apoyo visual, mediante tecnología asistida que agrega íconos familiares a los campos; y a personas con discapacidades motoras, que reducen la cantidad de entradas manuales necesarias.
**Cómo cumplirlo:**
- Usar atributos `autocomplete` estandarizados de HTML, como `autocomplete="given-name"`, `autocomplete="bday"` o `autocomplete="tel"`.
- Distinguir propósitos de campos combinados mediante tokens de detalle como "billing" y "shipping" en direcciones de facturación y envío.
**Ejemplos/notas:** Formularios de contacto donde identificar los campos (nombre, dirección, teléfono, correo) habilita el autocompletado del navegador y la personalización por tecnología asistida; formularios de pedido que distinguen direcciones de facturación y de envío mediante tokens explícitos de autocompletado.

### 1.3.6 Identificar el propósito (Nivel AAA)
**Qué pide:** Que el propósito de numerosos elementos de una página (íconos, regiones, componentes de interfaz) se pueda determinar programáticamente, permitiendo que los agentes de usuario extraigan y presenten ese propósito mediante distintas modalidades, apoyando funciones de personalización.
**Por qué importa:** Beneficia a personas con diversas discapacidades cognitivas, incluidas dificultades de memoria, atención, lenguaje y función ejecutiva, que necesitan símbolos y gráficos con los que estén familiarizados, menor carga cognitiva mediante funciones reducidas, y atajos de teclado o navegación simplificada.
**Cómo cumplirlo:**
- Indicar programáticamente el propósito mediante marcado para íconos, regiones y componentes de interfaz.
- Implementar landmarks ARIA para identificar regiones de la página (por ejemplo, `role="main"`).
- Usar marcado de microdatos para identificación semántica.
- Como mejoras recomendadas: habilitar adaptaciones según preferencias del usuario, usar atributos semánticos como `coga-simplification="simplest"`, y marcar campos obligatorios con `required` o `aria-required`.
**Ejemplos/notas:** Sitios web que usan landmarks ARIA para permitir ocultar regiones no esenciales; enlaces de navegación marcados para permitir sustitución de íconos personalizados; conjuntos de íconos reemplazables por alternativas preferidas por el usuario.

## 1.4 Distinguible

### 1.4.1 Uso del color (Nivel A)
**Qué pide:** Que la información no se transmita únicamente mediante diferencias de color, ya sea en texto, controles de formulario o imágenes. Si el color codifica un significado (por ejemplo, "los campos obligatorios están en rojo"), debe existir también otra señal visual (texto, icono, patrón, subrayado) que comunique lo mismo.
**Por qué importa:** Beneficia a usuarios con deficiencias de visión cromática (daltonismo) que no distinguen ciertos colores, a personas mayores cuya percepción del color se reduce con la edad, a personas con vista parcial (que suelen tener visión de color limitada) y a quienes usan pantallas monocromáticas o de color limitado.
**Cómo cumplirlo:**
- Garantizar que la información transmitida por color también esté disponible como texto (p. ej., una etiqueta "obligatorio" además del color rojo).
- Añadir un ícono o símbolo junto al elemento codificado por color.
- En formularios, incluir una pista textual adicional para las etiquetas de color.
- En imágenes o gráficos, combinar color y patrón/textura para diferenciar categorías.
**Ejemplos/notas:** Un formulario indica en sus instrucciones que los campos requeridos se marcan con texto rojo "y" con un ícono, de modo que quien no perciba el rojo igual identifique el ícono junto a la etiqueta.

### 1.4.2 Control de audio (Nivel A)
**Qué pide:** Si un sonido se reproduce automáticamente por más de 3 segundos, debe existir un mecanismo para pausarlo, detenerlo o controlar su volumen de forma independiente al volumen general del sistema. Se prefiere que el sonido sea iniciado por una acción del usuario en lugar de requerir que el usuario lo detenga.
**Por qué importa:** Beneficia principalmente a usuarios de lectores de pantalla, para quienes un audio de fondo puede tapar la salida de voz del lector (crítico para personas con baja visión o ceguera), y también a personas con dificultad para concentrarse en contenido visual o textual cuando hay audio simultáneo.
**Cómo cumplirlo:**
- Hacer que el sonido se detenga automáticamente dentro de los 3 segundos.
- Proporcionar un control visible cerca del inicio de la página que apague los sonidos automáticos.
- Reproducir el sonido solo a pedido del usuario (sin autoplay).
- Evitar elementos multimedia HTML5 en autoplay sin posibilidad de pausa.
**Ejemplos/notas:** Un archivo de audio comienza a reproducirse automáticamente al abrir la página, pero puede detenerse mediante un enlace "silenciar" ubicado en la parte superior.

### 1.4.3 Contraste (mínimo) (Nivel AA)
**Qué pide:** Exigir una relación de contraste mínima entre el texto y su fondo: 4.5:1 para texto normal y 3:1 para texto grande (18pt, o 14pt en negrita, o equivalente). Se exceptúan logotipos, texto decorativo, componentes inactivos y texto incidental dentro de fotografías.
**Por qué importa:** Las personas con baja visión suelen tener dificultad para leer texto que no contrasta con el fondo, problema que se agrava si además hay deficiencia de visión cromática. Usar contraste basado en luminancia (no en matiz) ayuda incluso a quienes no perciben el rango completo de colores.
**Cómo cumplirlo:**
- Asegurar 4.5:1 entre texto (o imagen de texto) y fondo para texto normal; 3:1 para texto grande.
- Evitar fijar colores de fondo/texto de forma que impida que el usuario aplique sus propios estilos (dejar valores por defecto del agente de usuario).
- Ofrecer un control que permita cambiar a una presentación de contraste suficiente.
- Recordar que, si un logo normalmente tiene contraste suficiente pero se presenta deliberadamente con bajo contraste, esa presentación no queda exenta.
**Ejemplos/notas:** El valor 4.5:1 compensa una pérdida de sensibilidad al contraste equivalente a una agudeza visual de 20/40 (común en adultos mayores de 80 años aproximadamente); para AAA, 7:1 compensa una pérdida equivalente a 20/80. El redondeo no es válido: 4.499:1 no cumple el umbral de 4.5:1. Tipografías muy estilizadas que funcionan como gráficos se rigen por 1.4.11, no por este criterio.

### 1.4.4 Cambio de tamaño del texto (Nivel AA)
**Qué pide:** El texto (incluyendo controles y etiquetas) debe poder ampliarse hasta un 200% sin usar tecnología de asistencia, sin perder contenido ni funcionalidad.
**Por qué importa:** Ayuda a personas con baja visión que solo pueden leer el texto si este se agranda. Reconoce que el escalado depende en parte del navegador, pero el diseño responsivo (medidas relativas) debe permitir que ese escalado funcione sin romper el contenido.
**Cómo cumplirlo:**
- Usar tecnologías cuyos agentes de usuario habituales soporten zoom.
- Emplear medidas relativas (em, porcentajes, tamaños de fuente nombrados) junto con diseño líquido/contenedores adaptables.
- Proporcionar controles en la página para incrementar el tamaño del texto hasta 200%.
- Evitar que el texto se recorte, trunque u oculte al escalar y que los controles basados en texto no se redimensionen.
**Ejemplos/notas:** Un usuario aumenta el tamaño de 1em a 1.2em y toda la información sigue mostrándose sin pérdida. En interfaces complejas (correo, hojas de cálculo), algunos componentes pueden truncarse inicialmente pero revelar el contenido completo al recibir foco, siempre que haya indicación visual de que hay más contenido.

### 1.4.5 Imágenes de texto (Nivel AA)
**Qué pide:** Usar texto real en lugar de imágenes de texto siempre que la tecnología lo permita, salvo que la presentación visual específica sea esencial para la información (logotipos) o el usuario pueda personalizar la imagen.
**Por qué importa:** Permite que personas con baja visión ajusten tipografía, tamaño y color; que personas con dificultades de seguimiento visual adapten espaciado y alineación; y que personas con discapacidades cognitivas reestilicen el texto según sus necesidades de lectura.
**Cómo cumplirlo:**
- Usar CSS para controlar la presentación visual del texto en lugar de generar imágenes.
- Si se usa una imagen de texto, ofrecer controles para alternar entre la versión imagen y la de texto real.
- Separar información/estructura de la presentación (principio general de diseño accesible).
- Aplicar OCR a PDFs escaneados para obtener texto real.
**Ejemplos/notas:** Un logotipo con texto integrado en una imagen GIF es una excepción válida porque la presentación visual es esencial para la identidad; lo mismo ocurre con una imagen que muestra una familia tipográfica específica, donde sustituir la fuente anularía el propósito. En ambos casos se requiere alternativa textual.

### 1.4.6 Contraste (mejorado) (Nivel AAA)
**Qué pide:** Versión reforzada de 1.4.3: contraste mínimo de 7:1 para texto normal y 4.5:1 para texto grande, con las mismas excepciones (logotipos, decoración, texto incidental, componentes inactivos).
**Por qué importa:** Sirve a personas con baja visión moderada a severa que no usan tecnología de asistencia para mejorar el contraste. Al basarse en luminancia y no en color, funciona también para personas con deficiencias de visión cromática.
**Cómo cumplirlo:**
- Asegurar 7:1 entre texto pequeño y fondo; 4.5:1 para texto grande.
- No fijar colores que impidan los valores por defecto del usuario; ofrecer un control para cambiar a presentación de alto contraste.
- No redondear los cálculos de contraste.
**Ejemplos/notas:** 7:1 compensa una pérdida visual equivalente a 20/80; 4.5:1 equivale aproximadamente a 20/40. Estados de hover por defecto pueden remediar una presentación de bajo contraste; botones deshabilitados con estilo por defecto quedan exentos.

### 1.4.7 Audio de fondo bajo o ausente (Nivel AAA)
**Qué pide:** En audio pregrabado que es principalmente voz (no un medio alternativo visual rotulado como tal), los sonidos no vocales deben cumplir una de tres condiciones: no existir, poder apagarse, o estar al menos 20 decibelios por debajo del discurso en primer plano (excepto sonidos ocasionales de uno o dos segundos).
**Por qué importa:** Las personas con dificultades auditivas suelen tener gran dificultad para separar la voz del sonido de fondo o ruido ambiente, lo que afecta su comprensión del contenido hablado.
**Cómo cumplirlo:**
- Evitar sonido de fondo en grabaciones de voz.
- Proporcionar un control para apagar el sonido de fondo.
- Mezclar el audio de modo que los sonidos no vocales queden al menos 20 dB por debajo del habla.
**Ejemplos/notas:** Un sonido de fondo que cumple la regla de 20 dB resulta aproximadamente cuatro veces más silencioso que el habla en primer plano.

### 1.4.8 Presentación visual (Nivel AAA)
**Qué pide:** Para bloques de texto, el usuario debe poder: elegir colores de fondo y primer plano; limitar el ancho de línea a no más de 80 caracteres (40 para CJK); evitar texto justificado a ambos lados; aplicar espaciado de línea de al menos 1.5 dentro de párrafos y espaciado entre párrafos de al menos 1.5 veces el espaciado de línea; y ampliar el texto hasta 200% sin necesitar scroll horizontal en pantalla completa.
**Por qué importa:** Beneficia a personas con discapacidades cognitivas, de lenguaje y aprendizaje, y a usuarios con baja visión, quienes pueden perder su lugar de lectura o no comprender el texto si el layout dificulta la lectura. Elegir combinaciones propias de color mejora la comprensión; columnas angostas ayudan a mantener el seguimiento visual; el espaciado extra ayuda a ubicar el final de un párrafo; el texto ampliable evita la desorientación por scroll horizontal.
**Cómo cumplirlo:**
- Permitir selección de colores de fondo/texto (o no especificarlos, dejando los valores por defecto del navegador).
- Limitar el ancho de columna usando medidas relativas, sin interferir con el reflow del agente de usuario.
- Alinear el texto solo a un lado (izquierda o derecha), nunca justificado completo.
- Especificar espaciado de línea y párrafo vía CSS según las proporciones mínimas indicadas.
- Usar diseño líquido y unidades relativas para que el texto escale a 200% sin scroll horizontal.
**Ejemplos/notas:** La página ilustra visualmente la diferencia entre interlineado simple, espacio y medio, y doble espaciado para mostrar el requisito de espaciado.

### 1.4.9 Imágenes de texto (sin excepciones) (Nivel AAA)
**Qué pide:** Versión más estricta de 1.4.5: las imágenes de texto solo se permiten cuando son puramente decorativas o cuando la presentación visual específica es esencial a la información transmitida (por ejemplo, logotipos, muestras de una tipografía concreta, cartas históricas). Fuera de esos casos, prácticamente se prohíbe el uso de imágenes de texto.
**Por qué importa:** Igual que en 1.4.5, beneficia a personas con baja visión (necesitan ajustar tipografía, tamaño y color), personas con problemas de seguimiento visual (necesitan ajustar espaciado y alineación) y personas con discapacidades cognitivas que afectan la lectura.
**Cómo cumplirlo:**
- Usar CSS para controlar la presentación visual del texto en vez de imágenes.
- Separar estructura/información de la presentación para habilitar distintas presentaciones.
- Aplicar OCR en PDFs escaneados.
- Usar unidades escalables (porcentajes, nombres de fuente, em) para tamaños de texto.
**Ejemplos/notas:** Una cita con cursiva e indentación controlada por CSS cumple el criterio porque el usuario puede adaptarla. Un logotipo con texto en GIF y una imagen que muestra una tipografía específica son excepciones válidas (la presentación es esencial), siempre con alternativa textual. A diferencia de 1.4.5 (nivel AA, con excepciones más amplias), 1.4.9 (AAA) eleva el estándar y restringe drásticamente los casos permitidos.

### 1.4.10 Reflow (Nivel AA)
**Qué pide:** El contenido debe poder presentarse sin pérdida de información ni funcionalidad y sin requerir scroll en dos dimensiones, para un ancho equivalente a 320 píxeles CSS (contenido de scroll vertical) o una altura equivalente a 256 píxeles CSS (contenido de scroll horizontal). Se exceptúan partes que requieren layout bidimensional para su comprensión o función (mapas, diagramas, video, juegos, tablas de datos, barras de herramientas que deben permanecer visibles).
**Por qué importa:** Favorece a personas con baja visión que necesitan ampliar (hacer zoom) el texto para leerlo; con reflow, el contenido se reacomoda dentro de la ventana visible, permitiendo seguir las líneas sin desplazamiento horizontal constante, lo cual reduce la pérdida de posición y el esfuerzo cognitivo/físico.
**Cómo cumplirlo:**
- Usar diseño responsivo que colapse a una sola columna dentro de un viewport de 320px CSS.
- Aplicar CSS Flexbox o Grid con media queries para reacomodar columnas.
- Manejar adecuadamente URLs o cadenas largas para que no fuercen scroll horizontal.
- Diseñar paneles de scroll horizontal (carruseles) que quepan individualmente en 320px.
- Usar CSS max-width/height para que imágenes fijas no provoquen desplazamiento horizontal.
**Ejemplos/notas:** 320 CSS px equivale a un viewport inicial de 1280px al 400% de zoom; este valor se eligió por corresponder al ancho de pantalla de dispositivos móviles comunes. Un carrusel aprueba si cada panel cabe en 320px aunque se navegue horizontalmente entre paneles; falla si el contenido dentro de un panel individual requiere scroll horizontal. Se solapa con 1.4.4 (zoom a 200%) y con 2.4.7 (contenido "sticky" que puede ocultar el foco al ampliar).

### 1.4.11 Contraste de elementos no textuales (Nivel AA)
**Qué pide:** Los componentes de interfaz de usuario (controles e indicadores de sus estados) y los gráficos significativos necesarios para comprender el contenido deben tener una relación de contraste de al menos 3:1 contra los colores adyacentes. No aplica a componentes inactivos, a elementos puramente decorativos, a aquellos sin alternativa textual visible, ni a presentaciones controladas por el usuario fuera del control del autor.
**Por qué importa:** Las personas con baja visión moderada, especialmente con deficiencias de visión cromática, suelen perder controles o gráficos de bajo contraste; una relación de 3:1 basada en luminancia los hace más distinguibles aunque no se perciba el rango completo de colores.
**Cómo cumplirlo:**
- Asegurar 3:1 de contraste en bordes/rellenos de controles como checkboxes, botones, campos de entrada, toggles e indicadores de desplegables.
- Mantener 3:1 también en los indicadores de foco visibles.
- Asegurar 3:1 en las partes esenciales de gráficos necesarios para comprender el contenido.
- No es necesario que los cambios de color entre estados de un mismo componente cumplan 3:1 si no aparecen uno junto al otro.
**Ejemplos/notas:** Aprueban: un checkbox con borde negro sobre blanco; un campo de texto con borde oscuro (#767676) que logra 3:1. Fallan: un checkbox con borde gris (#9D9D9D) sobre blanco (2.7:1) o un indicador de foco gris (#AAA) sobre blanco (2.3:1); un subrayado de enlace de bajo contraste como único indicador del enlace.

### 1.4.12 Espaciado del texto (Nivel AA)
**Qué pide:** Cuando el usuario sobrescribe el espaciado de texto definido por el autor (usando su propia hoja de estilos o configuración), el contenido debe seguir siendo legible y funcional al aplicar como mínimo: altura de línea de 1.5 veces el tamaño de fuente, espaciado entre párrafos de 2 veces el tamaño de fuente, espaciado entre letras de 0.12 veces el tamaño de fuente y espaciado entre palabras de 0.16 veces el tamaño de fuente.
**Por qué importa:** Beneficia a personas con baja visión que necesitan más espacio entre líneas, palabras y letras; a personas con dislexia, que pueden aumentar el espaciado para mejorar su velocidad de lectura; y, en general, a personas con discapacidades cognitivas que se benefician de más espacio en blanco.
**Cómo cumplirlo:**
- No impedir que el usuario sobrescriba el espaciado especificado por el autor.
- Permitir espaciado de texto sin que se rompa el ajuste de línea.
- Verificar que el texto no se corte vertical ni horizontalmente al aplicar el espaciado ampliado.
- Asegurar que el texto no se superponga con otros elementos al modificarse el espaciado.
**Ejemplos/notas:** Casos de falla típicos: palabras incompletas cortadas en la parte inferior de un contenedor, letras faltantes al final de una línea, o texto que se superpone a otros elementos.

### 1.4.13 Contenido en hover o foco (Nivel AA)
**Qué pide:** Cuando el hover del puntero o el foco del teclado revela contenido adicional (tooltips personalizados, submenús, popups no modales) que oculta o reemplaza otro contenido, ese contenido adicional debe ser descartable, desplazable (hoverable) y persistente, salvo que el disparador indique un error de entrada o que la presentación esté regida por otra norma.
**Por qué importa:** El usuario puede no haber tenido intención de activar la interacción, puede no saber que apareció contenido nuevo, o este puede interferir con su tarea. Beneficia a usuarios de baja visión con ampliación (pueden ver el contenido sin reducir su nivel de zoom), a usuarios con cursores ampliados, a personas con baja visión o discapacidades cognitivas (que necesitan tiempo adecuado para percibir el contenido) y a usuarios con poca precisión de puntero (que pueden descartar fácilmente contenido activado sin querer).
**Cómo cumplirlo:**
- Descartable: debe poder cerrarse el contenido adicional (p. ej. con Escape) sin mover el puntero ni el foco, salvo si es un mensaje de error o no oculta contenido relevante.
- Desplazable (hoverable): si lo activa el hover, el puntero debe poder moverse sobre el contenido adicional sin que este desaparezca.
- Persistente: el contenido permanece visible hasta que se quite el disparador, el usuario lo descarte, o la información deje de ser válida.
**Ejemplos/notas:** Un botón con un tooltip debajo puede cerrarse con Escape sin mover el ratón; un tooltip que un puntero grande podría tapar se soluciona moviendo el puntero hacia su borde inferior para verlo completo.
