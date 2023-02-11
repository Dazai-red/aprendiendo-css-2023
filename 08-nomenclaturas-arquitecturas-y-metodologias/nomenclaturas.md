# Nombrar clases en HTML

Debemos de nombrar las clases de forma que el nombre que le pongamos (tanto a clase como id) cumpla dos funciones:

- Entender la función de la etiqueta
- Tener un código robusto al trabajar en equipo

Y para este problema tenemos una solución: la convención.

# Convenciónes en CSS
Cuando hablamos de una convención hablamos de una norma o práctica que es aceptada por acuerdo general.

Y en CSS algunos desarroladores hemos aceptado algunas convenciones, por ejemplo en cómo escribir nombres/variables:
- Camel Case
- Pascal Case
- Kebab Case
- Snake Case

# Camel Case

Es una forma de escribir nombres y variables mediante convención a frases o palabras compuestas donde la regla a seguir es: **La primera letra de cada palabra va en mayúscula.**

Y existen 2 tipos:
- lowerCamelCase: El nombre comienza en minúsculas
- UpperCamelCase: El nombre comienza en mayúsculas

```html
<div class="nombreDeUnaClase"></div>
<div id="nombreDeUnId"></div>
```

# Pascal Case

Es una forma de escribir nombres de variables mediante convención o frases o palabras compuestas la regla a seguir es: **La primera letra de cada palabra va en mayúscula siempre**

Lo podemos considerar igual que UpperCamelCase.

```html
<div class="NombreDeUnaClase"></div>
<div id="NombreDeUnId"></div>
```

# Kebab Case

Es una forma de escribir nombres y variables mediante convención a frases o palabras compuesta la regla a seguir es: **cada palabra está separada por una "barra normal"**

```html
<div class="nombre-de-una-clase"></div>
<div id="nombre-de-un-id"></div>
```

# Snake Case
Es una forma de escribir nombres y variables mediante convención a frases o palabras compuesta la regla a seguir es: **cada palabra esta separa por una "barra baja"**

```html
<div class="nombre_de_una_clase"></div>
<div id="nombre_de_un_id"></div>
```

# Arquitecturas / Metodologías CSS

Este tipo de nomenclaturas está muy asociado a Arquitecturas CSS para el desarrollo de aplicaciones con frameworks como ReactJS o Angular.