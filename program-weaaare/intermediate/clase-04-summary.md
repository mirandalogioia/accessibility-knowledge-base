---
title: "Clase 4 — Tutoría: repaso de WCAG criterio por criterio (perceptible, distinguible y operable)"
status: in_progress
source: ../raw-inputs/clase-04-raw.txt
last_updated: 2026-10-21
---

# Clase 4 — Tutoría de Diseño Accesible (weAAAre)

Tutoría dedicada a repasar la WCAG "criterio por criterio" desde la mirada de diseño. Se cubrió el principio **Perceptible** completo (pautas 1.1 a 1.4) y parte de **Operable** (2.1, 2.2, 2.4.11, 2.5, etiqueta en el nombre). No se alcanzó a ver todo: el detalle con ejemplos y enlaces queda en un documento que se comparte después. Se decidió no ver proyectos en esta sesión (para eso están Discord y el correo).

## Estructura de la WCAG

- **Principios (POUR):** Perceptible, Operable, Comprensible (*understandable*), Robusto. Se pueden recordar con la palabra *pour*.
  - **Perceptible:** ¿puede percibir el contenido quien no ve, quien es daltónico, quien tiene baja visión?
  - **Operable:** uso con distintas tecnologías; en la práctica, **teclado** y lector de pantalla.
  - **Comprensible:** carga cognitiva (idioma definido, partes con nombre, etc.).
  - **Robusto:** compatible con tecnologías actuales y futuras (navegador, móvil, escritorio).
- **Pautas** = objetivo que agrupa; **criterios** = lo verificable, con nivel. Las comprobaciones son binarias: cumple / no cumple.
- Estrategia de estudio de la profesora: entender primero las **excepciones** de cada criterio; así se entiende lo que sí se pide.
- Las WCAG son un estándar del W3C; no es ajeno a intereses de empresas que pagan por tener asiento en el grupo (ej. Google y el captcha).

## Pauta 1.1 — Alternativas textuales

Todo contenido que no sea texto necesita una representación en texto, porque el texto es lo más accesible para cualquier tecnología de apoyo. No implica eliminar videos o imágenes: se puede tener un diseño moderno y accesible.

### Tipos de imagen

| Tipo | Qué es | Texto alternativo |
|---|---|---|
| **Decorativa** | Si se quita, la información se entiende igual | `alt=""` (vacío); la tecnología de apoyo la salta |
| **Informativa** | El contenido está en la imagen y no en otra parte (ej. instructivo de armado, nudo de corbata) | Describe lo esencial |
| **Funcional** | Es parte de un botón o enlace | El **verbo de la acción** ("buscar", "guardar"), no "lupa" ni "zoom" |
| **De texto** | Banner con texto incrustado (criterio 1.4.5) | Copiar exacto el texto que aparece en la imagen |

- Sin `alt`, la tecnología de apoyo "compensa" y puede leer el nombre del archivo o la ruta.
- **Si el icono tiene texto visible al lado** (ej. disquete + "Guardar"), el icono es decorativo: ponerle alt sería redundante.
- Redes sociales: el lector anuncia "enlace Facebook", "enlace LinkedIn"; decidir si se agrega el nombre de la marca ("Instagram de X") o solo la red.
- Imagen de error 404 con "¡Ups!" incrustado: no puede ser decorativa; el alt debe comunicar el error.
- Código QR: indicar que es un QR para descargar la app.

### Buenas prácticas del alt

- Unos **120 caracteres** como referencia ("piénsenlo como un tuit"); no sobredescribir.
- **No empezar con "imagen de…"**: el lector ya anuncia el rol; decirlo dos veces es redundante.
- Información más importante al inicio; claro y conciso.
- Se puede usar IA para generarlos, pero **validar** el resultado.
- Hay tensión entre el estándar (decorativas con alt vacío) y parte de las personas con discapacidad que prefieren que todo tenga descripción; ejemplo citado: NASA describe con nombre y apellido a cada persona en la foto de Artemis II. Conviene **preguntar a la persona usuaria**.
- **Gráficos:** el alt dice de qué se trata (ej. ventas del trimestre); si hace falta más, una **descripción larga** accesible vía enlace, botón (texto oculto/visible), modal o página nueva.
- Recurso mencionado: asistente tipo *wizard* (mapa de decisión) para generar alt guiado por contexto; **solo genera, no evalúa**. Se compartió por el chat y se suma a los recursos de weAAAre.

