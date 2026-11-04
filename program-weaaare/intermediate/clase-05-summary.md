---
title: "Clase 5 — Tutoría del módulo 4: foco visible y ejercicio en grupos auditando la web Aliso"
status: draft
source:
  - ../raw-inputs/clase-05-raw.txt
  - ../raw-inputs/clase-05-contenido-escrito-raw.txt
last_updated: 2026-10-31
---

# Clase 5 — Tutoría del módulo 4 (weAAAre)

Tutoría en vivo del módulo 4 (formas de interacción). Carlos resolvió una duda sobre foco visible y dirigió un ejercicio en grupos: en salas separadas, cada grupo auditó una web de aerolínea de ejemplo (**Aliso**) con **una forma de interacción** (teclado; puntero, voz y zoom; lector de pantalla), anotó barreras y el criterio WCAG que incumple, y después un/a portavoz las presentó en la sala común. Fecha por contexto: miércoles 28 de octubre de 2026 (se menciona "mañana que es jueves" y un proyecto "enviado el 27"). Resumen del módulo: [`modulo-04-summary.md`](modulo-04-summary.md).

> **Qué no está en este resumen.** Gran parte de lo que los grupos mostraron es **visual** (pantallas de Aliso, Figma de cada grupo) y no se explica verbalmente. Aquí solo se recoge lo que la conversación permite entender: **criterios aclarados, debates resueltos y barreras identificadas**. El listado completo de fallos de Aliso (≈10 por forma de interacción) y la tabla de criterios están en la presentación que Carlos dejará junto a la grabación; **no está en el repo**.

## Foco visible: quién es responsable (duda inicial)

Pregunta de una alumna sobre si hace falta diseñar el foco y cómo medir su contraste.

- **Foco nativo (si no se toca):** el *agente de usuario* (navegador, sistema operativo) sigue sus propios estándares y **debe garantizar que el foco de los elementos nativos sea accesible**. Si no se edita ese foco, el diseño no tiene que preocuparse de medirlo (el audio dice que la propia WCAG lo plantea así).
- **Foco personalizado:** la responsabilidad pasa al diseño. El foco **debe verse** y cumplir **contraste 3:1** entre los píxeles al cambiar de un estado a otro (ej. de *hover* de un botón a foco).
- **Fondos dinámicos** (ej. foto de fondo que cambia): el diseño sigue siendo responsable de que el foco funcione en **todos** los casos.
- **Truco del foco doble (azul – blanco – azul):** un contorno con dos colores garantiza que, si uno no contrasta con el fondo, el otro sí. Ejemplo mostrado en la web que están construyendo (sobre el footer, el azul solo podía no cumplir, pero el borde blanco sí).
  - **Costo:** si cada color cumple el grosor requerido (2 px), el foco queda de ~**6 px**, grueso y a veces molesto por la distancia entre elementos.
  - **Alternativa:** con **azul + blanco (4 px)** normalmente basta; incluso se puede ahorrar el contorno interno. Se ajusta por **prueba y error**.
  - Se hace así para que **cada color cumpla los 2 px**, no que los dos sumen 2 px.
- Criterios relacionados: **2.4.7**, **1.4.11** (3:1), **2.4.13** (AAA, grosor 2 px; ver [`clase-04-summary.md`](clase-04-summary.md)).

## Ejercicio: web de aerolínea "Aliso"

Aliso permite buscar vuelo, elegir asiento, pasajero y pagar. **Con ratón funciona bien**; las barreras aparecen según la forma de interacción. Se avisó que hay **al menos ~10 fallos por forma de interacción**.

| Grupo | Misión | Notas |
|---|---|---|
| **Teclado** | Buscar vuelo Madrid → Lanzarote, ordenar resultados, cambiar día, elegir la tarifa más barata | "El más sencillo". El grupo tenía **7 tipologías de criterio** posibles (todas **A y AA**) |
| **Puntero, voz y zoom** | Elegir asiento de ventanilla y ver su precio, añadir equipaje facturado, continuar solo con la voz, completar el flujo | Incluye Zoom y reducción de movimiento |
| **Lector de pantalla** | Partir del apartado "pasajero": orientarse, rellenar datos, añadir seguro, **enviar un error a propósito** y llegar al pago | |

Reglas: sin ratón en la web; anotar **la barrera, qué pasa, cómo se detectó y el criterio que falla**; solo las que afectan a **la forma de interacción asignada**; un portavoz comparte pantalla y expone. Un grupo comentó que había anotado errores pero **no los había agrupado por criterio**: la consigna es agrupar (muchos errores pueden caer en el mismo criterio).

