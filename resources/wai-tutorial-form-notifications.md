---
title: "WAI Tutorial — Notificaciones de usuario en formularios"
status: in_progress
last_updated: 2026-10-13
---

# Notificaciones de usuario en formularios (W3C WAI)

Resumen traducido del tutorial ["User Notifications"](https://www.w3.org/WAI/tutorials/forms/notifications/) de W3C WAI, parte del módulo "Forms Tutorial". Actualizado el 3 de junio de 2022 (editores: Eric Eggert, Shadi Abou-Zahra; desarrollado por el Education and Outreach Working Group — EOWG).

Se incluye en este repo porque el Módulo 2 del programa weAAAre lo referencia al hablar de cómo documentar cuándo aparece un error, cómo lo anuncia el lector de pantalla y adónde va el foco después de enviar un formulario.

## Idea general

Las notificaciones deben ser **concisas y claras**: los mensajes de error tienen que ser comprensibles y ofrecer instrucciones simples sobre cómo resolverlos. Los mensajes de éxito también importan, para confirmar que una tarea se completó.

## 1. Retroalimentación general (Overall Feedback)

Formas de comunicar el resultado general del envío de un formulario (no campo por campo):

### Usando el encabezado principal
Se recomienda usar el `<h1>` (o el encabezado más prominente de la página) para reflejar el resultado.
```
Error: <h1>3 Errors – Billing Address</h1>
Éxito: <h1>Thank you for submitting your order.</h1>
```
El propósito primario del encabezado sigue siendo identificar la página actual, así que el mensaje debe integrarse con eso, no reemplazarlo.

### Usando el título de página
El elemento `<title>` es útil especialmente para usuarios de lectores de pantalla, que reciben la retroalimentación inmediatamente al cargar la página (antes de que se lea cualquier otro contenido).
```
<title>3 Errors – Billing Address</title>
<title>Thank you for submitting your order.</title>
```

### Usando diálogos
JavaScript puede mostrar alertas básicas (`alert()`) que respetan la navegación por teclado y la configuración del usuario:
```javascript
document.getElementById('alertconfirm')
	.addEventListener('click', function() {
		alert('Thanks for submitting the form!');
	});
```

### Listado de errores
Cuando hay errores, debe incluirse un listado al inicio de la página. Cada error listado debe:
- Referenciar la etiqueta del control correspondiente.
- Dar una descripción concisa y comprensible del error.
- Indicar cómo corregirlo y recordar los requisitos de formato.
- Incluir un enlace dentro de la página hacia el control relevante.

Código recomendado con `role="alert"`:
```html
<div role="alert">
  <h4>There are 2 errors in this form</h4>
  <ul>
  	<li>
  		<a href="#firstname" id="firstname_error">
  			The First name field is empty; it is a required 
  			field and must be filled in.
  		</a>
  	</li>
  </ul>
</div>
```

Asociar cada campo con su mensaje de error mediante `aria-describedby`:
```html
<label for="firstname">First Name:</label>
<input type="text" id="firstname" aria-describedby="firstname_error">
```

## 2. Retroalimentación en línea (In-line Feedback)

Formas de dar feedback campo por campo, en distintos momentos de la interacción.

### Después de enviar (After Submit)
Se recomienda combinar mensaje de texto + señal visual:
- Entrada válida: marca de verificación (✓) con borde verde.
- Error: ícono de error (✗ rojo o signo de exclamación) con borde rojo.

```html
<div class="success">
	<label for="username">
		<strong>OK:</strong> Username:
	</label>
	<input type="text" name="username"
		id="username" value="spaceteddy13"
		aria-describedby="userDesc">
	<span id="userDesc">✓</span>
</div>
<div class="error">
	<label for="expire">
		<strong>Error:</strong> Expiry date:
	</label>
	<input type="text" name="expire"
		id="expire" value="03.2015"
		aria-describedby="expDesc">
		<span id="expDesc">Use the format MM/YYYY.</span>
</div>
```

```css
.error   { color: #900; }
.success { color: #007a00; }
.error   input { border: 3px solid #900; }
.success input { border: 3px solid #007a00; }
```

**Dónde va el foco:** si hay errores al enviar, el foco debe ubicarse en el primer `<input>` que contiene un error.

### Durante la escritura (During Typing)

**Mensajes binarios (válido/inválido en tiempo real):** retroalimentación instantánea mientras el usuario escribe, por ejemplo verificando si un nombre de usuario está disponible:
```html
<div>
	<label for="username">Username:</label>
	<input type="text" name="username" id="username">
	<span id="username_feedback" aria-live="polite"></span>
</div>
```
```javascript
document.getElementById('username').addEventListener('keyup', function(){
	function setError(el, msg) {
		el.parentNode.querySelector('strong').innerHTML = "Error:";
		el.parentNode.className='error';
		el.parentNode.querySelector('span').innerHTML = msg;
	}
	function setSuccess(el) {
		el.parentNode.querySelector('strong').innerHTML = "OK:";
		el.parentNode.className='success';
		el.parentNode.querySelector('span').innerHTML = "&check;";
	}
	var val = this.value;
	if (val !== "") {
		if (taken_usernames.includes(val.trim())) {
			setError(this, '&cross; Sorry, this username is taken.');
		} else {
			setSuccess(this, '&check; You can use this username.');
		}
	}
});
```
**`aria-live="polite"`:** "de-enfatiza" la importancia del mensaje — no interrumpe al lector de pantalla, se lee recién cuando el usuario deja de escribir.

**Retroalimentación escalada:** por ejemplo, un medidor de fortaleza de contraseña que combina codificación por color, una etiqueta ("Weak", "Okay", "Strong") y una estimación de tiempo para descifrarla.

### Al cambiar el foco (On Focus Change)
Para datos que requieren un formato específico (como fechas), conviene validar cuando el usuario abandona el campo (evento blur), no mientras todavía está escribiendo:
```html
<div>
	<label for="expire"><strong></strong> Expiry date:</label>
	<input type="text" name="expire" id="expire" value="03.2015" 
		aria-describedby="expDesc3">
	<span id="expDesc3" aria-live="assertive"></span>
</div>
```
**`aria-live="assertive"`:** "enfatiza" la importancia del mensaje — interrumpe al lector de pantalla para leerlo antes de anunciar lo próximo que reciba foco. Por eso se reserva para mensajes que realmente ameritan interrumpir (a diferencia de `polite`, usado mientras se tipea).

## Recursos WCAG relacionados (mencionados en el tutorial)

**Criterios de éxito:**
- [3.3.1 Error Identification](wcag22-understanding/03-understandable.md) (Nivel A)
- [3.3.3 Error Suggestion](wcag22-understanding/03-understandable.md) (Nivel AA)

**Técnicas ARIA:** (ver detalle completo en [`wcag22-techniques/01-aria.md`](wcag22-techniques/01-aria.md))
- ARIA18: Using aria-alertdialog to Identify Errors
- ARIA19: Using ARIA role=alert or Live Regions to Identify Errors
- ARIA21: Using aria-invalid to Indicate An Error Field
- G83: Providing text descriptions to identify required fields
- G85: Providing text descriptions when user input falls outside format
