---
title: "Módulo 1 — Diseñar para la diversidad"
status: draft
source: "raw-inputs/modulo-01-raw.rtf (audio de las lecciones) + raw-inputs/modulo-01-contenido-escrito-raw.txt (texto escrito de la plataforma)"
last_updated: 2026-10-02
---

# Módulo 1 — Diseñar para la diversidad

Resumen consolidado del Módulo 1, fusionando la explicación en video (Consuelo Correa Barros) con el contenido escrito de cada lección en la plataforma. Cubre las lecciones 1.2 a 1.11 (se omite 1.1 "Bienvenida al intensivo" por no tener contenido sustantivo, y 1.12 "Tutoría" / 1.13 "Examen" por ser instancias en vivo / evaluativas, no contenido de la knowledge base).

## 1.2 — Qué significa diseñar de manera accesible

La accesibilidad permite que un producto/servicio digital sea usado por personas con **distintas capacidades**, formas de interacción y contextos. Habilita **percibir** el contenido, **comprender** qué hacer, y **navegar/interactuar** para completarlo. Es un **atributo de calidad**: una experiencia no está terminada si excluye a un grupo de usuarios.

Toda pantalla esconde decisiones de accesibilidad, incluso una simple ficha (ejemplo recurrente: una card para reservar una ruta de senderismo, con foto, título, video, campo de correo y botón):

1. **La foto** — ¿informa o decora? Si informa, hay que decidir qué cuenta a quien no la ve.
2. **El título** — tiene que ser semánticamente un título (no solo letra grande), para que un lector de pantalla pueda saltar a él.
3. **Los colores** — deben leerse bien sobre el fondo, también a pleno sol.
4. **El video** — subtítulos para quien no oye, descripción de lo que solo se ve para quien no ve.
5. **El campo de formulario** — etiqueta visible que diga qué dato va, antes de empezar a escribir.
6. **El botón** — alcanzable y activable sin ratón, con un nombre que diga lo que hace.

Si el diseño no toma estas decisiones, se toman igual mas **por omisión** — ej. un lector de pantalla termina leyendo el nombre de archivo de una imagen sin alt text (`IMG_4032.jpg`).

**Dos escenarios de trabajo:**
- **Diseñar desde cero**: la accesibilidad entra antes de dibujar — en los requisitos, en a quién se investiga, en los bocetos. Cambiar algo en esta etapa es barato.
- **Remediar lo que ya existe**: no se empieza por diseñar sino por **saber qué pasa** (evidencia). Cada fuente enseña una parte: una auditoría dice qué incumple y dónde (no cuánto le cuesta a una persona); pruebas con personas con discapacidad muestran dónde se atascan (solo en lo que se probó); las quejas a soporte reflejan lo que molesta lo bastante como para escribir (no a quien abandona sin avisar). Si la barrera nace en un componente, se arregla en el componente, no pantalla por pantalla.

"Terminado" también debería implicar accesible, pero «que sea accesible» no es una condición verificable por sí sola — lo que funciona son criterios comprobables por cualquiera sin conocer una norma (ej. para un formulario de contacto: etiquetas visibles, se completa y envía solo con teclado, los errores dicen qué corregir, la confirmación llega también a lector de pantalla).

## 1.3 — Diversidad de personas y necesidades

Una etiqueta de diagnóstico (ej. "discapacidad visual") dice muy poco: no indica qué herramienta usa la persona, desde cuándo convive con la condición, ni su nivel de dominio de la tecnología. Caso ilustrativo: **Samuel** (ciego hace 20 años, usa lector de pantalla con atajos), **Inés** (baja visión, amplía la pantalla y necesita que lo que busca esté cerca) y **Rosa** (perdió la vista hace poco, recién aprendiendo el lector, se atasca mucho antes que Samuel) — mismo diagnóstico amplio, experiencias muy distintas.

De ahí tres ideas: la etiqueta no dice qué herramienta usa nadie; la experiencia cambia la barrera (un trámite de un minuto para uno puede ser un muro para otro); las necesidades se suman y cambian (con la edad se suele perder precisión visual, auditiva y motriz a la vez, y hay discapacidades no visibles como las cognitivas).

