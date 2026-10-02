---
title: "Módulo 1 — Diseñar para la diversidad"
status: draft
source: "raw-inputs/modulo-01-raw.rtf"
last_updated: 2026-10-02
---

# Módulo 1 — Diseñar para la diversidad

Lecciones grabadas (1.1 a 1.10) del Módulo 1 del programa intensivo "Diseño Accesible" de weAAAre. Base teórica: qué es la accesibilidad, diversidad de personas y necesidades, formas de interacción, tecnologías de apoyo, barreras, relación con usabilidad/UX, sesgos en el proceso de diseño, diseño universal/inclusivo, e investigación como hábito.

## 1.1 — Qué es la accesibilidad

- Permite que un producto/servicio digital sea usado por personas con **distintas capacidades**, formas de interacción y contextos (luz intensa, ruido, etc.).
- Habilita tres acciones: **percibir** el contenido, **comprender** qué hacer, y **navegar/interactuar** para completar una tarea.
- Es un **atributo de calidad**: una experiencia no está terminada si excluye a un grupo de usuarios.
- Dos escenarios de trabajo: **diseñar accesible desde cero** (se puede anticipar) o **remediar** un producto existente (detectar el problema y corregir con decisiones basadas en evidencia).

## 1.2 — Diversidad de personas y necesidades

- Una misma condición (ej. discapacidad visual) tiene manifestaciones muy distintas: lector de pantalla (ceguera), magnificadores (baja visión), o navegación sin tecnología de apoyo (discapacidad adquirida recientemente, aún sin aprender a usar TA).
- **Una persona no representa a todo su colectivo** — validar con más de una persona para no generalizar mal.
- Tipos de necesidad según duración:
  - **Permanentes**: la persona vive con una discapacidad.
  - **Temporales**: ej. pérdida auditiva por otitis.
  - **Situacionales**: ej. no poder activar sonido en transporte público o biblioteca.
  - Los subtítulos resuelven los tres casos a la vez — mismo patrón, distintos orígenes de la necesidad.
- Al investigar, conviene segmentar tanto por **tipo de discapacidad** como por **tecnología de apoyo usada**, y buscar los patrones comunes y las diferencias entre perfiles.

## 1.3 — Formas de interacción con productos digitales

- Toda tarea digital implica dos cosas: **recibir información** (percibir + comprender) y **realizar acciones** (interactuar vía teclado, mouse/puntero, voz, tacto o tecnología de apoyo).
- Estas formas se combinan en una misma tarea — ej. seleccionar una fecha: mouse (apuntar + clic) o teclado (foco + Enter/espacio); ambos caminos deben dejar visible la selección y el estado.
- **Accesible ≠ fácil de usar**: un selector de fecha por calendario puede ser accesible pero incómodo para una fecha de nacimiento lejana; la solución es ofrecer también **escritura directa con formato declarado con precisión**.
- Caso recuperación de contraseña: la biometría (reconocimiento facial/huella) puede fallar (envejecimiento, ceguera) — siempre debe existir una **alternativa preconfigurada** (ej. preguntas de seguridad) y **asistencia remota**; "ir a la sucursal" no cuenta como alternativa digital.

## 1.4 — Tecnologías de apoyo

Distinción clave: **preferencias/configuraciones del sistema** (tamaño de texto, contraste, modo oscuro, subtítulos — viven en el navegador/dispositivo y persisten entre sitios) vs. **tecnologías de apoyo** (herramientas externas para acceder y actuar sobre el contenido):

| Tecnología | Qué hace | Para quién |
|---|---|---|
| Lector de pantalla | Convierte texto a voz o a línea braille actualizable | Ceguera — por eso el texto alternativo en imágenes es crítico: "nada es más accesible que el texto" |
| Magnificador / ampliación | Aumenta tamaño de pantalla parcial o total, configurable en nivel, área, contraste y color texto/fondo | Baja visión |
| Voz a texto (dictado) | Permite buscar, abrir apps, navegar y dictar contenido sin teclado/mouse/táctil | Alternativa de entrada |
| Teclados alternativos | Disposiciones adaptadas (ej. teclado de una mano) | Discapacidad física |
| Punteros alternativos (joystick, control por cabeza) | Permiten escribir/navegar sin mouse estándar | Discapacidad física que impide usar mouse/teclado |
| Switches / interruptores | Acción simple (ej. mouse de un solo botón), combinable con barrido automático de la interfaz | Movilidad muy reducida |
| Seguimiento ocular (eye tracking) | Detecta movimiento del ojo para seleccionar/escribir | Discapacidad motriz severa |
| CAA (Comunicación Aumentativa y Alternativa) | Pictogramas/símbolos/teclados que se transforman en mensaje de voz sintética | Dificultades del habla |

