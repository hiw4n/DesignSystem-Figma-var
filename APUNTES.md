# CONCEPTOS:

## root ->
 **:root** es un selector CSS que apunta al elemento raíz del documento HTML, que es siempre <html>.

¿Para qué se usa?

Principalmente para definir variables CSS globales (también llamadas custom properties).
```
:root {
  --color-primary: #0055ff;
  --font-base: "Inter", sans-serif;
  --spacing-md: 1rem;
}
```


Ventajas:
	•	Las variables definidas en :root están disponibles en todo el documento, a menos que se sobrescriban.
	•	Es la práctica más común para Design Systems en CSS puros.
	•	Son fácilmente manipulables con JavaScript o desde otros contextos CSS.

    🔹 ¿Qué son estructuras anidadas ([data-theme], etc.)?

Es una técnica para cambiar los valores de variables CSS según un atributo en el HTML, como data-theme.

Ejemplo con [data-theme]
```
<body data-theme="light">
````
```
/* Tema claro */
[data-theme="light"] {
  --color-background: #ffffff;
  --color-text: #000000;
}

/* Tema oscuro */
[data-theme="dark"] {
  --color-background: #000000;
  --color-text: #ffffff;
}
```
Luego, en cualquier parte del CSS, puedes usar:
```
body {
  background-color: var(--color-background);
  color: var(--color-text);
}
```
¿Para qué sirve esto?
	•	Theming dinámico: cambiar temas sin recargar la página.
	•	Modularidad: puedes encapsular variables para contextos diferentes.
	•	Modo oscuro/claro, diseño por marca, personalización por usuario, etc.

⸻

🔁 ¿Y cómo se relacionan :root y [data-theme]?
	•	Puedes definir valores por defecto en :root y luego sobreescribir con [data-theme].

```
:root {
  --color-background: white;
}

[data-theme="dark"] {
  --color-background: black;
}

```
¿Para qué sirve esto?
	•	Theming dinámico: cambiar temas sin recargar la página.
	•	Modularidad: puedes encapsular variables para contextos diferentes.
	•	Modo oscuro/claro, diseño por marca, personalización por usuario, etc.

⸻

🔁 ¿Y cómo se relacionan :root y [data-theme]?
	•	Puedes definir valores por defecto en :root y luego sobreescribir con [data-theme].
```
:root {
  --color-background: white;
}

[data-theme="dark"] {
  --color-background: black;
}
```