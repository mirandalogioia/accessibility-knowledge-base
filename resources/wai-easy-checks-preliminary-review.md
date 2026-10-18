---
title: "Easy Checks — A First Review of Web Accessibility (W3C WAI)"
status: in_progress
last_updated: 2026-10-17
---

# Easy Checks — A First Review of Web Accessibility (W3C WAI)

Resumen de ["Easy Checks – A First Review of Web Accessibility"](https://www.w3.org/WAI/test-evaluate/preliminary/), recurso del W3C WAI para hacer una revisión preliminar rápida de accesibilidad.

Se incluye en este repo porque lo mencionó **Consuelo** (profesora del intensivo weAAAre) como algo a tener en cuenta.

## Qué es

Una guía de chequeos simples para tener una primera idea de si una página web aborda accesibilidad "de la forma más básica". El propio W3C aclara sus límites: cubre "solo algunos" problemas de accesibilidad, y una página puede pasar estos chequeos y aun así tener barreras significativas. Es un punto de partida, no un reemplazo de una evaluación completa (para eso remite a la metodología WCAG-EM y a testear con personas con discapacidad reales).

## Los chequeos

### Relacionados con texto
- **Título de página** — debe describir el contenido de forma breve y clara, y ser distinto al de otras páginas del sitio. Conviene que la información única vaya primero ("front-loaded"): mejor "Acme Web Solutions home page" que "Welcome to home page of Acme Web Solutions, Inc."
- **Texto alternativo de imágenes (alt)** — debe transmitir el mismo significado que la imagen, no solo describirla literalmente. Reglas clave:
  - Toda imagen necesita un atributo `alt` con el texto apropiado.
  - Las imágenes decorativas deben tener `alt=""` (alt nulo).
  - El texto que aparece dentro de una imagen tiene que estar incluido en el alt.
  - Información compleja (ej. gráficos) necesita un alt breve más una descripción detallada en otro lado.
  - Se puede chequear con IE WAT, la barra WebDev o WAVE.
- **Encabezados (headings)** — permiten navegar a usuarios de teclado y de lector de pantalla. Todo texto que visualmente parece un encabezado debe estar marcado como tal (`<h1>`, etc.), con una jerarquía con sentido. Chequear: que la página tenga al menos un heading, que los headings visuales estén bien marcados, que la jerarquía tenga sentido, y evitar saltar niveles (ideal, no obligatorio).
- **Contraste de color (ratio de luminancia)** — algunas personas no pueden leer texto sin suficiente contraste contra el fondo. Mínimo: ratio de contraste de **4.5:1** para texto de tamaño normal. Tres formas de chequear: tabla de ratios de contraste (completa pero puede ser inexacta), herramienta cuentagotas/eyedropper (precisa pero de a un elemento por vez), o vista en escala de grises (da una experiencia directa pero imprecisa).
- **Redimensionar texto** — el contenido debe poder agrandarse sin que el texto desaparezca, se superponga, o se necesite scroll horizontal. Al aumentar el tamaño: todo el texto crece, y texto/imágenes/otro contenido no se superponen. Instrucciones disponibles para zoom de solo texto en Firefox, Safari e IE.

### Relacionados con interacción
- **Acceso por teclado y foco visual** — mucha gente no puede usar mouse y depende del teclado. Chequeos clave:
  - Todos los elementos son accesibles con la tecla Tab.
  - El foco es claramente visible.
  - El orden de tabulación sigue un orden de lectura lógico.
  - Es posible salir ("tab-out") de cualquier elemento — sin trampas de teclado.
  - Toda la funcionalidad está disponible por teclado.
  - El foco visual indica con claridad qué elemento está enfocado.
  - Problemas comunes: controles de reproductores multimedia inaccesibles, o funcionalidad disponible solo con hover de mouse.
- **Formularios, labels y errores**:
  - Todo control tiene un label asociado con el markup correcto.
  - Los labels están bien posicionados (a la izquierda de campos de texto, a la derecha de checkboxes).
  - Los campos obligatorios están claramente indicados sin depender solo del color.
  - Las instrucciones aparecen antes de que se necesiten.
  - Los mensajes de error son claros y específicos.
  - Los campos mantienen sus valores después de un error de envío.
  - Se puede chequear con IE WAT, WebDev, o inspeccionando el markup HTML.

### Generales
- **Contenido en movimiento, parpadeante o intermitente** — si arranca automáticamente y dura más de 5 segundos, necesita controles para pausar, detener u ocultar el movimiento. El contenido que parpadea no debe superar **3 veces por segundo**, por riesgo de crisis en personas con epilepsia fotosensitiva (conecta con la Pauta 2.3 de WCAG — ver [resumen del artículo de Pokémon](../articulos-externos/intermediate/pokemon-pauta-2-3-accesibilidad-summary.md)).
- **Alternativas multimedia**:
  - **Subtítulos (captions)** para video, que se puedan activar/desactivar.
  - **Transcripciones** con todo el diálogo, identificando quién habla y sonidos importantes.
  - **Audiodescripción** para información visual no accesible para personas ciegas.
  - **Acceso por teclado** a los controles del reproductor.
  - **Control de autoplay** — el audio no debería arrancar automáticamente, o debe tener pausa/control de volumen.
- **Chequeo de estructura básica** — examina la estructura de la página con imágenes deshabilitadas, estilos removidos, y contenido linealizado (una sola columna). Verifica que la información siga teniendo sentido en orden lineal y que los bloques de información tengan encabezados claros.

## Herramientas sugeridas

No hace falta herramientas especiales — la mayoría de los chequeos se pueden hacer con cualquier navegador. Como opcionales: **WebDev Toolbar** (Chrome, Opera, Firefox), **IE WAT** (IE9+), **WAVE**.

## Próximos pasos (según la guía)

1. Compartir los hallazgos con quienes puedan resolver las barreras encontradas.
2. Promover una evaluación de accesibilidad completa usando la metodología **WCAG-EM**.
3. Involucrar a personas con discapacidad reales en el testeo.

El propio W3C remarca: "se necesita una evaluación más robusta para evaluar la accesibilidad de forma integral" — esto es solo un primer filtro.

También menciona las páginas **BAD (Before and After Demonstration)** del W3C como ejemplos prácticos de versiones inaccesibles vs. accesibles, útiles para practicar.

## Relevancia para el knowledge base

- Es un checklist rápido y accionable para una primera pasada de accesibilidad — útil antes de una auditoría completa o como gut-check rápido sobre un diseño/flujo.
- Conecta con varios temas ya documentados acá: contraste (criterio 4.5:1), WCAG-EM como metodología de evaluación más profunda, y la pauta de destellos/epilepsia (Pauta 2.3).
- Recordar su límite explícito: pasar estos chequeos no significa que la página sea accesible — es un filtro preliminar, no una auditoría.
