---
title: "Clase 1 — Kickoff del Programa Intensivo de Diseño Accesible (weAAAre)"
status: draft
source: "raw-inputs/clase-01-raw.txt"
last_updated: 2026-09-30
---

# Clase 1 — Kickoff

Primera clase en vivo del programa intensivo "Diseño Accesible" de weAAAre (primera edición). Sesión de presentación: metodología del curso, temario de los 10 módulos, mecánica del proyecto final, certificación, herramientas necesarias y dinámica de bienvenida (formulario + Kahoot).

## Quiénes dan el curso

- **Carlos Garrido Marín** — fundador de WIAR/weAAAre. Perfil de desarrollo, conecta diseño con desarrollo y acelera el trabajo con IA. Lidera los módulos de forma de interacción, laberinto de componentes, sistema de diseño accesible e IA (módulos 7-9).
- **Consuelo Correa Barros** — diseñadora UX, cofundadora de una consultora de accesibilidad digital, ha trabajado con BID, CAF, ONU y gobiernos. Lidera diseño para la diversidad, WCAG para diseñadores, diseño visual accesible, y el módulo final de negocio/priorización (módulo 10).
- Apoyo también de **Estibaliz Martin Borja**.

## Metodología del programa

- Dos tipos de lecciones: **grabadas** (a tu ritmo) y **tutorías en directo** (semanales, tipo clase en vivo).
- Cada miércoles se desbloquea un módulo completo grabado; la tutoría en vivo de esa semana repasa el módulo anterior y resuelve dudas.
- Dudas fuera de horario de clase: Discord y comentarios en las lecciones (respuesta asíncrona).
- Asistencia a las clases en vivo **no es obligatoria** para el certificado; todas quedan grabadas (disponibles ~2h después).
- **Acceso de por vida** al contenido, incluyendo futuras actualizaciones del temario (ej. si WCAG pasa de 2.2 a una nueva versión, se notifica y se actualiza sin costo).
- Primera edición → los tiempos de algunos módulos pueden no estar bien calibrados; el equipo pedirá feedback en vivo para decidir si se retrasa el ritmo.

## Temario: 10 módulos / 10 semanas

1. **Diseñar para la diversidad** — cómo navegan y usan tecnología las personas, base de accesibilidad (asumiendo poco conocimiento previo).
2. **WCAG para diseñadores** — cómo leer la documentación de WCAG, ejemplos y recursos.
3. **Diseño visual accesible** — color, tipografía, grillas responsivas.
4. **Forma de interacción** — cómo interactúan distintos usuarios (teclado, lectores de pantalla, pulsadores, etc.), uso real de tecnología asistida.
5. **Laberinto de componentes** — anatomía de interacción por tipología de componente (checkboxes, radios, botones, enlaces) hasta casos complejos (formularios multi-paso, modales, carruseles con autoplay/loop).
6. **Sistema de diseño accesible** — el módulo más denso: color/contraste, tipografía, estados, variantes, composición, patrones, documentación, requisitos para desarrollo/QA, gobernanza. Se trabaja fuerte con Figma. La documentación luego pasa por un proceso de iteración vía IA.
7. **IA — fundamentos** (nivel principiante) — cómo montar un entorno con agentes de IA desde cero, sin asumir base técnica. Casi no toca accesibilidad directamente; es la base técnica para los módulos 8-9. Requiere licencia de pago de un asistente de IA (Claude o GPT/Codex), a partir de este módulo.
8. **IA — caso de uso** (nivel medio) — llevar el sistema de diseño de Figma a un Storybook/playground interactivo real, con tests y evaluaciones deterministas de accesibilidad.
9. **IA — evolución del entorno agéntico** (nivel avanzado) — cómo evaluar y evolucionar el entorno agéntico construido; extrapolable a otros casos de uso (ej. un auditor de accesibilidad propio).
10. **Negocio y priorización** (Consuelo) — cómo priorizar problemas quiendo se interviene un producto ya existente, cómo documentar para equipos interdisciplinarios/stakeholders, y cómo argumentar accesibilidad con lenguaje de negocio en vez de derechos humanos/criterios técnicos. Contenido inédito, nunca antes dado en otros cursos de weAAAre.

## Herramientas necesarias

| Herramienta | Cuándo | Costo |
|---|---|---|
| Figma | desde el módulo 6 | Gratis (plan Draft alcanza) |
| Lector de pantalla (NVDA en Windows / VoiceOver en Mac) | a lo largo del curso | Gratis |
| Cuenta de GitHub | para repositorio de código y despliegue | Gratis |
| Asistente de IA (Claude o GPT/Codex) | a partir del módulo 7 | Pago (~20 USD/mes aprox.) |

## Proyecto final

- Dos caminos posibles:
  1. **Remediar**: elegir un sitio/app existente con problemas de accesibilidad, detectar barreras en un flujo y proponer solución.
  2. **Diseñar desde cero**: un flujo nuevo (propio o de un proyecto real) diseñado accesible desde el inicio.
- Se trabaja sobre un **flujo** (ej. login → perfil, compra, reserva), no una pantalla suelta.
- Se deben diseñar: las pantallas del flujo, **2 componentes simples** (botón, checkbox, link) y **1 componente complejo** (acordeón, carrusel, tabs — porque implican configuración/documentación específica para lector de pantalla). Un breadcrumb sería un ejemplo de complejidad intermedia.
- Debe incluir documentación completa: tokens (tipografía, color desde el módulo 1), especificaciones de accesibilidad (comportamiento con teclado, lector de pantalla), y **handoff** a desarrollo cubriendo al menos: estado semántico, orden de teclado, orden de lectura, texto alternativo en imágenes, idioma, título de página, e interacciones ARIA necesarias.
- El flujo final debe ser interactivo (prototipo funcional) y se lleva a código real: Storybook/playground desplegado con URL pública, usando el entorno de IA construido en los módulos 7-9.
- Se avanza semana a semana; al final de cada módulo habrá una lección con el detalle de qué construir esa semana.
- **Entrega: 9 de diciembre de 2026** (día antes de la última clase en vivo). Habrá feedback iterativo durante el proceso, no solo al final.
- El mejor proyecto gana un **reembolso completo** del programa.