## Hallazgos y criterios aclarados

### Grupo teclado

| Barrera | Criterio | Resolución en clase |
|---|---|---|
| Al pasar Tab por el menú "Destino" se abre el desplegable | Propuesto **3.2.1** → **no incumple** | **Abrir un menú no es un cambio de contexto.** Se asimila a lo que ve quien usa *hover*. Si dentro del menú **Escape no lo cierra**, el criterio es **4.1.2** (el menú no cumple su función). Se verá en el módulo de componentes |
| Un grupo de opciones no se recorre con Tab (ida y vuelta al origen) | — (cumple si funciona con flechas) | **Grupo de opciones:** con **Tab se entra y se sale** del grupo; **dentro, las flechas mueven la selección**. Vale para radios, **pestañas (tabs)** y **calendario/selector de fecha**. Si **no funciona con flechas** → **4.1.2** (no cumple su función; también se podría citar 2.1.1) |
| Campo de autocompletar (combobox) en el que la flecha hacia abajo no hace nada: imposible elegir opción | **4.1.2** | El combobox debe permitir elegir con la flecha abajo; sin eso la persona no puede avanzar en el flujo |
| Una modal interrumpe y el foco queda atrapado | (trap) | En una modal el foco se atrapa **si hay salida**; se vio como "secuestro del foco" |
| Elemento sin foco visible | **2.4.7** | |
| Tras el primer paso, para llegar al contenido de los pasos siguientes hay que recorrer de nuevo el menú | **2.4.1** | Evitar bloques: el enlace "Saltar al contenido" se necesita en **cada** paso/página con bloques repetidos |
| Atajo de una sola tecla | **2.1.4** | Hallado por el grupo (criterio "del carácter") |

### Grupo lector de pantalla

| Barrera | Criterio | Resolución en clase |
|---|---|---|
| Sin salto al contenido principal | **2.4.1** | |
| Campos de formulario con `label` no asociados | **1.3.1** | |
| Varios enlaces «Ver más» / «Modificar» con el mismo texto | **2.4.4** | |
| Errores indicados solo con borde rojo | **1.4.1** (aunque no sea del lector, se vio) | |
| Ningún campo con instrucciones, ejemplos o formato | **3.3.2** (etiquetas o instrucciones) | |
| Mensajes de error o de actualización de precio no se anuncian | **4.1.3** (mensajes de estado) | Es lo que **exige** la WCAG: que el lector se entere |
| Al enviar con errores: no se anuncian y el foco no se mueve; el resumen de errores aparece arriba pero **no está programado para lectores** | **4.1.3** | Ver abajo |
| Captcha puramente visual, sin alternativa | **3.3.8** (no solo 1.1.1) | Ver abajo |

### Grupo puntero, voz y zoom

| Barrera | Criterio | Resolución en clase |
|---|---|---|
| Cuenta atrás de la reserva (asiento + equipaje) que **no se puede detener ni ampliar** y, al terminar, **devuelve al paso 1** | **2.2.1** y **3.2.5 (AAA)** | Al terminar el tiempo el sistema **cambia de contexto sin que la persona lo pida** y resetea todo: no es 3.2.1 (aplica al recibir foco) ni 3.2.2 (aplica al rellenar formularios), sino **3.2.5 Cambio a petición**, que es **AAA** |
| Tarifas distinguidas **solo por color** | **1.4.1** | |
| Slider solo con arrastre, sin alternativa | **2.5.7** y **2.5.1** | Ver "Criterios aclarados". Con voz el slider tampoco tenía **nombre accesible** (**4.1.2**) |
| Botón «Continuar» con texto visible distinto del nombre accesible | **2.5.3** | Con "mostrar números" se podría continuar, pero eso **no sirve**: el criterio falla igual |
| Carrusel sin pausa | **2.2.2** | |
| «Reducir movimiento» activado y el carrusel sigue moviéndose | **2.3.3 (AAA)** | |
| Zoom al 400%: se pierde el paso 4 y se corta parte del carrusel con su botón | el grupo lo citó como **1.4.4** | **Contraste con la WCAG:** ver abajo |
| Tooltips de los asientos que **no se descartan con Escape** y se pierden al mover el puntero | **1.4.13** | |
| Elementos con área de clic menor a **24 × 24** | **2.5.8** (tamaño mínimo del objetivo, AA) | El área de clic no alcanza el mínimo |
| Botones «Añadir» de un carrusel (seguro de viaje, embarque prioritario, coche de alquiler) con el mismo texto | propuesto **2.4.9** → **no aplica** | **2.4.9 (AAA) solo aplica a enlaces**; aquí son botones |

