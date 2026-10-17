---
title: "Clase 2 — Tutoría en vivo (7 de octubre)"
status: draft
source: "raw-inputs/clase-02-raw.txt"
last_updated: 2026-10-16
---

# Clase 2 — Tutoría en vivo del 7 de octubre

Primera tutoría en vivo del intensivo: ronda de dudas sobre el Módulo 1, y luego trabajo práctico en Figma definiendo y acotando el flujo del proyecto de cada alumno.

## Testeo con personas con discapacidad

- **Usabilidad y accesibilidad son dos tipos de test distintos.** En usabilidad se mide eficacia/eficiencia (pasos, tiempo, satisfacción); en accesibilidad el tiempo se vuelve relativo — lo que importa es si la persona logra completar la tarea **de forma autónoma**.
- **Testear con una sola persona genera sesgo**, no evidencia generalizable. Ejemplo real de Consuelo: entrevistó a una persona sorda reconocida en tecnología que, por empatía hacia otros colectivos (no por conocimiento propio), opinó favorablemente sobre un widget de accesibilidad — su opinión terminó representándose a sí misma, no al colectivo.
- **Cuántas personas reclutar**: no hay receta fija, pero la base orientativa ronda las **6 personas** representando diversidad real — ej. daltonismo, baja visión, ceguera, sordera (idealmente de nacimiento o de muy temprana edad, para evaluar comprensión del contenido más que literacidad), autismo. En investigaciones más grandes se puede llegar a combinaciones de hasta 15, según presupuesto y tiempo.
- **Dos formas de armar la muestra** (llegan al mismo resultado): por **tipo de discapacidad** (visual, auditiva, cognitiva...) o por **tecnología de apoyo usada** (alguien con VoiceOver en computador, alguien con NVDA, alguien con lector de pantalla en celular, alguien que use solo teclado, alguien con magnificador) — esto último evita el sesgo de reclutar solo personas que usan la misma herramienta.
- **El dispositivo no es la variable relevante** como en un test de usabilidad convencional (no se segmenta por Android/iOS) — la persona casi siempre navega desde el mismo dispositivo que ya domina, así que hay que testear en el dispositivo que la persona usa habitualmente, no en el que el equipo elija.
- **La pauta de entrevista se adapta a la persona**, no es única. Ejemplo: con déficit atencional, un hallazgo típico es que los textos justificados (con líneas muy largas) son difíciles de seguir — esto después puede convertirse en buena práctica de diseño, y sirve como evidencia concreta para argumentarle a un stakeholder.
- Existe un formulario llamado **AUS** (Accessibility Usability Scale, de una empresa llamada Fable) para medir resultados de testeo con personas con discapacidad y comparar su evolución en el tiempo.
- **Shift left**: los testeos con personas con discapacidad suelen implementarse demasiado tarde (recién sobre el producto terminado/codeado). La propuesta es traerlos a etapas tempranas — con IA ya se pueden armar prototipos funcionales rápido que sí reflejan el sistema de diseño. Los **prototipos de Figma actuales no sirven para testear con personas ciegas** (solo permiten testear con baja visión o ciertas discapacidades cognitivas) — el curso enseñará a llevar un diseño de Figma a un prototipo real que sí puede usarse con lector de pantalla.
- Se puede testear de forma más liviana incluso con bocetos en papel narrados en voz (la misma lógica del testeo rápido en papel, pero contada/grabada en audio).
- Curso recomendado para profundizar: **"Entrevistas Inclusivas"** de weAAAre.

## Widgets de accesibilidad (overlays)