### Excepciones del 1.1.1

| Excepción | Qué se hace |
|---|---|
| **Controles y formularios** | No se resuelve con alt sino con etiqueta (criterio 4.1.2 / 1.3.1). Ojo: un icono dentro (ej. buscar) sí es imagen funcional y necesita nombre accesible |
| **Multimedia dependiente del tiempo** | Descripción breve de qué es el video + pauta 1.2 |
| **Pruebas / tests** | Alt que nombra el tipo de prueba ("prueba visual"), sin dar la respuesta |
| **Experiencias sensoriales** | Identificación descriptiva (obra y artista); ej. recorridos 3D, experiencias inmersivas |
| **Captcha** | Texto que indique la alternativa ("si no puedes ver la imagen, pulsa el botón de audio"); debe existir alternativa no visual |

- **Captcha:** el de elegir bicicletas/puentes no es accesible sin alternativa. Opciones más simples: operación matemática sencilla o "haz clic si eres humano". Incluso con audio queda fuera la persona sordociega. "No hay mejor captcha que el que no se usa" (seguridad desde backend).
- **Caso TGR** (Tesorería General de la República, cliente de la profesora; el caso está publicado en el sitio de Globalize, su empresa): los logos de bancos estaban marcados como decorativos, así que una persona ciega no sabía cómo pagar. Al nombrar cada banco ("Banco de Chile", "BCI", etc.), junto con el resto de mejoras de accesibilidad incluyendo teclado, la recaudación subió cerca de un **80%**.

## Pauta 1.2 — Multimedia (contenido dependiente del tiempo)

Cubre solo audio, solo video y audio-video. Los niveles varían: subtítulos y audiodescripción de contenido **pregrabado** son A/AA (1.2.2, 1.2.5), subtítulos en directo es AA (1.2.4), y lo más exigente es AAA (audiodescripción extendida 1.2.7, lengua de señas 1.2.6, audio en directo 1.2.9).

- **Audiodescripción:** audio que describe lo que solo se ve, aprovechando los silencios del diálogo (se mostró un ejemplo con *El Rey León*).
- **Subtítulos:**
  - *Closed caption*: se activan/desactivan (ej. YouTube).
  - *Open caption*: incrustados en el video.
  - Deben estar sincronizados, **no omitir palabras** e incluir **sonidos relevantes** (disparos, puerta que cruje, ruido ensordecedor).
- **Transcripción:** todo lo dicho en texto, incluidos aplausos y sonidos; puede estar visible y sincronizada (seleccionar texto lleva al momento del video) o ser un archivo descargable.
- La profesora compartirá una tabla resumen (el documento de apoyo tiene 157 páginas).

## Pauta 1.3 — Contenido adaptable

La información tiene que poder interpretarse de distintas maneras sin perder significado. Incluye información y relaciones (1.3.1), secuencia significativa (1.3.2), características sensoriales (1.3.3), orientación (1.3.4) y propósito de la entrada (1.3.5).

### Información y relaciones (1.3.1): estructura

Lo que se entiende visualmente debe transmitirse en el código ("teoría de conjuntos": agrupar lo que se lee junto y separar lo que no).

**Landmarks** (los usa la tecnología de apoyo para navegar con atajos):

| Landmark | Contenido |
|---|---|
| `header` (*banner*) | Lo que se mantiene estable arriba: logo, buscador, menú |
| `nav` | Menús de navegación; si hay más de uno con el mismo propósito, **nombre accesible con `aria-label`** (ej. "Idioma", "Principal") |
| `main` | Contenido central, lo que cambia en cada página |
| `aside` | Contenido complementario (no es solo "barra lateral"); un menú dentro de un aside se marca además como `nav` |
| `footer` | Lo que se mantiene estable abajo |

- `header`, `main`, `aside` y `footer` **no van contenidos dentro de otro landmark**; sí pueden contener `nav`.
- En el footer, marcar `nav` es opcional porque las personas ya saben que ahí hay enlaces; pero **si se marca uno, se marcan todos**.
- Extensión de Chrome recomendada: **Landmark Navigation via Keyboard**.