**Datos (España, encuesta EDAD 2020 del INE):** 4,38 millones de personas con discapacidad en hogares; 3 de cada 4 tienen 55+ años. La limitación más frecuente **no es visual sino de movilidad** (54 de cada mil personas de 6+ años, vs. 23,6 de discapacidad visual) — contradice la creencia de que "accesibilidad = personas ciegas".

**Una necesidad, tres orígenes** (modelo del diseño inclusivo de Microsoft): **permanente** (vive con la condición), **temporal** (ej. otitis), **situacional** (ej. sin auriculares en el transporte). Los subtítulos resuelven los tres casos — útil para ver hasta dónde llega una solución, pero con dos cuidados: lo situacional ayuda a que el equipo entienda el problema pero no equivale a vivir con la condición (quien va en el autobús recupera el sonido al bajarse; quien es sorda, no), y "temporal" no significa "leve".

**Una persona no es su colectivo** — para que la investigación no engañe: agrupar por lo que la persona necesita *poder hacer* (ver, oír, pulsar con precisión, entender, recordar), no solo por diagnóstico o herramienta; reclutar más de una persona por grupo con distinta experiencia; no buscarlas todas en el mismo sitio (misma asociación → mismas herramientas/costumbres); separar lo que se repite de lo que le pasa solo a algunas, y documentar qué no se probó.

## 1.4 — Diversidad de formas de interacción con productos digitales

Toda tarea digital se reduce a dos cosas: **recibir** información (percibir + comprender, vía vista, oído, braille, etc.) y **actuar** (interactuar vía teclado, mouse/puntero, voz, tacto, pulsador). Cada paso de un diseño da por hecha una forma de hacer ambas cosas — el problema aparece cuando solo contempla una.

Ejemplo (elegir sesión de cine): quien usa ratón apunta y hace clic; quien usa teclado salta con Tab y activa con Enter/Espacio; quien usa lector de pantalla escucha cada opción antes de elegir; quien va de pie en el transporte toca con el pulgar, con una sola mano. Todos buscan el mismo resultado — el diseño debe permitir llegar a él por cualquiera de los caminos.

El **foco** (cuando se navega por teclado) es el elemento activo en ese momento — donde ocurre lo que se pulsa; normalmente se ve como un borde/resaltado.

**Dos caminos son equivalentes cuando:** llegan al mismo resultado, muestran lo mismo, y cuestan un esfuerzo parecido (30 pulsaciones vs. 1 clic no es una alternativa razonable). Ejemplo clásico: un calendario manejable por teclado es accesible pero, para una fecha de nacimiento lejana, puede ser un castigo si solo permite avanzar mes a mes — la solución es permitir también **escribir la fecha directamente**, declarando el formato con precisión.

**Cuando la única vía falla** (caso recuperación de cuenta/contraseña): si solo existe reconocimiento facial, quedan fuera quienes la cámara no reconoce, quienes no pueden posicionarse frente a ella, o quienes no ven para encuadrar. "Ir a una oficina" no es alternativa — es otra tarea, en otro lugar, en otro momento. Para validar si una vía alternativa es real, 3 preguntas: ¿la persona puede completarla **sola**? ¿desde el **mismo dispositivo** y **momento**? ¿es **igual de segura** que la principal? (Enlace al correo, códigos de recuperación guardados, o llave de acceso desbloqueada con huella/cara/PIN cumplen las tres; las preguntas de seguridad tipo "¿nombre de tu primer colegio?" se desaconsejan hoy porque son averiguables). **WCAG 3.3.8 Autenticación accesible (mínima), nivel AA**: el login/recuperación no puede depender únicamente de memorizar, copiar a mano o resolver un acertijo.

## 1.5 — Tecnologías de apoyo

Misma página, tres personas (Samuel con lector de pantalla, Inés con ampliador ×4, Óscar con temblor en las manos que usa control por voz) reciben cosas distintas de ella. El diseño no elige qué herramienta usan; sí decide si les funciona. **Ninguna tecnología de apoyo adivina**: trabaja únicamente con lo que el diseño/código le da.

