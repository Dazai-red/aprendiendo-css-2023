# Variables o custom properties 
Es un espacio en memoria que almacena un valor, después usaremos ese valor en todos los sitios
necesarios y si en algún momento necesitamos cambiar ese valor, sólo tendremos que cambiar el 
valor de la variable.

Deben ir **SIEMPRE** en un selector. (En SCSS las variables pueden declararse en cualquier 
parte pero su funcionamiento es totalmente distinto al de CSS)

La sintaxis de una variable es:
Para declararla: --nombre: valor
Para usarla: propiedad: var(--nombre)

Las variables pueden almacenar cualquier **VALOR** válido en CSS, no pueden almacenar selectores
ni propiedades.

Es importante que sepamos que las variables se almacenan a nivel de documento por lo que tienen 
herencia y cascada, eso significa que se pueden heredar y que se pueden sobreescribir.

Respecto al ámbito (dónde las podemos usar) pueden ser globales las más comunes (accesibles 
desde cualquier selector) o locales (accesibles sólo desde el elemento donde se declaran)

Son keysensitive es decir sensibles a mayúsculas.