## Certificación (independiente del proyecto)

- Exámenes asíncronos cortos al final de cada módulo (repetibles).
- 70% del total de exámenes aprobado → certificado estándar.
- Máxima puntuación en los exámenes → "certificado aventajado" (alumno destacado).
- El certificado no depende de asistir a clases en vivo ni del proyecto — son dos pistas separadas.

## Comunicación: Discord

- Toda la comunicación pasa por la comunidad de Discord de weAAAre (requiere cuenta verificada por correo — causa común de no poder unirse).
- Canal exclusivo y permanente para este programa intensivo ("Diseño Accesible, septiembre").
- Resto de canales (foros, networking, presentaciones, salas de voz) accesibles según suscripción a WIAR.
- Problemas de acceso → escribir a soporte@wiar.com.

## Contenido adicional recomendado (opcional, no obligatorio)

Cursos cortos (≈1h) recomendados para reforzar el módulo 1, parte del temario de certificación de profesionales de accesibilidad:
- Modelos teóricos de la discapacidad (modelo de rehabilitación vs. modelo social, etc.)
- Discapacidad, etiquetas, barreras y estadísticas
- Discapacidad y tecnología asistida
- Diseño universal

## Datos y conceptos técnicos mencionados (via dinámica Kahoot)

- Según la OMS, **1 de cada 6 personas** vive con una discapacidad significativa (~1.300 millones; cifra subestimada porque no todos los países contabilizan igual). La cifra crece por el envejecimiento poblacional.
- **Efecto bordillo** ("curb-cut effect"): una adaptación pensada para sillas de ruedas (rebaje de vereda) termina beneficiando a mucha más gente.
- Reporte anual **WebAIM Million** (auditoría automática de 1M de páginas de inicio): el fallo más común sigue siendo **bajo contraste** (por encima de imágenes sin alt o campos sin etiqueta). Solo ~4% de los sitios auditados son realmente accesibles, y el porcentaje con al menos un fallo **ha empeorado** año a año — se debate que la generación de sitios con IA sin criterios de accesibilidad agrava el problema.
- La accesibilidad también impacta el posicionamiento en IA generativa (GEO): los modelos usan el árbol de accesibilidad para "leer" un sitio; si no es accesible, no aparece bien representado en respuestas de IA.
- **Texto alternativo (alt text)**: debe describir la información que la imagen aporta y que no está en el texto (ejemplo W3C del perro guía con cascabel: lo relevante es *dónde* está el cascabel, no que "tiene cascabel"). Para grupos de imágenes repetidas (ej. estrellas de valoración), se pone el alt completo en la primera y se marcan las demás como decorativas (alt vacío) — mejor aún, usar principio de equivalencia y mostrar el valor en texto visible (ej. "3.5 de 5") para todos los usuarios, no solo lectores de pantalla.
- Gráficos con datos únicos: alt breve + descripción larga con el detalle de los datos (eje X/Y, valores).
- Criterio WCAG **"Foco no oculto"**: si un elemento recibe foco de teclado, debe verse visualmente dónde está.
- Tamaño mínimo de objetivo de puntero en **WCAG 2.2 nivel AA es 24×24 px** (no 44×44, que es una buena práctica de mobile, ni 48×48; en AAA sí se exige más).
- Reordenar por arrastre debe tener alternativa por teclado para quien no usa mouse/dedo (ej. punteros de cabeza o boca).
- Criterio **"Autenticación accesible"** (WCAG 3.3.8/3.3.9): debe existir alternativa a la autenticación biométrica (Face ID, huella), que puede fallar con personas ciegas o con cambios físicos.
- Gestión de foco al cerrar modales/diálogos: el foco debe volver al elemento que originó la apertura (o al punto más cercano si ese elemento ya no existe, p. ej. tras eliminar algo).
- Patrón de navegación por **pestañas (tabs)**: dentro del grupo, se navega con flechas, no con Tab (Tab entra y sale del grupo).
- Cálculo del **nombre accesible**: el `aria-label` tiene prioridad sobre el texto visible/label asociado por `for`/`id`. "aria-label mata HTML" (mnemónico compartido en la clase, parafraseando "billetera mata galán").
- `role="presentation"` en un enlace no elimina su semántica real (mala práctica, pero el navegador ignora el rol y mantiene el comportamiento de enlace).
- Cambios de estado sin cambio de contexto (ej. toast "cambio guardado", contador de carrito): deben anunciarse mediante regiones live / mensajes de estado programáticos, no solo visualmente.
- Al pedirle un diseño/interacción a una IA, cuanto más específica la instrucción (ej. "foco entra al abrir, Escape cierra, foco vuelve al activador"), mejor y más determinista el resultado — no dejarle todo el criterio a la IA.

## Próximos pasos

- Módulo 1 se desbloquea el mismo día a las 23:00h España.
- Primera tutoría en vivo: miércoles siguiente, misma hora — se explicará en detalle la definición del proyecto.
- Recomendado ir pensando qué camino de proyecto elegir (remediar vs. diseñar desde cero).
- Masterclass en vivo al día siguiente sobre documentos accesibles (PDF/Word accesibles).