| Tecnología | Qué hace |
|---|---|
| **Lector de pantalla** | Convierte la interfaz en voz o braille actualizable (línea de puntos). Solo tiene lo escrito en el código: nombre de cada control, qué es, títulos de página. |
| **Ampliador** | Agranda una parte de la pantalla (a ×4 ve ~1/16 de lo que ve alguien sin ampliar); lo que aparece lejos de donde mira, no lo ve. |
| **Control por voz** | La persona dice lo que ve en pantalla para activarlo. |
| **Pulsador con barrido** | El sistema resalta opciones una a una; la persona pulsa cuando llega la deseada — cada elemento de más es una espera. |
| **Teclados adaptados, punteros por cabeza, seguimiento ocular** | Muchos terminan enviando pulsaciones de teclado o clics — por eso que *todo* funcione con teclado es la base de casi todo lo demás. |
| **CAA (comunicación aumentativa y alternativa)** | Pictogramas/símbolos/teclados que se transforman en mensaje de voz sintética — apoya a personas con dificultades del habla. |

**No basta con que algo parezca un botón** — un lector de pantalla lo reconoce por tres datos del código: **nombre** (ej. "Apuntarme"), **función** (botón/enlace/casilla/pestaña) y **estado** (pulsado/seleccionado/desplegado/desactivado). Si se construye como un bloque que solo reacciona al clic, se ve igual pero el lector no anuncia "botón", el teclado no llega y el control por voz no lo encuentra. Con controles HTML nativos estos 3 datos vienen de serie; el riesgo está en los hechos a medida. **WCAG 4.1.2 Nombre, función, valor — nivel A**. Conviene documentarlo junto a cada componente sin necesidad de código: «Botón · Apuntarme · desactivado si no quedan plazas».

**Decir lo que se ve**: si el control por voz necesita que la orden hablada coincida con el nombre accesible, un botón que se *ve* como "Apuntarme" pero se *llama* internamente "Inscribirse en el taller" no es encontrado — aunque el nombre interno sea correcto y descriptivo. **WCAG 2.5.3 Etiqueta en el nombre, nivel A**: el nombre de un control debe contener su texto visible, idealmente al principio. (Los íconos sin texto quedan fuera del criterio formal, pero no del problema.)

**Respetar lo ya ajustado**: mucha gente configuró su dispositivo de antemano (letra más grande, contraste, modo oscuro, menos animaciones, subtítulos activados) — son ajustes de sistema/navegador que la persona espera ver respetados en cualquier app. Las preferencias propias del producto (ej. selector de tema) suman pero no sustituyen: si alguien pidió menos movimiento, las tarjetas no deberían rebotar igual; si subió el tamaño de letra, la app no debería truncarla.

## 1.6 — Barreras por diseño

Una **barrera de accesibilidad** es una característica del producto que dificulta o impide realizar una tarea — la definición la ubica **en el producto, no en la persona**. Esto no es una forma amable de hablar: la **Convención de la ONU sobre los derechos de las personas con discapacidad** (vigente en España desde 2008) define la discapacidad como resultado de la interacción entre una deficiencia y las barreras del entorno — el **modelo social**. De esos dos lados, solo uno está en manos del diseño.

Caso ilustrativo: Julia (sorda) pide un certificado en la sede electrónica de su ayuntamiento, y el único método de verificación es una llamada telefónica con código dictado por voz. "Julia no puede pedir el certificado" y "el código solo llega por llamada" describen lo mismo, pero solo la segunda frase señala algo modificable por diseño.

**Cuatro formas de quedarse fuera** (parecidas a los 4 principios de WCAG, pero no lo mismo):
- **Percepción** — la información no llega (ej. un código que solo se oye).
- **Comprensión** — llega pero no se entiende (ej. aviso en lenguaje de norma técnica).
- **Interacción** — se entiende pero no se puede hacer (ej. firma que solo se dibuja con el dedo/ratón).
- **Estructura** — lo visualmente ordenado no llega ordenado a quien usa lector de pantalla (ej. "títulos" que solo lo parecen visualmente, sin marcado semántico).

