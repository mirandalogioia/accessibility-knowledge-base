---
title: "Las 10 heurísticas de usabilidad de Nielsen"
status: in_progress
last_updated: 2026-10-13
---

# Las 10 heurísticas de usabilidad de Nielsen

Resumen traducido del artículo ["10 Usability Heuristics for User Interface Design"](https://www.nngroup.com/articles/ten-usability-heuristics/) de Jakob Nielsen (Nielsen Norman Group). Publicado originalmente el 24 de abril de 1994, revisado por última vez el 30 de enero de 2024.

Se incluye en este repo porque el módulo del programa weAAAre lo referencia como base de principios de usabilidad que se complementan con la accesibilidad (POUR/WCAG): la accesibilidad asegura que el contenido pueda percibirse y operarse; estas heurísticas apuntan a que, una vez accesible, la interacción además sea clara y eficiente para cualquier usuario.

## Qué son

Son "principios generales para el diseño de interacción", llamados heurísticas porque representan "reglas generales y no pautas de usabilidad específicas". Nielsen las desarrolló originalmente junto con Rolf Molich en 1990 para evaluación heurística, y las refinó en 1994 a partir de un análisis factorial de 249 problemas de usabilidad reales, derivando el conjunto con mayor poder explicativo. Las 10 heurísticas se mantuvieron sin cambios desde 1994 — su vigencia de más de 25 años sugiere que seguirán aplicando a futuras generaciones de interfaces.

## Las 10 heurísticas

### 1. Visibilidad del estado del sistema
**Definición:** El diseño siempre debe mantener informados a los usuarios sobre lo que está pasando, mediante retroalimentación apropiada en un tiempo razonable.
**Por qué importa:** Cuando el usuario entiende el estado actual del sistema, aprende los resultados de sus interacciones previas y puede determinar los próximos pasos. Esta previsibilidad genera confianza tanto en el producto como en la marca.
**Cómo aplicarla:**
- Comunicar claramente el estado del sistema: ninguna acción con consecuencias debería ocurrir sin informar al usuario.
- Dar la retroalimentación lo más rápido posible, idealmente de forma inmediata.
- Construir confianza mediante comunicación abierta y continua.

### 2. Correspondencia entre el sistema y el mundo real
**Definición:** El diseño debe hablar el idioma de los usuarios, con palabras, frases y conceptos familiares en lugar de jerga interna, y seguir convenciones del mundo real para que la información aparezca en un orden natural y lógico.
**Por qué importa:** El diseño depende fuertemente de quiénes son los usuarios específicos: términos, conceptos, íconos e imágenes que son claros para quien diseña pueden confundir a los usuarios reales. Cuando los controles siguen convenciones del mundo real y corresponden a los resultados esperados (mapeo natural), el usuario aprende y recuerda la mecánica de la interfaz con más facilidad.
**Cómo aplicarla:**
- Asegurar que el usuario entienda el significado sin necesitar definiciones adicionales.
- Nunca asumir que la comprensión de quien diseña coincide con la del usuario.
- Investigar con usuarios reales para descubrir la terminología y los modelos mentales que ya tienen.

### 3. Control y libertad del usuario
**Definición:** Los usuarios suelen realizar acciones por error. Necesitan una "salida de emergencia" claramente marcada para abandonar la acción no deseada sin tener que pasar por un proceso extendido.
**Por qué importa:** Cuando las personas pueden salir fácilmente de un proceso o deshacer una acción, se genera libertad y confianza. Las salidas permiten que el usuario mantenga el control y evite la frustración de sentirse atrapado.
**Cómo aplicarla:**
- Dar soporte a funciones de deshacer y rehacer.
- Mostrar una forma clara de salir de la interacción actual, como un botón "Cancelar".
- Asegurar que la salida esté claramente etiquetada y sea fácil de encontrar.

### 4. Consistencia y estándares
**Definición:** Los usuarios no deberían tener que preguntarse si distintas palabras, situaciones o acciones significan lo mismo. Hay que seguir las convenciones de la plataforma y de la industria.
**Por qué importa:** La "Ley de Jakob" establece que las personas pasan la mayor parte de su tiempo usando productos que no son el tuyo — esas experiencias previas generan expectativas. No mantener la consistencia aumenta la carga cognitiva, porque obliga al usuario a aprender algo nuevo.
**Cómo aplicarla:**
- Mejorar la capacidad de aprendizaje manteniendo consistencia interna y externa.
- Mantener consistencia dentro de un mismo producto o familia de productos (consistencia interna).
- Seguir las convenciones establecidas de la industria (consistencia externa).

### 5. Prevención de errores
**Definición:** Los buenos mensajes de error son importantes, pero los mejores diseños previenen cuidadosamente que los problemas ocurran. Hay que eliminar las condiciones propensas al error, o detectarlas y presentar al usuario una opción de confirmación antes de que se comprometa con la acción.
**Por qué importa:** Existen dos tipos de errores: los deslices (slips, errores inconscientes por falta de atención) y los equívocos (mistakes, errores conscientes por un desajuste entre el modelo mental del usuario y el diseño).
**Cómo aplicarla:**
- Priorizar la prevención de errores de alto costo antes que las frustraciones menores.
- Evitar deslices ofreciendo restricciones útiles y buenos valores por defecto.
- Prevenir equívocos reduciendo la carga de memoria, permitiendo deshacer acciones, y advirtiendo al usuario.

### 6. Reconocimiento antes que recuerdo
**Definición:** Hay que minimizar la carga de memoria del usuario haciendo visibles los elementos, acciones y opciones. El usuario no debería tener que recordar información de una parte de la interfaz a otra. La información necesaria para usar el diseño (por ejemplo, etiquetas de campos u opciones de menú) debe estar visible o ser fácil de recuperar cuando se la necesita.
**Por qué importa:** Los seres humanos tenemos una memoria de corto plazo limitada. Las interfaces que promueven el reconocimiento reducen el esfuerzo cognitivo que se le exige al usuario.
**Cómo aplicarla:**
- Permitir que las personas reconozcan la información en lugar de forzarlas a recordarla.
- Ofrecer ayuda en contexto en lugar de tutoriales extensos para memorizar.
- Reducir la cantidad de información que el usuario debe recordar.

### 7. Flexibilidad y eficiencia de uso
**Definición:** Los atajos — ocultos para usuarios novatos — pueden acelerar la interacción para el usuario experto, de modo que el diseño pueda atender tanto a usuarios sin experiencia como a usuarios experimentados. Hay que permitir que el usuario adapte las acciones frecuentes.
**Por qué importa:** Los procesos flexibles pueden ejecutarse de distintas formas, permitiendo que cada persona elija el método que mejor le funciona.
**Cómo aplicarla:**
- Proveer aceleradores como atajos de teclado y gestos táctiles.
- Ofrecer personalización, adaptando contenido y funcionalidad a cada persona.
- Permitir la customización, para que el usuario decida cómo funciona el producto.

### 8. Diseño estético y minimalista
**Definición:** Las interfaces no deberían contener información irrelevante o que rara vez se necesita. Cada unidad extra de información en una interfaz compite con las unidades relevantes y disminuye su visibilidad relativa.
**Por qué importa:** Esto no implica necesariamente un diseño "flat" — significa mantener el contenido y el diseño visual de la interfaz enfocados en lo esencial, asegurando que los elementos visuales apoyen los objetivos principales del usuario.
**Cómo aplicarla:**
- Mantener el contenido y el diseño visual de la interfaz enfocados en lo esencial.
- No dejar que elementos innecesarios distraigan de la información que sí se necesita.
- Priorizar el contenido y las funciones que apoyan los objetivos principales del usuario.

### 9. Ayudar a los usuarios a reconocer, diagnosticar y recuperarse de errores
**Definición:** Los mensajes de error deben expresarse en lenguaje claro (sin códigos de error), indicar el problema con precisión, y sugerir una solución de forma constructiva.
**Por qué importa:** Los mensajes de error requieren un tratamiento visual que ayude al usuario a notarlos y reconocerlos.
**Cómo aplicarla:**
- Usar tratamientos visuales tradicionales para mensajes de error, como texto en negrita y rojo.
- Decir al usuario qué salió mal en un lenguaje comprensible, evitando jerga técnica.
- Ofrecer soluciones, como atajos que resuelvan el error de inmediato.

### 10. Ayuda y documentación
**Definición:** Es preferible que el sistema no necesite ninguna explicación adicional. Sin embargo, puede ser necesario proveer documentación que ayude al usuario a entender cómo completar sus tareas.
**Por qué importa:** La documentación de ayuda debe ser buscable y estar enfocada en la tarea, manteniéndose concisa mientras enumera los pasos concretos necesarios.
**Cómo aplicarla:**
- Asegurar que la documentación de ayuda sea fácil de buscar.
- Presentar la documentación en contexto, en el momento en que el usuario la necesita.
- Enumerar los pasos concretos que hay que seguir.

## Relación con accesibilidad

Estas heurísticas son principios de **usabilidad** (que el producto sea fácil y eficiente de usar para cualquier persona), mientras que WCAG/POUR son principios de **accesibilidad** (que el producto pueda ser percibido y operado por personas con discapacidad). Son complementarios, no intercambiables: una interfaz puede ser técnicamente accesible (cumple WCAG) y aun así tener mala usabilidad (viola varias heurísticas de Nielsen), o viceversa. Ver [`wcag22-understanding/`](wcag22-understanding/README.md) y [`wcag22-techniques/`](wcag22-techniques/README.md) para el lado de accesibilidad.