- Principio de diseño: **un componente debe ser lo que parece** — si visualmente es un botón, debe comunicarse como botón (rol + nombre accesible + acción activable por teclado), sin importar si a nivel de desarrollo se implementó como `div` o `link`. Anticipar esto es responsabilidad del diseño, no solo de desarrollo.

## 1.5 — Barreras de diseño

- **Barrera de accesibilidad**: característica del producto que dificulta o impide realizar una tarea. Todas las personas se benefician de la accesibilidad, no solo quienes tienen discapacidad.
- Cuatro tipos de barrera:
  1. **Percepción** — impide acceder a la información (ej. instrucción solo por audio excluye a personas sordas).
  2. **Comprensión** — impide entender el contenido/lo que pasa en la interfaz.
  3. **Interacción** — impide controlar o completar una acción.
  4. **Estructura** — la organización hace la información incomprensible para quien usa tecnología de apoyo.
- **Formular el problema sobre el diseño, no sobre la persona**: en vez de "la persona no puede usar el menú" → "el menú solo puede utilizarse mediante un gesto que la persona no puede realizar". La segunda formulación apunta a algo que el diseño puede modificar.
- Metodología: **detectar la barrera antes de buscar la solución** (investigar primero). Preguntas guía: ¿qué necesita el usuario para percibir / comprender / hacer? ¿De qué capacidad depende la tarea? ¿Existe otra forma razonable de hacerla?
- Qué debe reconocer el diseño: dependencias excesivas de una sola capacidad (ej. navegar solo por color), jerarquías visuales sin estructura semántica equivalente, estados/comportamientos no documentados (foco, activo/inactivo), y ausencia de alternativas.

## 1.6 — Accesibilidad, usabilidad y experiencia de usuario

- No son sinónimos, aunque están relacionados:
  - **Accesibilidad**: que personas con y sin discapacidad puedan acceder e interactuar con el producto.
  - **Usabilidad**: que el producto se use de forma efectiva, eficiente y satisfactoria — **para todas las personas** (no existe "usabilidad para personas con discapacidad" como categoría aparte).
  - **UX**: la experiencia global con el producto/servicio.
- Una interfaz puede ser **usable (clara, rápida, fácil de aprender, eficiente) y aun así inaccesible** — ej. no navegable por teclado.
- Ejemplo de ambigüedad: un campo de contraseña con instrucción "use un formato válido" sin especificar cuál, y un link de ayuda que no se percibe como tal — la relación entre campos y ayudas debe comunicarse de forma perceptible en cualquier modalidad (visual, auditiva, táctil).

## 1.7 — Sesgos y supuestos en el proceso de diseño

- Error común (sobre todo al inicio): diseñar como si uno mismo fuera el usuario típico (mouse, pantalla grande, buena vista/audición, mismo ritmo de lectura, reconocimiento de patrones de interfaz).
- Lo que creemos saber incluye sesgos y prejuicios — hay que **validar en vez de asumir**. Ejemplo: agregar la palabra "menú" junto al ícono hamburguesa mejora la comprensión en vez de asumir que el patrón es universalmente reconocido.
- **Un dato no cuenta toda la historia**: que una plataforma "no tenga usuarios con discapacidad" no explica si es porque no les interesa el producto o porque el producto tiene demasiadas barreras. Preguntas útiles (inspiradas en el libro *"Simplemente pregunta"* — *Just Ask*): ¿la persona con discapacidad conoce el producto? ¿puede entrar, registrarse, avanzar? ¿en qué parte del flujo abandona? ¿sería distinto si el producto fuera accesible?
- Marco de análisis: **origen** (¿estamos observando o solo suponiendo?), **ausencias** (¿a quién dejamos fuera y por qué?), **comprobación** (¿qué necesitamos investigar para confirmarlo?).
- Distinción importante: una **fricción intencional** (ej. impedir que un menor abra una cuenta bancaria o de crédito) no es una barrera de accesibilidad. Una barrera es una **omisión no intencional que termina excluyendo**.

## 1.8 — Diseño universal vs. diseño inclusivo