Efecto: una barrera **dificulta** (la tarea se completa, pero con más tiempo/errores/esfuerzo) o **impide** (la tarea se detiene, o solo la completa alguien más por la persona) — no pesan igual al priorizar qué arreglar primero.

**Escribir la barrera, no la persona**: en vez de "los mayores no terminan el pedido" (habla de la persona, no dice qué cambiar), una barrera bien escrita nombra 4 piezas: el **elemento** del producto, el **único modo** en que funciona (la pieza más valiosa — dice dónde actuar), lo que **da por hecho** que la persona puede hacer, y el **efecto** (dificulta/impide + qué tarea). Ejemplo: «El aviso de cambio de cita de Salud Norte llega solo como mensaje de voz. Da por hecho que se oye e impide enterarse del cambio a quien no oye o no puede atender la llamada».

**Palabras que avisan** (detectables incluso antes de diseñar, al leer requisitos): "solo"/"únicamente" (¿qué otra vía hay?), "al pasar el ratón"/"arrastra"/"mantén pulsado" (¿cómo lo hace quien usa teclado o voz?), "en rojo"/"el de la derecha" (¿lo dice también un texto?), "escucha"/"te llamamos" (¿llega también por escrito?).

## 1.7 — Accesibilidad, usabilidad y experiencia de usuario

No son sinónimos. Caso: Lucía (product manager de "Banco Norte") celebra que 5 de 5 personas completaron una transferencia en menos de un minuto — buena noticia de *usabilidad*, pero no dice nada de *accesibilidad* porque las cinco usaban ratón.

- **Usabilidad** (ISO 9241-11): en qué medida las personas para las que se diseñó consiguen su objetivo, con cuánto esfuerzo y satisfacción — pero siempre se mide con personas concretas; si el grupo de prueba no incluye a nadie que use teclado/lector/ampliador, la prueba no dice nada sobre esos usuarios. Por eso "usabilidad para personas con discapacidad" no es un concepto válido — la usabilidad es para todas las personas que se incluyan al medirla.
- **Accesibilidad**: si puede hacerlo *cualquiera*, con o sin discapacidad, reciba la información como la reciba y actúe como actúe.
- **Experiencia de usuario (UX)**: el recorrido completo — antes, durante y después (confirmación por correo, soporte cuando algo falla, confianza al volver).

**Usable ≠ accesible** — pueden combinarse de 4 formas: usable e inaccesible (la transferencia de Lucía: con ratón sale en 1 minuto, con teclado no sale), accesible y poco usable (una solicitud pública alcanzable y legible con cualquier tecnología pero de 12 pantallas pidiendo datos redundantes), ninguna de las dos (PDF escaneado para imprimir/rellenar a mano/entregar en oficina), o ambas (el objetivo real).

En formularios, la distinción empieza por nombrar bien los textos: **etiqueta** (qué dato va, ej. "IBAN"), **instrucción** (cómo rellenarlo, ej. "Empieza por ES y tiene 24 caracteres"), **mensaje de error** (qué falló y cómo corregir). Una instrucción vaga como "Use un formato válido" falla en ambos frentes a la vez.

**Cada método de prueba ve una parte**: una prueba de usabilidad encuentra lo lento/confuso (pero si nadie usa tecnología de apoyo, no detecta casi ninguna barrera); una revisión por criterios (WCAG) encuentra barreras conocidas de forma ordenada (pero no dice si la tarea resulta lenta/confusa); una prueba con personas que usan tecnología de apoyo dice si la tarea se completa de verdad y con cuánto esfuerzo. La forma más simple de combinarlas no es armar un estudio aparte, sino **invitar a personas con discapacidad a las pruebas de usabilidad que ya se hacen**.

## 1.8 — Sesgos y supuestos en el proceso de diseño

Frase típica de reunión: "Las personas mayores no se aclaran con la app y no tenemos usuarios con discapacidad" — suena razonable y nadie la discute, pero contiene supuestos no comprobados.

