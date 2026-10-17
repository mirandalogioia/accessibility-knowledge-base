---
title: "Best practices for annotating"
source: "GitHub — annotation-toolkit (repo oficial)"
url: "https://github.com/github/annotation-toolkit/blob/main/deep-dives/best-practices-for-annotating.md"
date_saved: 2026-10-17
status: completo
---

# Best practices for annotating

## Qué es el annotation-toolkit

Es el kit de anotaciones de accesibilidad que usa GitHub en Figma para documentar, sobre el propio diseño, la información que necesitan los ingenieros para implementar accesibilidad: nombres accesibles, foco, orden de tabulación, roles, headings, etc. Se compone de "Stamps" (marcadores visuales sobre el diseño: pin, bracket, lasso) y "Details" (las instancias de texto en los márgenes que explican cada stamp). Este artículo es la guía de buenas prácticas para que esas anotaciones sean legibles y no saturen el archivo de diseño.

## Las 6 buenas prácticas

1. **Mantené legible el frame de diseño** — ubicar los stamps afuera del frame (pin/bracket/lasso apuntando al elemento), no encima. Menos solapamiento con el diseño real, más fácil de escanear para ingeniería.
2. **Separá tipos de anotación en frames duplicados** — en features grandes, duplicar la página/frame y poner solo 1-2 tipos de anotación por copia (ej. un frame solo con Focus Order) en vez de todo mezclado.
3. **Enlazá labels de Stamps con su Detail correspondiente (deep link)** — con `Cmd/Ctrl+L` copiás la URL de la instancia de Detail, y con `Cmd/Ctrl+K` creás un link desde el texto del Stamp hacia esa URL. Útil cuando el Stamp y su explicación están visualmente lejos.
4. **Anotá solo lo necesario** — elementos repetidos sin variación (ej. una fila de íconos de redes sociales todos iguales) no necesitan anotación individual; se anota el primero y se aclara que aplica al resto. Mismo criterio entre viewports si el tratamiento no cambia. Clave: comunicarle esta decisión a ingeniería para evitar confusión.
5. **Anotá componentes complejos por separado** — cuando hay mucha densidad y los stamps se superponen, conviene (a) separar el patrón complejo en su propio frame, o (b) usar la anotación utilitaria "Area out of scope" para tapar con un overlay las partes del diseño que no son relevantes y liberar espacio visual.
6. **Dividí componentes complejos en pantallas separadas** — para patrones anidados (ej. listas con ítems interactivos dentro de contenedores), conviene documentar por capas: el contenedor, la fila de acciones, la estructura de cada ítem, y el focus order completo, cada uno en su propio frame. Reduce el riesgo de que se pierda información crítica de accesibilidad (teclado, foco) en interfaces complejas.

## Relevancia para el knowledge base

- Es un ejemplo concreto de cómo un equipo de producto grande (GitHub) opera el hand-off de accesibilidad diseño→desarrollo: no alcanza con definir los criterios WCAG, hay que documentarlos de forma legible para que ingeniería los implemente bien.
- Conecta con el tipo de anotaciones que importan en una auditoría o implementación real: nombre accesible, focus order, roles de componentes, elementos fuera de alcance — vocabulario útil para armar criterios de revisión de diseño.
- El énfasis en "no sobrecargar visualmente" es un recordatorio aplicable más allá de Figma: la documentación de accesibilidad que nadie puede leer por exceso de ruido no cumple su función.

## Pendiente

- Si en algún momento se arma una guía propia de cómo anotar accesibilidad en Figma para el equipo, esta es una referencia directa a citar.
- Explorar el resto del repo `annotation-toolkit` (fuera de este deep-dive) por si hay más documentación relevante (ej. qué tipos de Stamps existen, cómo se instala el kit).
