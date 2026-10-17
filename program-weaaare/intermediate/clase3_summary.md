---
title: "Clase 3 — Tutoría: flujos de proyecto, teclado, encabezados y Kahoot WCAG"
status: in_progress
source: ../raw-inputs/clase3_raw.txt
last_updated: 2026-10-17
---

# Clase 3 — Tutoría de Diseño Accesible (weAAAre)

Tutoría de revisión: se repasaron los entregables de los módulos 1 y 2, se ajustó el alcance de tres proyectos de alumnas (OC, agencia de viajes, salud de Galicia), se explicó navegación por teclado y encabezados, y se cerró con un Kahoot sobre WCAG.

## Entregables de los módulos 1 y 2

- **Módulo 1 (brief):** define producto, necesidad, flujo y contexto. Incluir nombre de alumna y de proyecto.
- **Módulo 2 (matriz de requisitos):** barreras → a quién afectan → criterios WCAG → requisitos → decisiones de diseño. Se copia al Figma propio.
  - Ejemplo de formulario: cada campo con etiqueta, estados (inválido) y mensaje que explique cómo recuperarse del error.
  - Es un ejercicio de mapeo conceptual: del módulo 3 en adelante el trabajo es el proyecto en sí.
- **Proyecto:** documentar en detalle **2 componentes simples + 1 complejo**, más colores y tipografía (mini sistema de diseño / muestrario).
  - Simples: enlace, botón, checkbox, radio button (con etiqueta).
  - Complejos: tabla, card, acordeón, tabs, calendario, formulario.
  - Modal: queda entre simple y complejo.
- **Alcance:** ideal **no más de 4 pantallas**; hacer microflujos y **bocetar a mano primero**. Se asume que lo diseñado funciona (no hay research con usuarias). Documentar para un solo dispositivo (ej. date picker).
- Se diseña la UI de todas las pantallas del flujo, pero solo se documenta a fondo lo anterior.

## Criterios y buenas prácticas mencionados

| Tema | Idea clave |
|---|---|
| Contraste | 4.5:1 texto normal, 3:1 texto grande. Excepciones: elementos inhabilitados y logotipos |
| Estado de botones | Un botón inactivo pero cliqueable que parece deshabilitado comunica mal el estado |
| Tamaño interactivo | Mínimo 24×24 (AA); 44×44 es AAA |
| Múltiples vías | Menú, buscador, mapa del sitio, accesos directos |
| Ubicación | Menú con ítem activo marcado, título de página, breadcrumb |
| Patrones de diseño | Menú arriba, buscador, footer: usar patrones conocidos evita tener que "aprender" el sitio |
| Mapa del sitio / IA | Ayuda a indexar; la IA lee el árbol de accesibilidad |
| Simplificar | Mejor un paso más pero inequívoco que ahorrar un clic y generar confusión |

## Casos revisados

### OC (pago de agua, Uruguay)
- Textos como imágenes, captcha sin alternativa auditiva, botones sin jerarquía primaria/secundaria, sin menú ni footer.
- Número de cuenta mostrado como imagen → alternativa: pedir **DNI** (referencia: Enel).
- **Alcance acordado:** desde la tercera pantalla hasta la selección de método de pago (la pasarela es otro flujo). Agregar menú y footer.
- Tiene tabla (componente complejo) y formularios.

### Agencia de viajes (Austria)
- Flujo: encontrar la experiencia más barata para 3 personas; la reserva puede ser otro flujo.
- Se puede rediseñar la estructura completa. Candidatos a documentar: **calendario** (complejo), **tabs** (complejo), buscador y botón (simples).
- **Tabs:** son un grupo; se entra con Tab y se mueve entre pestañas con flechas. Hay que documentarlo porque el comportamiento de teclado es inesperado.

### Ficha de viaje (Paula)
- Precio orientativo, galería, itinerario en acordeón; modal de configuración con input con sugerencias, calendario y stepper. Alcance válido: todo va en la UI, solo se documentan 3 componentes.
- Tabs y acordeones son complejos porque HTML no tiene elemento nativo (a diferencia de `table`) → se usa **ARIA**.

### Sistema de salud de Galicia (Clara)
- Problemas: tarjetas de login que no se anuncian como botones, dos accesos simultáneos confusos, modales innecesarios, calendario que deshabilita días sin avisar, foco y lector de pantalla fallan, footer leído primero.
- **Alcance acordado:** desde "consulta" hasta la pantalla de confirmar cita.
- Mejora de UX: mostrar primero las **próximas horas disponibles** antes del calendario.
- Principio: **no trasladar al mundo digital los errores del mundo físico**; accesible ≠ buena experiencia.
- Login y registro podrían ser un flujo aparte.

