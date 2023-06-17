# pseudoclases :valid, :invalid, :required y :optional

algunos selectores de validación que combinados con la pseudo clase CSS :valid, o :invalid nos permitirán crear una 
interfaz da validación más intuitiva para el usuario. Crearemos algunos ejemplos aprovechándonos también de la validación 
nativa que nos proporcionan los input type de HTML5 o el atributo pattern que ilustrarán mejor el funcionamiento de CSS :valid.

Vamos pues con unas definiciones básicas y seguimos con ejemplos prácticos

## CSS :valid / :invalid

Estas pseudo-clases seleccionan todo elemento de formulario capaz de contener un valor susceptible de ser validado. Esta validación podrá ser de varios tipos en función de una serie de atributos del elemento validado.

## input[ type ]:valid / :invalid

HTML 5 nos brinda una gran referencia de validación con sus input type mostrando mensajes específicos para cada tipo de input al pulsar el botón submit. Sin embargo con :valid podemos adelantarnos y crear nuestra propia validación en línea al instante. En el momento en que el usuario entre un valor que no cumpla con lo que HTML5 considera válido, el estado del input cambiará y CSS lo detectará, aplicando el selector que le corresponda.

De la misma forma podemos incluir un parámetro pattern que sea quién defina la cadena contra la que tenemos que comparar el valor.

## Otros selectores CSS de validación

### :required:valid

Antes incluso que comparar valores, la forma más sencilla de validar un campo es comprobar si está completado o no en caso 
de ser obligatorio. Esto lo podemos hacer añadiendo el atributo required a nuestro input, y automáticamente :valid e 
:invalid harán su magia (cuando no escribimos nada en ese campo y cambiamos de foco nos aparecera un popup de error).

### :optional
Su opuesto es :optional, que nos indica que el campo no es obligatorio, es decir no está declarado el atributo required, pero su valor puede seguir siendo susceptible de ser validado. Si quieres ahorrarle trabajo a tu usuario, indicarle que el campo es opcional es una buena forma.

### :indeterminate

Algunos tipos de input como radio o checkbox, disponen de un estado booleano: checked. Ésos activarán el selector :invalid si incluyen el atributo HTML required mientras el checkbox no esté marcado (checked)  o no se haya seleccionado uno de los radio buttons del mismo grupo, es decir, que estén en un estado «indeterminado».

Por lo tanto, en el caso de los radio buttons, podríamos usar :indeterminate en lugar de :required:invalid

Para los checkbox, puede forzarse este estado, o propiedad, mediante el uso de Javascript o jQuery. Aunque me cuesta imaginar una situación donde tuviese sentido.

Otro elemento que dispone del estado :indeterminate es < progress >. Sin embargo al ser un elemento tipo output, :valid o :invalid, no tienen efecto.

### :out-of-range

Seleccionará cualquier input que, como type number o type date, soporte los atributos min y max, y reciba un valor fuera del rango establecido por éstos.