- **Rechazo explícito y categórico** de Consuelo y Carlos: los widgets no son accesibles, no cumplen el estándar, y generan que la organización **se desentienda del problema** en vez de resolverlo de raíz. Muchos profesionales de accesibilidad han firmado una carta abierta pública en contra de este tipo de soluciones (mencionado también en la fundación DALAT, consultada aparte por una alumna en otra investigación).
- **Por qué no funcionan**: asumen que la persona tiene una sola necesidad a la vez (no puedes "prender todo" simultáneamente); por lo general estos widgets **no son accesibles en sí mismos** (quedan al final del recorrido de teclado, no tienen nombre accesible); y la persona que realmente usa tecnología de apoyo **ya tiene su propia configuración** — no va a adoptar un lector de pantalla embebido en un sitio puntual que no le sirve para el resto de la web. Además, muchos widgets interfieren con los comandos de la tecnología de apoyo real de la persona (hay excepciones de widgets que sí leen en voz sin competir con el lector de pantalla nativo, útiles como alternativa de consumo tipo podcast, pero eso no es igual a "accesibilidad").
- **A quién podría ayudarle un widget**: personas mayores o quienes recién empiezan a vivir con una discapacidad y todavía no configuraron su propia tecnología de apoyo — pero la solución correcta ahí es diseñar bien desde el principio, no parchar con un widget.
- **La legislación europea no obliga a tener un widget** — el apartado 11.7 de la norma técnica europea habla de "preferencias del usuario", y mucha gente lo malinterpreta como una obligación de incluir un widget. Lo que exige es que el producto respete las preferencias que la persona ya configuró a nivel de sistema operativo/navegador (texto más grande, contraste, modo oscuro, menos movimiento), no que se reemplace eso con una herramienta propia del sitio.
- **El estándar WCAG no fija un tamaño mínimo de tipografía** — exige que el texto pueda ampliarse al 200% y 400% sin pérdida de información. Aun así, es buena práctica diseñar con un **mínimo de 16px** para quienes no saben configurar el zoom del sistema. Distinción clave repetida en la clase: **una cosa es el estándar (WCAG) y otra es diseñar una buena experiencia** — WCAG es la base, no el techo.
- **Cosas sí recomendables** (no son un "widget" en el sentido criticado): un botón simple para agrandar/achicar letra pensado para personas mayores que no conocen el atajo de teclado del sistema.
- **Dato técnico**: escribir texto directamente en mayúsculas en el código (en vez de aplicar un estilo CSS de `text-transform`) puede hacer que el lector de pantalla lo interprete como un acrónimo — ejemplo dado: "US" en "ABOUT US" se leería como "United States". La solución (usar estilos para transformar a mayúsculas visualmente, manteniendo el texto real en minúsculas/formato normal) resuelve ese problema pero genera dificultad de lectura para personas con dislexia, que tienen más problemas con texto todo en mayúsculas — es un trade-off a tener en cuenta.

## Estándares de accesibilidad (recordatorio rápido antes del Módulo 2)

- WCAG aplica a contenido web **y apps**, pero se está creando un estándar específico para apps nativas (algunas marcas HTML, como los niveles de encabezado H1-H6, no tienen sentido igual en apps nativas — ahí "encabezado" es una sola jerarquía).
- Existen estándares separados para: **software** (ATAG... mencionado también UAAG para navegadores/agentes de usuario), **herramientas de autor** (ej. WordPress — una cosa es la web resultante, otra cómo se sube el contenido a ella), y el **Mobile Accessibility Task Force** (grupo de trabajo del W3C que adapta criterios de WCAG a apps móviles — ej. el criterio 1.4.10 Reflow no aplica igual en móvil). Todo esto se profundiza en el Módulo 2.
- **COGA** (Cognitive and Learning Disabilities Accessibility Task Force) no es un estándar formal todavía, pero reúne principios e indicadores para diseñar considerando discapacidad cognitiva — surge porque WCAG 2.1/2.2 empezó a incorporar criterios para esto pero todavía es insuficiente.
- Conformar WCAG 2.2 implica conformar 2.1 y 2.0 (estructura acumulativa desde la versión 2.0); la versión 3.0 (borrador) reestructurará todo por completo.
- **Norma armonizada**: cuando una ley o norma técnica (sobre todo la europea) referencia un criterio WCAG dentro de su propio numerado, hay que rastrear la equivalencia correcta — y para apps, puede que haya que remitirse a la adaptación del Mobile Accessibility Task Force en vez del criterio WCAG "puro".
- Video recomendado por Consuelo (pendiente de compartir por Discord): publicidad/documentales de Apple mostrando personas con discapacidad usando sus dispositivos y software (edición de foto/video con seguimiento ocular, interacción sin manos) — ejemplo de que un producto puede ser atractivo, moderno y accesible a la vez ("la gente piensa que diseñar accesible es aburrido o es for un diseño institucional — no es así").

## Brief del proyecto: instrucciones

