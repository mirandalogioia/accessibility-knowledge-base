---
title: "ARIA APG — Patrón de pestañas (Tabs)"
status: in_progress
last_updated: 2026-10-18
---

# Patrón de pestañas (W3C WAI-ARIA Authoring Practices Guide)

Resumen traducido del patrón [Tabs](https://www.w3.org/WAI/ARIA/apg/patterns/tabs/) de la APG del W3C. Se incluye en este repo porque el Módulo 3 del programa weAAAre lo referencia al explicar que, en un grupo de pestañas, **foco y selección pueden separarse** (una pestaña identifica el panel abierto; otra puede recibir el foco antes de activarse con Intro o Espacio).

## Qué es

Secciones de contenido en capas (paneles) que muestran un panel a la vez. Cada panel tiene una pestaña asociada que, al activarse, lo muestra. Al iniciar, un panel está visible y su pestaña aparece como activa.

## Términos

- **Tabs / interfaz con pestañas:** el widget completo (pestañas y paneles).
- **Tab list:** el conjunto de pestañas, dentro de un elemento `tablist`.
- **Tab (`tab`):** elemento de la lista que rotula un panel y puede activarse para mostrarlo.
- **Tab panel (`tabpanel`):** el elemento con el contenido asociado a una pestaña.

## Variantes de activación

- **Activación automática:** la pestaña se activa y muestra su panel apenas recibe el foco.
- **Activación manual:** la persona mueve el foco entre pestañas y pulsa Espacio o Intro para mostrar el panel.
- **Recomendación de la APG:** usar activación automática cuando los paneles aparecen sin latencia perceptible (normalmente precargando el contenido). Si no, ralentiza el movimiento del foco y dificulta la navegación eficiente.

## Interacción con teclado

| Tecla | Comportamiento |
|---|---|
| **Tab** | Al entrar en la lista, el foco va a la pestaña activa. Estando en la lista, Tab lleva el foco al siguiente elemento de la secuencia fuera de la lista (normalmente el tabpanel, salvo que el primer contenido significativo del panel sea enfocable). |
| **Flecha izquierda / derecha** (lista horizontal) | Mueve el foco a la pestaña anterior / siguiente; de la primera salta a la última y viceversa. Opcionalmente activa la pestaña enfocada. |
| **Flecha arriba / abajo** (lista vertical) | Arriba actúa como izquierda y abajo como derecha. En una lista horizontal estas teclas no se escuchan, para conservar el scroll de la página. |
| **Espacio o Intro** | Activa la pestaña enfocada si no se activó al recibir el foco. |
| **Home** (opcional) | Foco a la primera pestaña; opcionalmente la activa. |
| **End** (opcional) | Foco a la última pestaña; opcionalmente la activa. |
| **Mayús + F10** | Si la pestaña tiene menú emergente asociado, lo abre. |
| **Suprimir** (opcional) | Si se permite cerrar pestañas, cierra la actual y su panel; el foco pasa a la siguiente pestaña (o a la anterior si no hay siguiente). Si se cierra la última, el foco va a otro elemento que sostenga un flujo lógico. Puede ofrecerse también (o en su lugar) desde un menú contextual. |

## Roles, estados y propiedades WAI-ARIA

- **`tablist`:** contenedor del conjunto de pestañas.
- **`tab`:** cada pestaña; debe estar dentro de un `tablist`.
- **`tabpanel`:** contenedor del contenido de cada pestaña.
- **Nombre del `tablist`:** `aria-labelledby` si hay etiqueta visible; `aria-label` si no la hay.
- **`aria-controls` en cada `tab`:** apunta a su `tabpanel`.
- **`aria-labelledby` en cada `tabpanel`:** apunta a la pestaña que lo rotula.
- **`aria-selected`:** `true` en la pestaña activa, `false` en las demás.
- **`aria-haspopup`** en la pestaña (`menu` o `true`) si tiene menú emergente.
- **`aria-orientation="vertical"`** en el `tablist` si es vertical (por defecto es horizontal).
- **`tabindex="0"` en el `tabpanel`** cuando el panel no tiene elementos enfocables o su primer contenido no lo es, para que entre en la secuencia de Tab.

## Relación con el Módulo 3

- Ilustra la distinción **foco ≠ selección**: con activación manual, una pestaña tiene el foco sin ser la seleccionada. El diseño debe mostrar ambos estados de forma distinta (ver 2.4.7 Foco visible y 1.4.11 Contraste no textual en [`wcag22-understanding/`](wcag22-understanding/README.md)).
- Fuente original: https://www.w3.org/WAI/ARIA/apg/patterns/tabs/ (para ejemplos de código con activación automática y manual).