### Criterios aclarados en el debate (resumen para la knowledge base)

- **2.4.9 solo aplica a enlaces**, no a botones.
- **3.2.1 vs 3.2.2 vs 3.2.5:** 3.2.1 se rompe al **recibir el foco**; 3.2.2 al **introducir datos**; 3.2.5 (AAA) cuando el **sistema** cambia de contexto sin que la persona lo pida (ej. reinicio al agotarse el tiempo). Abrir un menú o desplegable no es cambio de contexto.
- **Grupos de opciones (radios, tabs, calendario):** Tab entra/sale, **flechas** mueven. Falla de flechas → **4.1.2** (o 2.1.1).
- **Menús, modales y desplegables:** deben poder **cerrarse con Escape**; si no, **4.1.2**.
- **Error de formulario y foco:**
  - Lo que **exige** la WCAG a nivel de lector es un **mensaje de estado** (**4.1.3**) que informe de que hay errores. Si aparece una lista de errores, debe notificarse **la misma información** que ve la persona que mira.
  - **Mover el foco** al primer campo con error (o al resumen de errores con enlaces a los campos) es **buena práctica, no criterio**: no es obligatorio si ya hay mensaje de estado.
  - **Problema real:** que no se mueva el foco **y** no se notifique.
  - Mejor práctica recomendada por Carlos: notificar **y** mover el foco.
  - Se puede configurar para que el foco se quede en el botón pero se anuncie un texto/sonido: debe haber una **reacción** a la acción.
- **Captcha:** **1.1.1 tiene una excepción** para captcha (dar la solución en el alt le quita el propósito). El criterio que aplica es **3.3.8 Autenticación accesible**: debe existir **una alternativa** que permita resolver el reto a todas las personas.
  - Los captchas de texto distorsionado están **obsoletos**: modelos como ChatGPT o Claude los resuelven y no protegen.
  - Hoy se usan captchas **invisibles** (análisis heurístico de si es usuario o bot, sin reto).
  - Si no hay más remedio, ofrecer alternativa (audio u otra); en el ejemplo (pie del pago) no había.
- **Enlace «Saltar al contenido»:** debe aparecer en el **primer Tab de cada página**; el audio no deja claro un matiz que se comentó sobre usuarios recurrentes.

## Avance del proyecto (comentarios de la revisión)

Una instructora (Consuelo, por contexto; figura como Speaker 1) revisó los proyectos enviados hasta el del 27 y dejó comentarios en Figma. Dos proyectos no dieron acceso al Figma (se comunicará por Discord).

- **Varios proyectos abarcan demasiados flujos.** Cada flujo es un trabajo en sí (ej. login, añadir al carrito); conviene **acotar a uno**. "No es que esté mal el proyecto, sino que es muy grande y no va a dar el tiempo".
- **Esta semana:** definir el flujo, **dibujar las pantallas** con los elementos necesarios y **pensar qué componentes se van a documentar**: **dos simples y uno complejo**. Componentes mencionados como interesantes: selector de butaca, *stepper* que añade tiempo (proyecto vinculado a energía).
- **El objetivo del curso no es diseñar bonito, sino aprender a documentar.** El diseño no tiene que ser perfecto.
- Si hay dudas sobre el alcance: **dibujarlo a mano**, tomar captura y enviarlo por Discord. **No diseñar todavía el comportamiento de los componentes**: primero elegir los dos simples y el complejo.

### Tarea oficial para la próxima tutoría (texto de la plataforma)

Publicada junto con la grabación (ver [`clase-05-contenido-escrito-raw.txt`](../raw-inputs/clase-05-contenido-escrito-raw.txt)). **Objetivo: tener el flujo acotado y las pantallas dibujadas** con los elementos que necesitan.

1. **Acotar el flujo:** si abarca demasiado, dividirlo (iniciar sesión es un flujo; añadir un producto a la cesta es otro). En los equipos de producto nadie lleva un servicio entero de punta a punta, se trabaja por flujos.
2. **Dibujar las pantallas del flujo**, aunque sea a mano; no tienen que ser bonitas. Si hay dudas de alcance, foto o captura del boceto por Discord.
3. **Pensar qué componentes documentar:** **dos simples y uno complejo**. Buenos candidatos vistos: selector de butacas, control para sumar y restar cantidades. **No diseñar todavía su comportamiento**: se trabaja con el módulo 5.
4. **Orden del proyecto:** (1) *briefing* con capturas y análisis del flujo → (2) **matriz de requisitos**, que ahora se puede completar con lo aprendido en el módulo 4 → (3) **diseño**.
5. **Lo que viene:** módulo 5 (componentes), por partes; módulo 6, donde Consuelo explica cómo especificar y documentar en Figma para el traspaso.