- Cada alumno copia la ficha de brief compartida a su **propio archivo de Figma** (no trabajar sobre el archivo compartido, para no perder el trabajo si alguien lo edita/borra). La entrega final del proyecto completo será la URL de ese Figma.
- **No se recomienda usar un proyecto del trabajo/empresa** por temas de confidencialidad y permisos — mejor un tema ficticio o de interés personal. *(Nota: esto coincide con la regla de confidencialidad ya registrada en memoria del repo.)*
- **Qué es un "flujo acotado"**: algo concreto como "añadir un producto al carrito" o completar un formulario de contacto — **2 a 4 pantallas como máximo**, nunca más. La accesibilidad se evalúa en pantallas individuales, pero los problemas reales aparecen en el *flujo* completo.
- El brief asume que ya existen research, arquetipos y journey maps (no es el foco del curso) — se trabaja directamente desde una necesidad y una tarea principal asumidas como dadas.
- Distinción enseñada: **lo que sabemos** (ej. "las personas con discapacidad necesitan accesibilidad") vs. **lo que suponemos** (ej. "suponemos que necesitan un widget de accesibilidad" — un supuesto que hay que cuestionar, no una necesidad real comprobada). No hay que inventar necesidades de accesibilidad forzadas; basarse en lo que cada alumno ya conoce.
- Campos del brief: nombre del proyecto, descripción del producto/servicio (nuevo o rediseño, con referentes si aplica), necesidad que resuelve, flujo (inicio y fin — no necesariamente arranca en el home), contexto de uso, personas usuarias, tarea principal, acciones necesarias, información necesaria en pantalla, y posibles barreras ya identificadas.
- **El foco del curso es la documentación de accesibilidad, no la calidad de la idea de producto** — se puede elegir cualquier idea, por disparatada que sea; no se evalúa si el producto tiene sentido de negocio. Esto es deliberado para no perder las 10 semanas en investigación/validación de producto.

## Ejemplo de brief ya resuelto (Consuelo — proyecto de referencia del curso)

Plataforma para descubrir y comprar obras de arte (cliente real en Alemania, con obligación legal de accesibilidad). Necesidad: "crear un espacio digital que permite a las personas descubrir y seleccionar obras de arte para comprarlas... de manera accesible, considerando desde el inicio diferentes capacidades, formas de interacción y contextos de uso" — **no dice "a personas con discapacidad"**, dice "a todo el mundo, con o sin discapacidad". Flujo: encontrar una obra → revisar información → añadir al carrito. Tarea principal: explorar/buscar, identificar la obra, acceder a la info, decidir, añadir al carrito, **identificar que la obra fue añadida** (este último paso se destaca a propósito: cuando algo cambia solo visualmente — como el contador del carrito — hace falta una alerta en vivo vía ARIA para que quien usa lector de pantalla también lo perciba).

## Flujos de proyecto presentados por los alumnos (y cómo se acotaron)

| Alumno/a | Idea original | Acotación acordada |
|---|---|---|
| **Gaby** (Speaker 4 / Carlos — ejemplo del facilitador) | Comprar un pasaje de tren en Trenes Argentinos (con CUD — Certificado Único de Discapacidad) | Diseñar el flujo **hasta antes de la compra**, con confirmación clara de fecha/asiento. Se descartó el flujo completo de compra por ser demasiado extenso; foco en el calendario (no accesible por teclado, trampa de foco, fechas deshabilitadas sin feedback) |
| **Bárbara** | Sitio de tutoriales de digitalización para personas mayores (WhatsApp, apps) | Un flujo específico de tutorial (ya probado con usuarios reales: prefieren ver todos los pasos juntos en una sola pantalla en vez de un stepper paso a paso, porque necesitan comparar y sentirse seguras — hallazgo real de sus propios tests, no un criterio WCAG) |
| **Estibaliz** | App de gestión de energía para personas con TDAH/neurodivergencia/dolor crónico (proyecto propio, para uso personal) | Pendiente de cerrar encuesta de validación de funcionalidad antes de elegir flujo final; se descartó de entrada la funcionalidad de "sugerencias con IA" por requerir un modelo entrenado, fuera de alcance |
| **Camille** | Agenda de sesiones de kinesioterapia de Clínica Meds (Chile) | Acotado **solo a la agenda** (seleccionar y guardar hasta 10 horas de sesión), asumiendo usuaria ya logueada y con profesional/centro médico ya seleccionados — se descartó rediseñar todo el flujo de registro/previsión social por ser excesivo |
| **Carol** | Comprar entrada de teatro | Desde la ficha de la obra hasta la selección de butaca, **antes del pago** — se identificó que el mapa de butacas no es accesible por teclado; también se detectó un límite de tiempo de sesión sin alternativa de extensión (criterio de accesibilidad real) |
| **Sara** | Marketplace de productos para mascotas | Categoría de producto → página de producto → desplegable del carrito. Barreras ya detectadas: filtros no navegables por teclado, texto justificado con "ríos" visuales, imágenes de producto inconsistentes entre vendedores, un banner que es una imagen con texto embebido |