**Encabezados (H1–H6):**
- **Un H1 por página**, que la distingue de otros sitios y de otras páginas del mismo sitio; no tiene que ser el texto más grande.
- Secciones H2, subsecciones H3, etc., **sin saltar niveles** ("no hay nietos sin padre"); rara vez se llega a H6.
- No elegir un nivel por tamaño visual: por eso el sistema de diseño debe ser flexible en tamaños (se retoma en el módulo 6).
- Un encabezado es un texto corto que agrupa información; un texto grande sigue siendo un párrafo.
- El título de una card suele ser H3 (está dentro de una sección), pero varía según la pantalla: **el nivel se marca en la interfaz, no en el componente del sistema de diseño**.
- Herramienta: complemento **HeadingsMap** (resultado en W3C como ejemplo).

**Otras estructuras:**
- Grupos de formulario (radio, checkbox): `fieldset` + `legend`; con flechas se cambia dentro del grupo. Rara vez se pide documentarlo a este nivel.
- **Listas numeradas (`ol`) y no numeradas (`ul`)**: el lector anuncia cuántos elementos tiene. El número lo genera el código, no se escribe a mano; un párrafo con bullet no es lista para la tecnología de apoyo. Los menús de navegación deberían ser listas dentro del `nav`.

### Secuencia significativa (1.3.2)

- El orden de lectura y de foco debe tener sentido (arriba→abajo, izquierda→derecha). **No existe un orden correcto único, pero hay que marcarlo** de forma intencional cuando hay dudas.
- Ejemplo de banner de cookies: debería recibir el foco primero (bloquea el sitio), antes del enlace "Saltar al contenido".
- **Modal:** orden = cerrar → confirmar → cancelar, y el **foco queda atrapado** dentro. Esto sí se documenta en el sistema de diseño (comportamiento de la modal). No se recomienda un patrón con Tab interno extraño.
- Card: el lector debería leer primero el título y luego imagen/precio; si el orden visual lleva al alt de la imagen antes que al título, se reordena para que coincida visual y auditivo.

### Otros criterios de la pauta

- **Características sensoriales (1.3.3):** las instrucciones no pueden darse solo por color (y similares).
  - Ejemplo de selector de colores: mostrar color **y nombre** del color (ej. "Velvet Teddy"), así nadie se equivoca.
  - Enlaces solo diferenciados por color; verde = continuar / rojo = rechazar (daltonismo).
- **Orientación (1.3.4):** el contenido no restringe su visualización a una sola orientación de pantalla (reflow es otro criterio).
- **Identificar el propósito de la entrada (1.3.5):** cada campo debe indicar qué dato pide (ej. nombre); se implementa en código.

## Pauta 1.4 — Contenido distinguible

### Uso del color (1.4.1)

- La información no puede depender solo del color. Preguntarse: **¿se entiende sin el color?**
- **Gráficos (ej. torta):** sumar texto, separación entre porciones y **texturas** (puntos, rayas horizontales/verticales/diagonales). Sirve para daltonismo y escala de grises.
- Los tooltips resuelven un problema pero crean otro (acceso por teclado, 2.1.1); solución más robusta: alt corto del gráfico + **descripción larga** con los datos reales (ej. "España, 32% del público").
- **Estados de error en formularios:** un borde rojo del mismo grosor comunica solo por color. Combinar: borde más grueso + icono de error + texto que explique **cómo recuperarse** (otro criterio).

### Control del audio (1.4.2)

- Si un audio se reproduce solo por más de 3 segundos, debe poder pausarse o detenerse.

### Contraste

| Elemento | Contraste mínimo (AA) |
|---|---|
| Texto normal | 4.5:1 |
| Texto grande | 3:1 |
| Iconos, bordes de inputs, borde de foco (no texto, 1.4.11) | 3:1 |
| Texto normal, nivel AAA (1.4.6) | 7:1 (texto grande: 4.5:1) |

