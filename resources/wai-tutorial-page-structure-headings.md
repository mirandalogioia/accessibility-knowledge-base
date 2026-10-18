---
title: "WAI Tutorial — Encabezados (estructura de página)"
status: in_progress
last_updated: 2026-10-18
---

# Encabezados (W3C WAI)

Resumen traducido del tutorial ["Headings"](https://www.w3.org/WAI/tutorials/page-structure/headings/) de W3C WAI, parte del módulo "Page Structure Tutorial". Actualizado el 4 de mayo de 2017 (editores: Eric Eggert, Shadi Abou-Zahra; desarrollado por el Education and Outreach Working Group — EOWG).

Se incluye en este repo porque el Módulo 3 del programa weAAAre (lección 3.7, jerarquía visual y semántica) lo referencia como guía para usar los niveles de encabezado y comunicar la organización de una página.

## Idea general

Los encabezados muestran cómo está organizado el contenido de una página. Navegadores, extensiones y tecnologías de apoyo los usan para la **navegación dentro de la página** (p. ej. la lista de encabezados de un lector de pantalla).

## Niveles (ranks)

- Los encabezados se anidan por nivel: `<h1>` es el más importante y `<h6>` el menos.
- Un encabezado de **igual o mayor nivel** abre una **sección nueva**; uno de **menor nivel** abre una **subsección** de la sección anterior.
- **Evitar saltarse niveles**: un `<h2>` no debería ir directamente seguido de un `<h4>`.
- Sí es aceptable "saltar" hacia arriba al cerrar subsecciones: un `<h2>` que abre una sección nueva puede seguir a un `<h4>`.
- **Excepción para áreas fijas** (barras laterales, etc.): el nivel de sus encabezados no debería variar según el contenido principal; importa más la coherencia entre páginas.

## Usos

- **Organizar pasajes de texto**: los encabezados pueden estructurar el contenido principal sin etiquetar regiones grandes de la página.
- **Reflejar la organización de la página**: pueden rotular regiones (el tutorial remite al de "Labeling Regions" para asociar un encabezado a su región con `aria-labelledby`). Los encabezados visibles facilitan identificar regiones a todas las personas.
- **Ubicación del encabezado principal (h1)**:
  - puede ir **antes de la navegación** (p. ej. si es el nombre del sitio);
  - o **después**, cuando el encabezado del contenido principal es el más importante; en ese caso, la navegación y los encabezados estructurales son nivel 2.

## Ejemplos del tutorial (sin código en la página)

1. **Organizar pasajes de texto**: un `<h1>` («Space Teddy») con tres `<h2>` en el contenido («Cotton Fur», «Sapphire Eyes», «Synthetic Felt Paws»).
2. **Encabezado principal antes de la navegación**: el primer encabezado es `<h1>`; «Navigation Menu», «Sidebar», «Footer» y el encabezado del contenido principal son `<h2>`. La subsección «Sapphire Eyes» es `<h3>` con una subsección `<h4>` («How they are made»); el siguiente `<h2>` cierra ambas.
3. **Encabezado principal después de la navegación**: la página empieza con `<h2>` «Navigation Menu» y `<h2>` «Sidebar»; el encabezado del contenido principal («Space Teddy») es `<h1>`; los siguientes son `<h2>`, incluido el footer.

## Criterios y técnicas relacionados (según el propio tutorial)

**Criterios de éxito**: 1.3.1 Información y relaciones (A), 2.4.1 Evitar bloques (A), 2.4.6 Encabezados y etiquetas (AA), 2.4.10 Encabezados de sección (AAA). Resúmenes en [`wcag22-understanding/`](wcag22-understanding/README.md).

**Técnicas**: ARIA12 (usar `role=heading`), G130 (encabezados descriptivos), G141 (organizar una página con encabezados), H42 (usar h1–h6), H69 (elementos de encabezado al inicio de cada sección), H80 (propósito del enlace con el texto del enlace + el encabezado anterior), PDF9 (encabezados en PDF). Ver [`wcag22-techniques/`](wcag22-techniques/README.md).

## Qué NO cubre este tutorial

No trata la elección del nivel según tamaño o aspecto visual, el uso de CSS para el aspecto, encabezados ocultos, título de página vs. `<h1>`, ni encabezados dentro de widgets. La relación **nivel ≠ tamaño** (diseñar estilos con nombres neutros, p. ej. «Título L/S», y anotar «h1 · Título S») es contenido de la lección 3.7 del programa, no de este tutorial.
