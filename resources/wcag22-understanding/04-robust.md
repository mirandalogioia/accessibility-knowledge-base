---
title: "WCAG 2.2 Understanding — Principio 4: Robusto (Robust)"
status: in_progress
last_updated: 2026-10-13
---

# 4. Robusto (Robust)

> El contenido debe ser suficientemente robusto como para ser interpretado de forma fiable por una amplia variedad de agentes de usuario, incluyendo las tecnologías de asistencia.

Fuente: [W3C WAI — Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/)

## 4.1 Compatible

### 4.1.1 Procesamiento (Obsoleto / retirado en WCAG 2.2)
**Qué pide:** Este criterio fue declarado obsoleto y retirado en WCAG 2.2. Originalmente (Nivel A) exigía que el contenido pudiera analizarse de forma inequívoca mediante las reglas de su gramática formal: elementos con etiquetas de apertura y cierre completas, anidamiento correcto según la especificación, atributos sin duplicar e identificadores (ID) únicos. Se retira porque las tecnologías de asistencia modernas ya no dependen de analizar directamente el HTML: delegan en el navegador, y tanto los navegadores como las especificaciones han mejorado enormemente su manejo de errores de marcado, haciendo innecesaria esta validación estricta como criterio de accesibilidad independiente.
**Por qué importa (histórico):** Garantizar etiquetas completas y anidamiento adecuado ayudaba a que las tecnologías de asistencia analizaran el contenido sin fallos, y permitía que distintos navegadores procesaran el contenido de forma confiable y consistente.
**Cómo cumplirlo (histórico):**
- Verificar que no existan atributos duplicados.
- Asegurar que los identificadores (ID) sean únicos en el documento.
- Completar correctamente las etiquetas de apertura y cierre, respetando el anidamiento según la especificación del lenguaje de marcado.
**Ejemplos/notas:** Al estar retirado, no se evalúa en auditorías actuales de WCAG 2.2; se mantiene documentado por motivos históricos y de trazabilidad entre versiones.

### 4.1.2 Nombre, rol, valor (Nivel A)
**Qué pide:** Que para todos los componentes de interfaz de usuario (incluidos los personalizados), se pueda determinar mediante software su nombre y rol; que los estados, propiedades y valores que puedan establecerse por el usuario también puedan determinarse por software; y que se notifique a los agentes de usuario, incluidas las tecnologías de asistencia, cualquier cambio en estos elementos.
**Por qué importa:** Permite que las tecnologías de asistencia (lectores de pantalla, magnificadores, software de reconocimiento de voz) obtengan información adecuada sobre los controles, los activen y mantengan actualizado su estado. Beneficia especialmente a personas con discapacidades visuales, motrices y cognitivas que dependen de estas tecnologías.
**Cómo cumplirlo:**
- Para componentes estándar de HTML: usarlos conforme a la especificación, con elementos `<label>` asociados y atributos `title` cuando sea necesario.
- Para componentes personalizados (widgets): exponer nombre accesible mediante `aria-labelledby` o similar, asignar roles ARIA apropiados, y exponer estados y propiedades (`aria-*`) actualizados.
**Ejemplos/notas:** Una página que usa widgets personalizados —como botones de alternancia, comboboxes o widgets de divulgación (disclosure)— implementados con una combinación de HTML y ARIA, para que transmitan programáticamente su nombre accesible, su rol, y su estado y valor actuales.

### 4.1.3 Mensajes de estado (Nivel AA)
**Qué pide:** Que los mensajes de estado (confirmaciones, resultados de búsqueda, progreso, errores) puedan ser determinados por tecnologías de asistencia mediante un rol u otra técnica apropiada, sin necesidad de que reciban el foco, y sin interrumpir innecesariamente el trabajo del usuario.
**Por qué importa:** Informa a personas ciegas y con baja visión que usan lectores de pantalla sobre cambios dinámicos en la página sin interrumpir su flujo de trabajo; también beneficia a personas con discapacidades cognitivas al permitirles personalizar cómo reciben estas notificaciones (retrasarlas, suprimirlas o transformarlas).
**Cómo cumplirlo:**
- Para mensajes de éxito o estado general: usar `role="status"`.
- Para alertas y errores: usar `role="alert"` o regiones vivas (live regions).
- Para indicadores de progreso: aplicar `role="log"` o regiones `aria-live`.
**Ejemplos/notas:** Mensajes como "5 resultados encontrados" tras una búsqueda, "Cinco artículos" en un carrito de compras, "Entrada inválida" en validación de formularios, barras de progreso con anuncios intermitentes, o "Su formulario fue enviado correctamente" como confirmación final.