**Cinco sesgos frecuentes en equipos de diseño:**
- **Falso consenso** — creer que los demás usan el producto como uno mismo ("nadie rellena esto con teclado" → ¿cómo lo sé, además de por mí?).
- **Confirmación** — buscar solo datos que dan la razón ("las métricas confirman que el flujo funciona" → ¿qué dato me haría cambiar de opinión?).
- **Supervivencia** — mirar solo a quien llegó al final ("quien termina el alta está contento" → ¿quién no aparece acá, y por qué?).
- **Estereotipo** — atribuir un rasgo a todo un grupo ("la gente mayor no compra online" → ¿es de las personas o de mi interfaz?).
- **Generalizar desde un caso** — tomar a una persona por todas ("se lo mostré a un amigo ciego y le pareció bien" → ¿cuántas personas, con qué tecnologías?).

**De supuesto a pregunta comprobable** — plantilla de 3 líneas: *"Creemos que..."* (lo que se supone) / *"Lo comprobaremos con..."* (cómo, con quién, cuándo) / *"Cambiaremos... si..."* (decisión escrita antes de mirar el resultado). Importa observar lo que hacen las personas, no lo que opinan ("¿te resultaría fácil?" mide cortesía, no uso real); el grupo de prueba debe incluir a alguien que no se parezca al equipo.

**Lo que la analítica no puede decirte**: un panel con "0 usuarios con discapacidad" no significa lo que parece, por 3 razones — (1) **no se debe saber**: la discapacidad es un dato de salud protegido especialmente por ley; (2) **no se puede ver**: por diseño, la web no puede detectar si alguien usa un lector de pantalla u otra tecnología de apoyo (evita que ese dato sirva para discriminar); (3) **quien tropieza se va antes**: si un paso tiene barrera, la persona abandona ahí y nunca llega a "contar" como usuaria — el cero lo fabrica, en parte, la propia barrera. Alternativas de señal indirecta: en qué paso se abandona, qué dicen las consultas a soporte ("no puedo"/"no me deja"), y qué pasa cuando alguien con tecnología de apoyo intenta la tarea.

**Fricción intencional vs. barrera no intencional**: un banco impidiendo que un menor abra cuenta corriente es una **fricción** (deliberada, con motivo, pensada para frenar a quien corresponde). Una barrera de accesibilidad es distinta: nadie la decidió, apareció porque nadie pensó en quien tropezaría. Tres preguntas las separan: ¿alguien lo decidió?, ¿para qué sirve?, ¿frena solo a quien debía frenar? (la 3ª es la que más se olvida — ej. un CAPTCHA de imágenes verifica humanidad, pero también frena a quien no puede ver las imágenes).

## 1.9 — Diseño universal y diseño inclusivo

Analogía: un cine con escalera en la entrada principal y rampa solo por la puerta trasera (junto a los contenedores de basura) — todos pueden entrar, pero no por el mismo sitio. El diseño universal busca **una sola entrada que sirva a todo el mundo**.

- **Diseño universal**: que el producto lo use todo el mundo, en la mayor medida posible, sin adaptaciones ni versiones especiales. No implica que nadie use lector de pantalla o teclado adaptado — implica que el producto funciona bien con ellos, sin "puerta aparte". Por eso una «versión accesible» separada enlazada desde la cabecera suele ser mala idea: se actualiza tarde (el equipo no la usa), tiene menos funciones, y segrega a las personas en dos grupos.
- **Diseño inclusivo**: no describe un resultado sino una forma de trabajar — empieza por quien queda fuera, trabaja con esas personas, y acepta que a veces la respuesta correcta no es una solución única sino varias (ej. subtítulos que cada cual activa según necesite, no forzados para todos). *El universal dice adónde llegar; el inclusivo, cómo llegar.*

**Origen**: el diseño universal viene del diseño físico/arquitectónico — acuñado en 1997 en el Center for Universal Design de NC State (Carolina del Norte). Es un **marco orientador**, no un estándar técnico como WCAG.

**Los 7 principios, como preguntas para revisar cualquier pantalla:**
1. **Uso equitativo** — ¿todo el mundo usa el mismo producto, con las mismas funciones?
2. **Flexibilidad** — ¿hay más de una forma de hacer cada cosa?
3. **Uso simple e intuitivo** — ¿se entiende a la primera y responde a cada acción?
4. **Información perceptible** — ¿lo importante llega por más de un canal, no solo color?
5. **Tolerancia al error** — si me equivoco, ¿tiene arreglo?
6. **Bajo esfuerzo físico** — ¿ahorra pasos y gestos repetidos?
7. **Tamaño y espacio** — ¿se puede pulsar cada cosa sin puntería fina?

