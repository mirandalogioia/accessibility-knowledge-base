Fuente: GitHub — annotation-toolkit (repo oficial de GitHub)
Título: Best practices for annotating
URL: https://github.com/github/annotation-toolkit/blob/main/deep-dives/best-practices-for-annotating.md
Tipo: Deep dive del annotation toolkit de GitHub (kit de anotaciones de Figma para documentar accesibilidad en diseños)

[NOTA: markdown extraído tal cual vía `gh api` desde el repo, incluye referencias a imágenes del repo original que no se copiaron acá.]

---

# Best practices for annotating 🏆

The best annotation kit is only as useful as it is legible for the people consuming the annotations. Here are our recommended techniques for keeping our documentation easy to read and free of overwhelming clutter.

> [!TIP]
> 1. When positioning Stamps on top of a design frame, it can be helpful to Lock (**Shift + Command/Control + L**) the frame or hold down the **Space** key while dragging a component. This helps prevent Stamps being inserted into the design itself which can make them difficult to edit and disrupt the layout of any frames that use auto-layout.
> 2. You don't need to annotate existing UI that hasn't been changed in the current work, or is not an immediate part of the new user experience.

---

## Best practice 1: Keep the design frame legible
Try to place stamps outside the frame, with the "pin", "bracket", or "lasso" referencing the appropriate design element.

With closer proximity to associated Detail components in the margins, engineers can quickly scan the annotations and there is less risk of them accidentally overlooking one.

Keeping the design frame legible also makes the distinction between the original design and our annotations more obvious. This reduces the time and cognitive effort required for folks to understand the documentation.

[Imágenes comparativas: "menos legible" (23 stamps superpuestos y confusos) vs. "más legible" (stamps separados, apenas sobresaliendo del frame del diseño)]

---

## Best practice 2: Split annotation types on to duplicate frames
Large features and full pages may contain hundreds of elements to annotate. Putting every type of annotation on only one frame can make it become visually overwhelming and difficult to parse.

One strategy to help keep things legible is to duplicate the page/frame and place only one or two types of annotation on each. This also helps ensure there is room around the design to place annotations in a legible way, as described in best practice #1.

In this example, we have split one fully annotated design into two, with Focus Order annotations on their own dedicated frame.

[Imágenes comparativas: "antes" (stamps de links, botones, imágenes, focus order y headings todos mezclados) vs. "después" (focus order separado en su propio frame)]

---

## Best practice 3: Deeplink stamp labels with details
Linking a Details annotation to its corresponding Stamp can be helpful for helping people understand which Stamp is associated with which Details instance. This can be especially useful for complicated annotations, or situations where the Stamp and its corresponding label are visually separated.

To deep-link a Stamp label with its corresponding label:

1. Select the Details annotation instance.
2. Press **Command/Control + L** to copy the Details instance's URL to the clipboard. Figma will display a badge notification to communicate that the URL was successfully copied.
3. Click on the text of the corresponding Stamp label until it is highlighted.
4. Press **Command/Control + K**.
5. Figma will open a command palette menu, with the "Create link" option selected. Press **Return** to activate this option.
6. A tooltip menu will pop up over the selected Stamp label text, with a placeholder that reads, "Type or paste a URL".
7. Paste the Details annotation instance's URL into the tooltip by pressing **Command/Control + V**. Then press **Return** to add the link.
8. The Stamp text will become underlined, confirming the link has successfully been added.

[Imágenes: flujo paso a paso de copiar el link del Detail y crear el link en el Stamp]

---

## Best practice 4: Annotate only what is needed
Designs often have repeated elements, such as a list of social media links. If there's no variation for each repeated element, you may not need to annotate every single instance. Instead, you can annotate the first one and make a note of this.

This may also be the case with design treatments across multiple viewports. Many annotations might be the same regardless of viewport size or orientation. In this case, you may not need to annotate it more than once.

> [!TIP]
> It's best to communicate this intentional choice to engineering partners to avoid confusion.

[Imágenes comparativas: "antes" (7 íconos de redes sociales, cada uno con su propia anotación de imagen y link, muy ruidoso) vs. "después" (un solo ícono anotado dentro de una selección en lazo, con nota de que el nombre accesible usa el nombre del servicio)]

---

## Best practice 5: Annotate complex components separately
The complexity of an interface is not always distributed equally. When annotating parts of a design that are more dense, there may be a lot of overlap between Stamps. There may also be more detail to a component than there is surrounding space to annotate it clearly.

This can be addressed in a couple of ways:

1. Annotating complex patterns in their own frames. Here you can break a design down into smaller, more focused parts to keep things focused and more legible.
2. Using the Area out of scope utility annotation to cover parts of a page that are not relevant. This will provide more space to annotate complex sections, as well as focus attention on the parts that are relevant.

[Imagen: página de issues de GitHub.com con anotaciones extensas; header, navegación, footer y casi todos los issues de la lista cubiertos con un overlay semitransparente azul que indica "fuera de alcance / redundante"]

---

## Best practice 6: Split up complex components into separate screens

GitHub is full of complex interfaces, including patterns nested inside of other patterns. This can add additional risk, especially in terms of things like accessibility and keyboard navigation.

It's helpful to break complex patterns down into smaller pieces when documenting designs. This will help convey vital information to engineers.

For example, nested lists that contain multiple interactive items are found in many places on GitHub. There are separate annotations for the header at the top of the container, the component's container, as well as the list item itself. There are also annotations to convey focus order and keyboard navigation through several flows (not all of these are shown here).

[Imagen: set de frames de anotación para un componente de lista, separado en: contenedor, fila de acciones, estructura de contenido de los ítems, y focus order detallado]