**Entrega:** enlace del archivo de **Figma** a soporte@weaaare.com, Discord, grupo del intensivo o mensaje privado a Carlos (basta una vía), **con permiso de visualización** verificado antes (en esta revisión, dos proyectos no se pudieron abrir por falta de acceso).

## Calendario y logística

- **Módulo 5 (componentes):** se desbloquea **por partes** (aprox. 10 lecciones cortas y otras 10, entre jueves y viernes) porque son muchas. Cubre cada tipo de componente, casuísticas y cómo interactúa con lector de pantalla y teclado.
- **Módulo 6:** Figma, documentación y sistema de diseño (documentación activa).
- **Próxima tutoría (con Carlos):** también resolverá dudas del módulo 4 y las relacionadas con el módulo 5.
- **Retraso en el módulo 4:** mucha gente no lo terminó. Se lanzará una **encuesta por Discord** para aplazar todo **una semana** si más del 50% de quienes respondan lo necesita.
- **No se alcanzó** a ver las "pinceladas" de **ARIA** (anatomía de cómo el navegador transmite información a la tecnología de apoyo) que estaban en el plan; es una pieza fundamental para la especificación final y para dar indicaciones a la IA en el módulo correspondiente.

## Contraste con la WCAG

Comparado con [`resources/wcag22-understanding/`](../../resources/wcag22-understanding/README.md):

- **Foco nativo y contraste (resuelve el matiz de `modulo-04-summary.md`):** lo dicho en clase coincide con la referencia: 1.4.11 exige 3:1 al foco, pero **no se aplica a presentaciones que determina el agente de usuario fuera del control del autor**. Si el autor **no modifica** el foco nativo, no es responsable; si lo **personaliza**, sí.
- **Zoom al 400% citado como 1.4.4:** la referencia define 1.4.4 como ampliar el **texto hasta 200%**. Pérdida de contenido al 400% de zoom corresponde a **1.4.10 Reflow** (320 px CSS ≈ 400%). Carlos no corrigió el número en la sesión.
- **Captcha y 3.3.8:** según la referencia, 3.3.8 aplica a **autenticación de usuarios existentes** y ofrece excepciones (reconocimiento de objetos o contenido propio); 3.3.9 (AAA) las elimina. Carlos usa 3.3.8 como el criterio de la alternativa al captcha; si el reto de Aliso (al final del pago) entra en el alcance de "autenticación" es **interpretación del instructor**.
- **4.1.3 para errores:** la referencia cubre confirmaciones y errores de validación (`role="alert"`, `role="status"`, regiones vivas). La identificación textual del error es **3.3.1**; en clase no se nombró.
- **3.2.1 en menús:** coincide con la referencia (cambio de contexto = envío, ventana nueva, mover el foco a otro control); abrir un menú sin mover el foco no lo es.
- **2.5.8** (tamaño mínimo 24 × 24, AA) y **3.2.5 / 2.3.3 / 2.4.9** (AAA): coinciden con los niveles de la referencia.

## Notas de transcripción

- **Hablantes sin nombre:** Speaker 2 es Carlos (guía el ejercicio); Speaker 1 mezcla una instructora y alumnas; Speaker 3 y 4, alumnas. Hay atribuciones cruzadas (p. ej. «Tu, tu, tu, tu» es Carlos tarareando mientras arma los grupos; «Uy, estoy ahí con el lector, escucho» es Carlos al visitar una sala).
- **Siglas:** «Wicat» = WCAG; «área» = ARIA; «Aliso/Alisio» = Aliso; «hover» y «fold» = hover; «cloud» = Claude; «el 241»/«el 211»/«el 413»/«el 338»/«el 144»/«el 257»/«el 253»/«el 258»/«el 249» = 2.4.1, 2.1.1, 4.1.3, 3.3.8, 1.4.4, 2.5.7, 2.5.3, 2.5.8, 2.4.9; «el 325» = 3.2.5.
- **Contenido conversacional omitido:** logística de salas (quién comparte pantalla, perder el chat del grupo), comentarios de ánimo y despedidas.

## Pendiente

- Cuando se publique la presentación de la grabación (tabla de criterios de Aliso), revisar si conviene sumarla al repo.
- Resultado de la encuesta de aplazamiento una semana (Discord).