## Navegación por teclado

- **Tab** avanza y **Shift+Tab** retrocede, solo por elementos interactivos (no títulos, párrafos ni imágenes).
- Orden esperado: banner de cookies (si existe) → enlace "Saltar al contenido" (normalmente oculto) → resto.
- Enter/Espacio activan; grupos con chevron se abren así. Dentro de un grupo (tabs) se navega con flechas.
- Demo con W3C como ejemplo de buen sitio.
- Se diseña para todas las personas, aunque se documente también lector de pantalla.
- Documentar dos niveles: **interfaz** y **componente / sistema de diseño**.

### Modales (reglas)
1. No se disparan solas.
2. Atrapan el foco.
3. Más de una forma de cerrar (botón, X, clic fuera).
4. Título como **H1** (nuevo contexto).

## Encabezados y estructura (demo con WAVE)

- **Un solo H1** por página = título de la página (no un banner promocional).
- H2 = secciones, H3 = subsecciones, secuencial hasta H6 (rara vez se llega).
- Landmarks: header, navigation, main, aside (contenido complementario, no solo barra lateral), footer.
- Listas dentro de navegación: el lector anuncia cuántos elementos tiene.
- El lector de pantalla anuncia rol y estado (botón, contraído/expandido), de ahí la necesidad de documentar ARIA.

## Estándares

| Sigla | Qué es |
|---|---|
| WCAG | Contenido web (4 principios POUR, 13 pautas, criterios A/AA/AAA) |
| ATAG | Herramientas de autoría (tipo Canva, WordPress, Photoshop); dos partes: plataforma accesible + contenido creado accesible |
| UAAG | Agentes de usuario (navegadores) |
| COGA | Accesibilidad cognitiva |
| WCAG-EM | Método para definir la muestra de páginas al evaluar conformidad |
| VPAT / ACR | VPAT es la plantilla voluntaria; completada, es el ACR (Accessibility Conformance Report) |

- Los estándares "AG" = Accessibility Guidelines.
- Apps de escritorio tipo Canva: aplican WCAG + ATAG.
- WCAG 2.2 contiene 2.1 que contiene 2.0 ("muñecas rusas"); 3.0 está en borrador. Los criterios nuevos se agregan al final de su pauta para no renumerar.

## Kahoot: ideas confirmadas

- Jerarquía WCAG: principios → pautas → criterios de éxito → niveles (A, AA, AAA).
- Criterios definen condiciones evaluables (el qué, no el cómo); las técnicas no son la única forma de cumplir.
- Herramientas automáticas cubren ~30% (medido sobre criterios, pero depende de las pruebas); hay que combinar con tecnología de apoyo y personas con discapacidad.
- Accesible ≠ 100% usable; los tests de usabilidad siguen siendo necesarios.
- Cumplir WCAG no garantiza que todas las personas puedan usar toda interfaz.
- Considerar accesibilidad desde las primeras decisiones y **documentar decisiones** (estados, comportamiento de teclado, interacción).
- Declarar conformidad requiere definir estándar, nivel (ej. WCAG 2.2 AA) y muestra; no basta la home ni un escáner.
- HTML y WCAG no son lo mismo, pero HTML semántico evita muchos problemas; cuando HTML no alcanza, se usa ARIA.
- Una buena especificación de componente incluye propósito/comportamiento, interacción, teclado, estados y cambios de estado.

## Logística del curso

- Módulo 3 se libera al día siguiente (retraso por enfermedad de Carlos); dos contenidos llegan el sábado. Foco del módulo: foco, teclado, herramientas de contraste (auditoría y diseño) y plugins.
- Cuando se agrega contenido a un módulo ya liberado, se envía un correo.

## Próximos pasos

- Speaker 1: compartir enlaces de ATAG, UAAG y WCAG-EM (posible recurso del curso); grabar y subir los 2 contenidos pendientes del módulo 3.
- Speaker 2: ajustar el flujo de OC (tercera pantalla → método de pago).
- Clara: acotar el flujo de cita médica (consulta → confirmación).
- Carlos: liberar el módulo 3.
- Alumnas: completar la matriz, definir pantallas a diseñar y bocetar a mano para la próxima semana.

## Pendientes / dudas para mí

- Confirmar nombres reales de los speakers (el transcript solo los etiqueta).
- Varias siglas del audio están transcritas con errores (WCAG aparece como "Wicar", ATAG como "ATAC", UAAG como "UAC", VPAT como "BIPAC"); este summary usa las siglas correctas.