- Regla práctica: si no es texto normal, es 3:1.
- **Texto grande:** **18 pt** o **14 pt en bold** (la WCAG habla de puntos, no de píxeles). Equivalencias que dio la profesora para diseño: ≈**24 px** y ≈**19 px en bold**.
- **Excepciones:** logotipos y elementos inhabilitados. El texto del **placeholder** sí necesita 4.5:1 (no es decorativo), aunque es mejor evitar usarlo.
- **Inputs:** deben tener borde (puede ser solo la línea inferior) o un **fondo** con contraste 3:1 contra el fondo de la página, y 4.5:1 con el texto interior.
- **Botones:** primario, secundario y *ghost*; el ghost siempre aparece junto a otro y lleva la palabra subrayada; en ellos ayuda el tamaño (24×24).
- **Foco del teclado:** todo elemento interactivo debe tener foco visible. Para cumplir **AAA** (2.4.13 Apariencia del foco) la profesora indicó indicador de **2 px** y contraste 3:1 por fuera y por dentro, además de compararse con el estado previo sin foco (el resumen de `resources/` solo dice que el criterio fija umbrales de tamaño y contraste, sin detallarlos).
- **Enlaces:** la WCAG acepta subrayado solo al pasar el cursor, pero por pruebas con usuarios con discapacidad cognitiva la profesora recomienda **subrayado permanente**.
- Enlace vs botón: da lo mismo cómo se vea; importa el código. **Enlace = cambia de contexto** (otra página, sección, descarga); **botón = ejecuta una acción** en la misma interfaz (ej. mostrar/ocultar contraseña).
- Herramientas: calculadora de contraste web (foreground/background; muestra AA/AAA para texto, texto grande e interfaz), plugin **Stark** en Figma, extensión **WAVE** para auditar (ejemplo: botón "Mostrar" de un banco con 3.05:1 al necesitar 4.5:1).

### Otros criterios

- **Cambio de tamaño del texto:** poder ampliar hasta **200%** sin pérdida de contenido o funcionalidad; probar también el menú y que nada quede solapado.
  - Zoom en el navegador: Ctrl/Cmd + `+`, `-`, `0`.
- **Imágenes de texto (1.4.5, AA):** usar texto real; excepciones: presentación visual esencial (logotipos, una tipografía específica) o que la persona pueda personalizar la imagen, siempre con alternativa textual. Mejor: texto real en HTML con la imagen de fondo.
- **Reflow:** sin scroll en dos direcciones; excepciones razonables: tablas y carruseles contenidos.
- **Gestos y carruseles:** aceptados si hay alternativa al gesto (flechas, botones, indicadores clicables).

## Principio Operable

- Las otras tecnologías de apoyo (pulsadores, soplido, mirada, voz, etc.) **dependen del teclado**: basta probar con **teclado y lector de pantalla**.
- **Árbol de accesibilidad:** versión del DOM con la semántica (botón, enlace, encabezado); de ahí leen las tecnologías de apoyo.

### Criterios revisados

| Criterio | Idea clave |
|---|---|
| **2.1.1 Teclado** | Todo lo que se usa con mouse debe usarse con teclado |
| **2.1.2 Sin trampas de teclado** | Si el foco entra con teclado, tiene que poder salir; una modal abierta con teclado se cierra con teclado (Esc) |
| **2.1.4 Atajos de teclado** | No reasignar atajos existentes; "no inventar la rueda" |
| **2.2.1 Tiempo ajustable** | Poder desactivar, ajustar o ampliar (mín. 10 veces) el límite de tiempo (ej. "¿sigues ahí?"). Excepciones: tiempo real/esencial (subastas), límite ≥ 20 horas |
| **2.2.2 Poner en pausa, detener, ocultar** | Algo que se mueve solo debe poder detenerse (carrusel, contador, divisas). Preferible movimiento a pedido o evitar el carrusel |
| **2.4.11 Foco no oculto** | El componente enfocado no queda completamente tapado por contenido del autor |
| **2.5.1 Gestos con el puntero** | Gestos multipunto o de trayectoria necesitan alternativa de un solo puntero (ej. unir conceptos con dos clics en lugar de arrastrar; botones de zoom en mapas; botones de rotar/cortar en editor de fotos) |
| **2.5.2 Cancelación del puntero** | Activar al soltar, poder cancelar o deshacer (ej. transferencia hecha por error); es 100% desarrollo |
| **2.5.3 Etiqueta en el nombre** | El texto visible debe coincidir con el nombre programático, para quien navega por voz |