No tienen medidas/umbrales (no se "cumplen" como una norma) — sirven para decidir antes de dibujar y revisar después.

**El principio 5 en detalle** (el que más decisiones concretas genera) — 4 formas de tolerar el error, cada una según el tipo de equivocación: **prevenir** (error previsible: mostrar formato de fecha, validar N° de cuenta antes de seguir), **deshacer** (error frecuente/barato/reversible: sacar algo del carrito, borrar una foto — recuperar un correo enviado), **confirmar con resumen** (error caro/irreversible: una transferencia bancaria — debe decir algo concreto: "Vas a enviar 1.500,00 € a Marta López", no un genérico "¿Está seguro?"), **guardar el avance** (tarea larga: un formulario de 12 pasos no debería reiniciarse al volver a loguearse). Ojo: si todo pide confirmación, la gente aprende a aceptar sin leer — reservarla para lo realmente caro; y el "deshacer" debe durar lo suficiente para quien tarda más en reaccionar (no 3 segundos).

## 1.10 — Pensamiento accesible: cómo detectar una barrera antes de diseñar la solución

Muchas barreras no se dibujan, **se escriben** — nacen en una frase de un documento de requisitos que da por hecho cómo es la persona, y para cuando llegan a pantalla ya tienen diseño, código y fecha de entrega.

Un requisito como «la persona identifica *visualmente* el estado de su solicitud» ya decidió que la persona ve. Si la pantalla lo cumple al pie de la letra (icono de colores), el diseño es "correcto" respecto al requisito pero deja fuera a quien no ve el icono — **el error no está en la pantalla, está una fase antes**.

Conviene releer cualquier requisito que hable de **ver/mirar/oír/arrastrar/deslizar**, que nombre un **canal único** (llamada, cámara, app) o que dé por hecha la **memoria o la prisa** (recordar un código en menos de un minuto). No siempre es un error (en una herramienta de retoque de color, ver el color sí es la tarea), pero casi siempre describe una forma de hacer algo que podría hacerse de más formas. A veces "ver" es solo una forma de hablar — "como paciente, quiero *ver* mis citas" en realidad significa *consultarlas*.

**Patrón de reescritura — conservar el qué, abrir el cómo**: donde dice "la persona tiene que **ver, oír o arrastrar** algo" → reescribir como "la persona puede **saber, elegir, cambiar o confirmar** algo". El dato, la acción y los plazos de negocio se mantienen; la forma de conseguirlo queda abierta para el diseño. Un requisito bien reescrito no nombra sentido ni movimiento (salvo que sean la tarea misma), tampoco elige ya el componente/canal (ej. "con aviso por correo" ya es una decisión de diseño que cierra otras opciones), y es comprobable sin depender de una sola capacidad.

Abrir el cómo **no significa construir una vía aparte por persona** — significa elegir una solución principal que no dependa de una sola capacidad, revisable con 3 preguntas: ¿se **percibe** sin depender de un solo sentido?, ¿se **comprende** qué está elegido y qué pasa después?, ¿se puede **hacer** sin precisión ni prisa?

**Arquetipos que sirven de verdad**: un arquetipo cambia decisiones de diseño si sus rasgos describen *cómo usa la persona la tecnología*, no un diagnóstico. Ejemplo: de Inés (68 años) sirve saber que amplía ×4, domina el ampliador pero pierde lo que queda fuera de la zona ampliada, y abandona si debe reiniciar desde cero. Dos errores a evitar: crear "el arquetipo con discapacidad" (un personaje aparte que concentra toda la accesibilidad mientras los demás "quedan igual"), y atar un requisito a un arquetipo específico ("para Rosa, que usa lector, añadimos descripción" — en vez de que **todos** los arquetipos describan su uso de tecnología y **ningún requisito dependa de cuál sea la persona**). La accesibilidad se le pide al producto, no a un personaje.

