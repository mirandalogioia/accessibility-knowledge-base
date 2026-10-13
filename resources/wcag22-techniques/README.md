---
title: "WCAG 2.2 Techniques — Índice"
status: in_progress
last_updated: 2026-10-13
---

# WCAG 2.2 — Techniques

Resumen traducido y estructurado de las páginas oficiales "Techniques" del W3C: ejemplos concretos (código + test) de cómo implementar los criterios de éxito de WCAG 2.2. Complementa a [`../wcag22-understanding/`](../wcag22-understanding/README.md), que explica el "qué" y el "por qué" de cada criterio — esta carpeta cubre el "cómo", con código real.

Fuente original: [w3.org/WAI/WCAG22/Techniques](https://www.w3.org/WAI/WCAG22/Techniques/). Importante: las técnicas son *ejemplos* de formas de cumplir WCAG, no son obligatorias — el contenido puede ser conforme sin usar exactamente estas técnicas.

## Alcance de este resumen

El catálogo completo de W3C tiene ~290 técnicas repartidas en 10 categorías de tecnología (incluyendo PDF, SMIL, Flash/Silverlight legacy, Server-Side Script, Plain-Text y ~113 "Common Failures"). Este resumen cubre únicamente las **4 categorías de desarrollo web moderno** más relevantes para proyectos actuales:

| Categoría | Archivo | Técnicas |
|---|---|---|
| ARIA | [01-aria.md](01-aria.md) | 26 |
| Client-Side Script (JavaScript) | [02-client-side-script.md](02-client-side-script.md) | 23 |
| CSS | [03-css.md](03-css.md) | 36 |
| HTML | [04-html.md](04-html.md) | 52 |
| **Total** | | **137** |

Quedan **fuera de este resumen** (no cubiertas): General Techniques (~190, muchas son conceptuales y ya están reflejadas en los "Cómo cumplirlo" de `wcag22-understanding/`), Common Failures (113, ejemplos de qué NO hacer), PDF (23), Server-Side Script (5), SMIL (8) y Plain-Text (3). Si hacés trabajo con PDFs o necesitás los "Failures" como checklist de antipatrones, se puede sumar una carpeta aparte.

## Formato por técnica

Cada técnica incluye: código (ej. `H37`), título, a qué criterio(s) de éxito se relaciona (y si es "Suficiente" o "Advisory"/consultiva), qué hace, un ejemplo de código y un resumen de cómo testearla.

## Notas de alcance

- Armado con fetches automatizados de las 137 páginas oficiales (sesión 2026-10-13), traducido y condensado — para el texto normativo completo, procedimientos de test detallados o ejemplos extendidos, remitirse a la fuente original del W3C.
- Los índices de categoría del sitio (`/Techniques/html/`, `/css/`, etc.) devuelven 403 al acceder directamente; el listado completo de códigos se extrajo de la página principal de Techniques.
