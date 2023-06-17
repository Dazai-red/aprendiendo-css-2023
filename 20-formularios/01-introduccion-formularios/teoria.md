# Estilizando formularios HTML

## ¿Porqué es tan difícil aplicar estilos a formularios con CSS?

Se añadieron los controles de formulario en la 2ª especificación HTML en 1995 CSS fue lanzado a finales de 1996, y ningún navegador lo 
implementó correctamente por años. Los navegadores le dejaban el trabajo de manejar y renderizar los formularios a los sistemas operativos.

Aun con CSS permitiendo estilizar HTML, los fabricantes de navegadores han sido — y son, hasta el día de hoy — reacios a permitir el estilizado 
de estos porque los usuarios estaban acostumbrados al estilo de sus plataformas. Esto ha cambiado. Los dueños de los sitios web quieren estilos 
que encajen con el diseño de sus páginas más que nunca, y la plataforma web ha cambiado para hacer esto posible.

Para algunos controles, todavía es díficil reconstruirlos para permitir que se puedan estilizar, pero ya podemos usar CSS para estilizar muchas 
partes de los formularios, debemos de tener cuidado para no romper la funcionalidad de este.

### No todos los controles se crean igual con CSS

Actualmente aun se encuentran dificultades cuando se utiliza CSS con formularios; estos problemas se pueden dividir en tres categorías.

#### Lo bueno

A algunos elementos se les puede dar estilo con pocos o ningún problema independientemente de la plataforma. Entre estos se incluyen los 
siguientes elementos estructurales:

- < form >
- < fieldset > y < legend >
- < input > de una sola línea (p.ej. de tipo text, url, email...), a excepción de < input type="search" >
- < textarea > de multiples líneas
- Botones (ambos < input > y < input >)
- < label >
- < output > 

#### Lo malo

Algunos elementos son más díficiles de estilizar, llegando a necesitar CSS complejo o trucos muy específicos:

- Casillas de verificación (checkbox) y botones de opción (radio).
- < input type="search" > (en-US)

#### Lo feo

En algunos elementos, simplemente no se puede utilizar CSS. Incluyendo a:

- < input type="color" >
- Controles relacionados al tiempo como < input type="datetime-local" >
- < input type="range" >
- < input type="file">
- Elementos involucrados en la creación de controles de selección como < select >, < option >, < optgroup > y < datalist >.
- < progress > y < meter > 

El verdadero problema con todos estos controles es que tienen una estructura muy compleja, y más allá de algunos estilos básicos (como cambiar el ancho o el margen del control), generalmente no tiene la capacidad de diseñar los componentes internos de los controles (como el calendario del selector de fecha, o el botón en < select > que hace que se muestre la lista de opciones) que conforman esos controles.

Si desea personalizar a fondo esos controles, realmente tiene que crear los suyos usando HTML, CSS y JavaScript. 

## Lo bueno

Para diseñar controles de formulario que son fáciles de diseñar con CSS, no debería tener mucha dificultad, ya que en su mayoría se comportan como cualquier otro elemento HTML.

Además de las herramientas básicas de CSS mencionadas anteriormente, también se nos han proporcionado varios selectores (pseudoclases de interfaz de usuario) que permiten diseñar según el estado actual de la interfaz de usuario.

Existen algunos aspectos específicos del diseño de formularios que vale la pena conocer.

### Fuentes (tipografía) y texto

Las funciones de fuente y texto CSS se pueden usar fácilmente con cualquier control (y sí, puede usar @font-face con controles de formulario). Sin embargo, el comportamiento del navegador suele ser inconsistente. De forma predeterminada, algunos controles no heredan font-family y font-size de sus padres. En su lugar, muchos navegadores utilizan la apariencia predeterminada del sistema. Para que la apariencia de sus formularios sea consistente con el resto de su contenido, puede agregar las siguientes reglas a su hoja de estilo:

```css
button, input, select, textarea {
  font-family: inherit;
  font-size: 100%;
}
```

El valor de la propiedad inherit hace que el valor de la propiedad coincida con el valor calculado de la propiedad de su elemento principal; hereda el valor del padre.

### Tamaño de caja

Todos los campos de texto tienen soporte completo para cada propiedad relacionada con el modelo de caja CSS, como width, height, padding , margin y border. Sin embargo, como antes, los navegadores se basan en los estilos predeterminados del sistema cuando muestran estos controles. Depende de usted definir cómo desea combinarlos en su contenido. Si desea mantener la apariencia nativa de los controles, enfrentará algunas dificultades si desea darles un tamaño uniforme.

Esto se debe a que cada control tiene sus propias reglas para el borde, el relleno (padding) y el margen. Para dar el mismo tamaño a varios controles diferentes, puede usar la propiedad box-sizing junto con algunos valores consistentes para otras propiedades:

```css
input, textarea, select, button {
  width : 150px;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
```

### Ubicación de la leyenda < legend >

El elemento < legend > está bien para darle estilo, pero puede ser un poco complicado controlar su ubicación. De forma predeterminada, siempre se coloca sobre el borde superior de su padre < fieldset >, cerca de la esquina superior izquierda. Para colocarlo en otro lugar, por ejemplo, dentro del conjunto de campos en algún lugar, o cerca de la esquina inferior izquierda, debe confiar en el posicionamiento.

Para posicionar la leyenda de esta manera, usamos el siguiente CSS (otras declaraciones eliminadas por brevedad):

```css
fieldset {
  position: relative;
}

legend {
  position: absolute;
  bottom: 0;
  right: 0;
}
```

El < fieldset > también debe posicionarse, de modo que < legend > se posicione en relación con él (de lo contrario, < legend > se ubicaría en relación con < body >).

El elemento < legend > es muy importante para la accesibilidad; las tecnologías de asistencia lo hablarán como parte de la etiqueta de cada elemento de formulario dentro del conjunto de campos, pero usar una técnica como la anterior está bien. El contenido de la leyenda aún se pronunciará de la misma manera; es sólo la posición visual la que ha cambiado.