## 1.11 — Cambio de mindset en diseño

Al final de muchos proyectos aparece una lista "Accesibilidad: pendiente" que casi nunca se vacía — cada punto compite con trabajo nuevo, y cada arreglo toca algo ya construido. El cambio de mirada es simple de enunciar y exigente de practicar: **decidir antes**.

Ejemplo: un tablero tipo kanban diseñado para reordenar tarjetas solo por arrastre. Agregar después un botón "Mover a..." ya no es "agregar un botón" — hay que modificar el componente, la ayuda y las pruebas, que asumían que no existía. Como cada arreglo pequeño parece menos urgente que una función nueva, termina en una "fase 2" sin fecha.

Anticipar no exige saberlo todo — basta con 4 preguntas antes de construir cada interacción importante: ¿cuál es la tarea real? (ordenar tareas, no "arrastrar tarjetas"), ¿cuál es la vía principal?, ¿qué otra vía no depende de la misma capacidad?, ¿cómo se comprobará en el prototipo?

**El teclado es el mínimo, no toda la respuesta** — **WCAG 2.1.1 Teclado, nivel A**: todo lo que se hace con ratón debe poder hacerse con teclado (salvo lo que depende del trazo, ej. dibujar a mano alzada). Por qué importa tanto: control por voz, teclados en pantalla, pulsadores y sistemas de soplo funcionan **enviando pulsaciones de teclado** — si algo funciona con teclado, todas esas tecnologías tienen un camino. El criterio no prohíbe el ratón, pide que no sea el único camino. Pero el teclado no cubre todo: en móvil el lector de pantalla se maneja con gestos (que pueden chocar con gestos propios de la app); el control por voz necesita que el nombre accesible coincida con lo que se ve (ver 1.5); quien maneja el puntero con la mirada no pulsa teclas, necesita objetivos grandes y sin arrastre.

**Arrastrar necesita alternativa pulsable** — **WCAG 2.2, criterio 2.5.7 Movimientos de arrastre, nivel AA**: todo lo que se hace arrastrando debe poder hacerse también con toques/clics sueltos (ej. pulsar la tarjeta y luego la columna destino, o un botón "Subir"). Confusión habitual: **una alternativa solo de teclado cumple 2.1.1 pero no 2.5.7** — quien tiene temblor, usa un pulsador, o maneja el puntero con la mirada necesita *pulsar*, no *teclear*.

**Separar lo que se sabe, se asume y se cree** antes de defender una decisión: lo que el equipo **sabe** (ej. 5 personas de una prueba movieron tarjetas sin problema), lo que **asume** (que cualquiera puede arrastrar, sin haberlo validado con alguien de poca precisión manual), y lo que **cree** (que arrastrar es "más intuitivo" que un menú — eso no justifica que falte el menú). Lo que se sabe se cita; lo que se asume se comprueba; lo que se cree se prueba con personas. Decidir tarde también acarrea riesgo legal/reputacional — en España, sector público y buena parte del sector privado (banca, comercio online) están obligados a ser accesibles.

---

## Nota de alineación con la Clase 1

Varios conceptos de este módulo ya habían sido adelantados por Carlos Garrido Marín en la dinámica Kahoot de la Clase 1 (ver [`clase-01-summary.md`](./clase-01-summary.md)): tamaño mínimo de objetivo de puntero (WCAG 2.2 AA = 24×24px, no 44×44 ni 48×48), gestión del foco al cerrar modales, criterio de autenticación accesible, y cálculo del nombre accesible (`aria-label` prioriza sobre el texto visible). Este módulo profundiza la base teórica/conceptual; esos criterios WCAG específicos se retoman con más detalle en el Módulo 2 ("WCAG para diseñadores").

## Próximos pasos

- Pendiente sumar: contenido escrito de 1.1 (si aporta algo más allá de la bienvenida), y las instancias de 1.12 (Tutoría del módulo 1, miércoles 7 de octubre) una vez que ocurra — como evento en vivo, no como contenido grabado.
- 1.13 (Examen del módulo 1) se excluye deliberadamente por ser evaluación, no contenido de la knowledge base.
