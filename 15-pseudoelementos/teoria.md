# Pseudoelementos

Se utilizan para dar estilo a partes específicas de un elemento.
La sintaxis es selector::pseudoelemento{estilos}

Existen 5 pseudoelementos:
- ::first-line (Elementos de bloque)
- ::first-letter (Elementos de bloque)
- ::before
- ::after
- ::selection

Existen algunos más pero estan en fase de experimentación y no son compatibles con todos los navegadores por eso no se 
incluyen.

## ::before y ::after

Estos son los pseudo elementos más usados en CSS, nos permiten generar dos elementos extra que serán hijos del elemento al 
que lo apliquemos.

::after se colocará después del elemento y :before antes. Usar estos pseudo elementos sería el equivalente a colocar  un 
**< span >** antes y/o después del elemento. Uso **< span >** en lugar de **< div >** porque es muy importante recordar
que los pseudo elementos ::after y ::before **son elementos de línea por defecto**

Existe mucha confusión acerca de cuando y cómo usarlos correctamente. La norma principal es que estos pseudo elementos se 
utilizan para adornar el elemento al que se lo aplicamos. Estos "hijos" no se ven reflejados en el HTML, por lo que no 
podemos seleccionarlos ni están accesibles desde JavaScript, por lo que a efectos técnicos, estos elementos no existen.

Respecto a las propiedades que les podemos aplicar la respuesta es TODAS. Lo podemos tratar como si fuera un **< span >** 
en todos los sentidos, la única peculiaridad que tienen es que debemos de usar la propiedad **content** de manera 
OBLIGATORIA, si no la usamos los elementos no se pintarán en pantalla.

Otro detalle importante es que no todos los elementos admiten **::after** y/o **::before**, estos pseudo elementos NO se 
pueden aplicar en los que se denominan **REPLACED ELEMENTS**

Estos elementos son aquellos cuyo contenido no se ve afectado por los estilos del documento actual, enlace a la mdn: 
https://developer.mozilla.org/es/docs/Web/CSS/Replaced_element

Los elementos de reemplazo más comunes en lo sque no funcionan **::after** y **::before** son los **< img >**, los 
**< input >** que admitan entrada de datos (text, number, etc.) y los **< textarea >**

Una curiosidad sobre estos pseudoelementos es que el selector universal * cuando usamos la propiedad box-sizing deja fuera a estos pseudoelementos por eso es habitual que cuando hacemos el reseteo del box-sizing:border-box se añadan al selector.

```css
*, *::before, *::after {box-sizing:border-box}

```