- Ambos consideran la diversidad desde el inicio del proceso.
- **Diseño universal**: busca el uso más amplio posible sin requerir adaptaciones especializadas (ej. un pasillo ancho sirve a peatones, sillas de ruedas y coches de bebé por igual). Origen: 1997, Center for Universal Design de NC State. Viene del diseño físico/arquitectónico.
- **Diseño inclusivo**: considera la diversidad de personas y contextos durante el proceso de diseño (más orientado a proceso que a resultado final).
- El diseño universal es un **marco orientador**, no un estándar técnico como WCAG — ayuda a tomar decisiones pero no define requisitos específicos para la web.
- **Los 7 principios del diseño universal**:
  1. Uso equitativo — medios equivalentes, sin separar ni estigmatizar.
  2. Flexibilidad en el uso — distintas preferencias y formas de interactuar.
  3. Uso simple e intuitivo — la persona entiende el campo sin necesidad de equivocarse primero.
  4. Información perceptible — el estado (error, éxito, etc.) no depende únicamente del color.
  5. Tolerancia al error — prevenir, confirmar y permitir recuperación (ej. confirmar una transferencia bancaria, deshacer el envío de un correo, guardar el avance de un formulario largo para no perderlo).
  6. Bajo esfuerzo físico — evitar gestos o movimientos innecesariamente complejos.
  7. Tamaño y espacio para el acceso y uso — controles amplios y bien separados (se conecta directamente con criterios de WCAG sobre tamaño de objetivo táctil).
- Estos principios se traducen en 4 preguntas de diseño: ¿se puede usar de distintas maneras? ¿la información se percibe por distintos medios? ¿qué pasa si la persona se equivoca, puede recuperarse? ¿funciona con distintas capacidades y contextos?

## 1.9 — Investigación en el diseño (pensar antes de diseñar)

- La investigación es parte esencial y temprana del proceso, no un paso posterior a validar lo ya diseñado.
- Preguntas base: ¿quién necesita hacer esta tarea? ¿de qué capacidades/movimientos/dispositivos depende? ¿qué experiencias faltan? ¿a quién estamos dejando fuera, y es por diseño intencional o por omisión?
- **Ir de la tarea a la interfaz, no al revés**: entender la tarea → identificar necesidades diversas → recién ahí diseñar la solución accesible.
- Ejemplo recurrente: un requisito que depende solo de la vista (ej. "identificar el estado por color/ícono") debe reformularse como "la persona debe poder identificar el estado" y luego diseñarse de forma multicanal (texto + color, no solo color).
- Ejemplo de prenda roja con ícono de color: agregar la etiqueta de texto "rojo" junto a la selección resuelve la dependencia del color para personas daltónicas, ciegas o con visión borrosa.
- Recomendación: todos los **arquetipos/personas** deberían incluir características de accesibilidad y uso de tecnología de apoyo (no un arquetipo aparte "con discapacidad"), para que los requisitos de diseño exijan accesibilidad desde el origen. Curso recomendado de la plataforma: *entrevistas inclusivas*.
- Flujo de trabajo propuesto: investigar con perfiles diversos → definir personas/necesidades → levantar requisitos (que exijan accesibilidad) → diseñar flujos → definir componentes e interacción.

## 1.10 — Cambio de mirada: accesibilidad como hábito

- La accesibilidad debe decidirse **desde el inicio**, no al final: decidirla al final genera una lista de correcciones que tiende a **despriorizarse y no hacerse nunca**.
- Diseñar con accesibilidad temprana da un criterio para anticipar decisiones en cada paso (tarea → alternativas de interacción → validación antes de construir).
- Por qué "todo debe poder hacerse por teclado": todas las tecnologías de apoyo (switches, eye tracking, CAA, etc.) **confían en el teclado** como interfaz común subyacente.
- Nadie necesita tener todas las respuestas de antemano — lo importante es identificar lo que no se sabe/se asume y salir a validarlo.
- Riesgos de no hacerlo: además del impacto en personas usuarias, hay **riesgo legal y de reputación** para la empresa.

## Próximos pasos

- Este resumen cubre el contenido teórico grabado del Módulo 1. Falta sumar, cuando estén disponibles: ejercicios interactivos del módulo, recursos adicionales, y la tutoría en vivo asociada (definición formal del proyecto, según lo adelantado en la Clase 1 — ver [`clase-01-summary.md`](./clase-01-summary.md)).