Patrón repetido en varias correcciones de Consuelo: achicar el alcance a lo mínimo indispensable para que el ejercicio de documentación sea manejable en 10 semanas — "no hace falta rediseñar la plataforma completa, bastan 2-4 pantallas con un componente simple y uno complejo".

## Otros datos y ejemplos mencionados al pasar

- **Patrón oscuro (dark pattern)**: mostrar "últimas unidades" en la mayoría de los productos de un catálogo (como en el marketplace de mascotas de Sara) pierde su propósito de urgencia real y es una práctica cuestionable, además de un problema de confianza/diseño más allá de la accesibilidad pura.
- **Botones/objetivos interactivos**: WCAG exige mínimo 24×24px; en mobile es común subir a 44×44px — no es obligación pero mejora la experiencia y "se ve más moderno".
- **Alineación de texto**: preferir alineación a la izquierda; el texto centrado solo es aceptable en títulos cortos (2-3 líneas). El texto justificado genera "ríos" visuales (espacios irregulares) que empeoran con pantallas anchas sin ancho máximo definido.
- **Mayúsculas sostenidas** en títulos largos son una tortura de lectura para personas con dislexia (coincide con lo mencionado antes sobre el código).
- **Tipos de imagen según función** (se profundizará en próximos módulos): descriptivas, informativas, decorativas, y de texto (ej. un banner donde el texto es parte de la imagen — el alt debe ser el texto exacto que aparece). Consuelo comentó que está desarrollando un modelo de IA propio para generar automáticamente texto alternativo de imágenes informativas (ej. tablas nutricionales), aunque reconoce que un alt no debería superar ~150 caracteres y esa cantidad de info a veces es mucho mayor — hay que decidir dónde va el resto de esa información.
- **Modo lectura del navegador** (Chrome, Firefox, Safari) — función nativa que lee el texto de la página en voz alta sin leer todo lo demás (menús, distractores); alternativa gratuita a instalar un plugin de lectura de texto.
- **Modelo de la prescindencia** (mencionado pero deliberadamente no incluido en el curso de modelos teóricos por no ser parte del temario CIPAC): modelo histórico/religioso en desuso que todavía aparece en frases coloquiales como "tener una bendición" o "castigo divino" al hablar de discapacidad — viene arrastrado desde la Edad Media.

## Carga de trabajo del Módulo 1 (feedback a la plataforma)

- Estimado original: ~2-3 horas de contenido + 2 horas de clase en vivo = ~5 horas semanales, más el tiempo que cada quien quiera dedicar al proyecto (poco al principio, pero crece con los módulos).
- Según las estadísticas de la plataforma, **solo la mitad de los alumnos había terminado el Módulo 1** para esta clase. Algunos alumnos confirmaron que les tomó más (toda la semana, trabajando un poco cada día) — una alumna con dislexia reportó que le toma más tiempo por su condición.
- Carlos advirtió que **los módulos 1, 2 y 3 son los más livianos**; la carga aumenta notablemente a partir del módulo 4. Se está considerando reducir la cantidad de ejercicios si hace falta.
- Se están preparando materiales descargables en PDF/diapositivas para quienes prefieren imprimir y subrayar.
- Se pidió feedback continuo sobre la plataforma — al ser desarrollada por el propio equipo (Carlos), los problemas reportados se pueden solucionar/mejorar rápido cuando es viable.

## Próximos pasos

- Consuelo: buscar y compartir por Discord el video de Apple sobre accesibilidad en software.
- Carlos: publicar la grabación de la clase con los enlaces compartidos durante la sesión y el dato del "modo lectura" del navegador.
- Estibaliz: cerrar la encuesta de validación el fin de semana, elegir el flujo definitivo y compartirlo para revisar su viabilidad.
- Todos los alumnos: copiar la ficha del brief a su propio Figma y avanzar en completarla antes de la próxima tutoría.
