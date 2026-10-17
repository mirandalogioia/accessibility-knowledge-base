---
title: "Cómo pokemón ayudó a crear una pauta de accesibilidad"
source: "Medium — Pipi Marquez"
url: "pendiente (completar con el link del artículo)"
date_published: 2023-02-13
date_saved: 2026-10-10
status: completo
---

# Cómo pokemón ayudó a crear una pauta de accesibilidad

## El incidente

En 1997, el episodio 38 de Pokémon emitido en Japón ("Soldado eléctrico Porygon") mostró una explosión animada con destellos de luz azul/rojo en 54 planos durante 5 segundos. Provocó la hospitalización de más de 700 personas, en su mayoría niños.

## Epilepsia fotosensitiva vs. otras epilepsias

- La **epilepsia fotosensitiva** es un tipo de epilepsia donde las crisis son provocadas por estímulos visuales (luces intermitentes, cambios de contraste). Afecta a 3 de cada 100 personas con epilepsia — es decir, es una forma minoritaria dentro de la condición.
- Los estímulos visuales pueden desencadenar una crisis incluso en personas sin diagnóstico previo, especialmente si están estresadas, cansadas o deshidratadas.
- Muchas personas no saben que tienen este tipo de epilepsia hasta que se exponen a una secuencia de luces que la dispara (testimonios citados: una película 3D, un videojuego de celular, Fortnite en consola).
- Dato clave (Ivana García, Espacio Epilepsia): 1 de cada 100 personas es diagnosticada con epilepsia en algún momento de su vida — cualquiera puede tener una crisis epiléptica, esté o no diagnosticado.

## El impacto en los estándares

El incidente de Pokémon no llevó directamente a una mejora de buena fe en el programa, sino que impulsó regulaciones de televisión que, años después, el W3C tomó como referencia al crear su propia pauta de accesibilidad web.

**Pauta 2.3 (WCAG 2.0) — Convulsiones y reacciones físicas:**
> No diseñar contenido de un modo que se sepa podría provocar ataques, espasmos o convulsiones.

La pauta oficial incluye una explicación que hace referencia al incidente (sin nombrar a Pokémon directamente):
> "En 1997, una caricatura en la televisión de Japón envió a casi 700 niños al hospital, incluyendo alrededor de 500 de ellos con este tipo de ataques. Las advertencias no son efectivas pues muchas veces son ignoradas, especialmente por niños que quizás no puedan leerlas."

El objetivo es evitar destellos que puedan generar una crisis incluso si el contenido se ve solo 1-2 segundos — las advertencias previas no alcanzan como mitigación porque mucha gente (ej. niños) no las entiende o no llega a leerlas a tiempo.

**Criterios técnicos asociados a la Pauta 2.3:**
- **2.3.1 Umbral de tres destellos o menos** — nivel A
- **2.3.2 Tres destellos** — nivel AAA

(La autora anuncia un próximo post profundizando en el criterio 2.3.1 y cómo diseñar para no causar crisis epilépticas — no está en este repo todavía.)

## Terminología correcta

El artículo hace una aclaración importante sobre lenguaje: el término **"ataque"** (como aparece en la traducción oficial de la pauta, "podría provocar ataques, espasmos o convulsiones") **no es el término que usa la comunidad con epilepsia**. Lo correcto es decir **"crisis"**, no "ataque" — la traducción oficial está desactualizada. Esto refuerza que las traducciones de estándares deben revisarse con las comunidades a las que afectan.

## Relevancia para accesibilidad web

- Conecta un criterio de éxito de WCAG (2.3, convulsiones y reacciones físicas) con su origen histórico real — útil como ejemplo concreto al explicar por qué existe esa pauta.
- Recordatorio práctico: contenido con parpadeos/destellos de alto contraste (animaciones, transiciones, video autoplay) es un riesgo real de accesibilidad, no solo una preocupación teórica.
- Al hablar o escribir sobre epilepsia, usar "crisis" en vez de "ataque".
- Los criterios técnicos concretos (2.3.1 nivel A, 2.3.2 nivel AAA) son el próximo nivel de detalle a investigar si se quiere auditar contenido animado/con destellos.

## Pendiente

- Buscar el próximo post de la autora sobre el criterio 2.3.1 cuando esté disponible.
- Agregar el link original del artículo a `resources/links.md` si se decide usar como referencia citable.
