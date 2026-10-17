---
title: "Sync Diseño <> QA sobre accesibilidad (Johana Rios)"
status: draft
source: "raw-inputs/sync-diseno-qa-joha-raw.txt"
last_updated: 2026-10-16
---

# Sync Diseño <> QA sobre accesibilidad

Primer acercamiento entre diseño (Teresita Ambrosio, Miranda Logioia) y QA (Johana Rios) para entender cómo QA trabaja hoy la accesibilidad en Dualboot y buscar puntos de alineación con la knowledge base e iniciativa de agente de accesibilidad que está armando diseño.

## Iniciativa de accesibilidad en diseño

- Miranda arrancó un curso de accesibilidad (weAAAre) y alimenta una knowledge base con el contenido.
- Diseño planea crear un agente que audite accesibilidad en diseños y prototipos; buscan complementar con el input de QA.
- Consenso explícito: la validación humana de un especialista sigue siendo clave aunque existan skills o agentes automáticos — un chequeo automático puede dar "aprobado" sin que el producto sea realmente usable (ver ejemplo Lighthouse/Crónica abajo).

## Cómo QA trabaja la accesibilidad hoy

- Hay cada vez más legislación y multas; los clientes suelen pedir accesibilidad por obligación legal, no por prioridad real.
- Cuando se pide, QA prioriza pero compite con problemas funcionales que llegan rotos — muchas veces no se llega ni al flujo completo de chequeo ni a la prueba manual.
- En el proyecto Dingo (cliente con requisito doble A): cada PRD pasa por "ticket review" (tool de sus agentes) que desglosa pruebas funcionales y corre un chequeo doble A vía MCP.
- Herramientas automáticas tienen un techo conocido: Lighthouse puede dar 90% de aprobación a algo cuya navegación por teclado no funciona (implementación visual vs. funcional). Ejemplo citado: el sitio de Crónica, donde el teclado navegaba pero el lector de pantalla anunciaba "link href" en vez del nombre accesible real.
- Recomendación de herramientas:
  - **Axe**: la mejor opción según QA; tiene plugin para design systems (configurable por nivel WCAG — A/AA/AAA) y plugin para código. Permite que diseño y QA usen la misma herramienta.
  - **Payly**: herramienta pública (repo en GitHub) integrada al repo de automation de QA — corre flujos como usuario final y valida nivel de accesibilidad de componentes/pantallas.
- Pese a tener las herramientas y los repos integrados, QA no está llegando hoy a correr el flujo completo de validación ni la prueba manual, por los problemas funcionales previos.

## Mobile

- No existe un equivalente rápido a Axe para mobile a nivel de producto (sí a nivel de código).
- El chequeo manual se hace activando la configuración nativa de accesibilidad del celular (screen reader de iOS/Android), lo cual reconfigura todo el dispositivo — proceso incómodo pero sin alternativa mejor hoy.
- Referencia externa: charla de **María Evangelina Ferreira (Eva)**, líder de producto en Mable, en la conferencia Quality Sense (Uruguay) — insistió en que los chequeos automáticos no reemplazan el ojo humano.

## Estado en proyectos reales

- La calidad de accesibilidad de los diseños depende hoy del diseñador; no hay herramienta ni estándar aplicado de forma consistente en el equipo.
- En **CRDN**: no se pidió accesibilidad explícitamente; se probó un agente de Figma para accesibilidad al testear dark mode en la versión web (restore net). Quedó en backlog — el stakeholder (Eric) quería ver un ejemplo antes de expandir a mobile. El diseño legacy de mobile (cautelo) fue descrito como "horrible", especialmente en dark mode.

## Traspaso de información diseño → QA (gap identificado)

- Hoy se pierde información: diseño arranca el proyecto y releva requisitos de accesibilidad y target audience, pero para cuando se suman PM/TL/QA/desarrollo esa información ya no se transmite bien.
- Propuesta de QA: que diseño documente desde el arranque del proyecto, por cliente/proyecto:
  - Requisitos de accesibilidad pedidos explícitamente por el cliente.
  - Target audience: devices, sistema operativo mínimo, browsers, tamaño de pantalla.
  - Contexto de uso más allá de disability (ej. un proyecto de laboratorio que se usa con guantes).
- Esto alimentaría el onboarding de QA a un proyecto y la estrategia de testing, sin depender de la comunicación humana informal que hoy se pierde.
- Acción concreta: revisar el template de user personas de la knowledge base para asegurar que contemple devices, SO mínimo y screen size.

## Decisiones tomadas

- **Estándar mínimo de accesibilidad para diseño y QA: doble A (WCAG)**, ajustable a triple A si el cliente lo pide explícitamente.

## Próximos pasos

- Johana pasa el contacto de Eva (María Evangelina Ferreira) y el repo público de Payly.
- Johana hace una encuesta al equipo de QA sobre la calidad de accesibilidad de los diseños que reciben.
- Miranda comparte la knowledge base de accesibilidad con QA.
- Teresita revisa el template de user personas de la knowledge base para incluir devices/OS/screen size.
- Interés compartido en una futura sesión para alinear procesos y patrones de diseño entre diseño y QA más allá de accesibilidad (ej. patrones de autenticación).

## Relevancia para `dualboot-findings/`

- Confirma gap real de proceso (traspaso diseño→QA) como candidato fuerte para la propuesta de checklist/proceso de accesibilidad.
- Valida el estándar doble A como piso a proponer formalmente.
- Axe + plugin de design system es la herramienta más viable para unificar diseño/QA/desarrollo bajo un mismo criterio.
- El caso Lighthouse/Crónica es un buen ejemplo concreto para justificar por qué el chequeo automático no puede ser la única validación.