- **Teclas básicas:** Tab / Shift+Tab, flechas (listas, menús, pestañas), Espacio y Enter (activar), Esc (cerrar modales).
- **Modal documentada:** título H1; botón cerrar con `aria-label="Cerrar modal"`; orden de foco 1 cerrar, 2 confirmar, 3 cancelar, con foco cíclico.
- La accesibilidad se trata un poco de **ser redundante**: si no funciona por una vía, existe otra.
- Un criterio de WCAG 2.0 (cierre de etiquetas, 4.1.1) se eliminó porque las tecnologías de apoyo ya lo resuelven.
- Los **overlays** se rechazan: dan la falsa idea de que se resolvió la accesibilidad.
- Ejercicio sugerido: navegar con teclado la sección de actividades de la plataforma del curso, que está preparada para funcionar con teclado.

## Qué se documenta y dónde

- **En la interfaz (pantalla completa):** niveles de encabezado, landmarks, orden de foco, texto alternativo.
- **En el sistema de diseño (componente):** comportamiento del foco (ej. modal) y cosas que siempre se comportan igual. Se profundiza en el **módulo 6**.

## Próximos pasos

- Profesora: subir el documento y materiales de la sesión; pedir a Carlos que avise por Discord y correo cuándo activar la cuenta de IA; responder la duda que una alumna dejó en Discord.
- Alumnas: avanzar en el **diseño visual** y llegar con **al menos un componente** al próximo miércoles.
- Alumnas: **no activar la cuenta de IA** (Claude u otra) antes de la sesión con Carlos; las próximas tres semanas se documentan los componentes con IA para generar un sistema de diseño vivo en **Storybook** (costo estimado 20–30 USD por un mes).
- Dudas: Discord (la profesora lee de noche); urgencias por WhatsApp.

## Notas de transcripción

- Siglas mal transcritas en el audio y corregidas por contexto: WCAG ("Wicat", "Wicac"), CPACC ("CIPAC"), IAAP ("IAP"), `aria-label` ("area label"), Stark ("Start"), Claude ("Cloud"), HeadingsMap ("heading map"), modal ("modual"/"modales").
- Nombres confirmados: "Olga Carrera" es una persona real (autora del wizard/formulario de alt text) y Globalize es la empresa de la profesora.
- Dejado fuera por no ser contenido de la clase: charlas laterales (colegio, familia, gustos musicales, teléfono de contacto).

## Correcciones respecto a la WCAG

Lo dicho en el audio que no coincide con `resources/wcag22-understanding/` (que se toma como referencia). El cuerpo del resumen ya usa los valores corregidos.

- **Robusto:** el audio dice que tiene "un solo criterio". En WCAG 2.2 son **4.1.2** (nombre, rol, valor, A) y **4.1.3** (mensajes de estado, AA); el 4.1.1 (procesamiento) está retirado.
- **Niveles AAA:** el audio dice que son AAA los criterios "demasiado difíciles, como la audiodescripción" o los de contenido en vivo. Según la referencia, la audiodescripción pregrabada es **AA (1.2.5)**, los subtítulos en directo son **AA (1.2.4)**; son AAA la audiodescripción extendida (1.2.7), la lengua de señas (1.2.6) y el audio en directo (1.2.9).
- **Foco de 2 px:** en el audio se asocia al "1.4.1" por confusión de numeración; corresponde a **2.4.13 Apariencia del foco (AAA)**. La referencia no detalla el umbral de 2 px ni el 3:1.
- **Texto grande:** la WCAG define 18 pt o 14 pt en bold; los 24 px y 19 px son equivalencias aproximadas de la profesora.
- **1.4.5 Imágenes de texto:** la excepción es presentación visual esencial (logotipos, tipografía específica) o personalizable por la persona; no "cuando la imagen pierde su significado".
- Criterios citados verificados en `resources/wcag22-understanding/`: 1.1.1, 1.2.x, 1.3.1–1.3.5, 1.4.1–1.4.6, 1.4.10, 1.4.11, 2.1.1, 2.1.2, 2.1.4, 2.2.1, 2.2.2, 2.4.11, 2.4.13, 2.5.1–2.5.3, 2.5.8.
