# Degradados

Un degradado es una transición entre un color y otro. El navegador calculará todos los pasos
intermedios entre los colores del degradado.

Es un valor de background-image
Existen dos tipos de degradados: lineales y radiales

Un gradiente de CSS no es un <color> pero tampoco es una imagen con dimensiones intrínsecas; es decir, que no tiene tamaño natural o preferido, ni una relación preferida. Su tamaño concreto coincidirá con los elementos a los que se aplica.

## Degradados lineales

linear-gradient([direction], color-1, color-2....)
background-image: linear-gradient(red, blue);
La dirección es opcional, se puede establecer con un ángulo (20deg, 19deg...) o estableciendo una dirección del 
degradado con "to top | right | bottom | left |top left | top right |bottom left | bottom right "
background-image: linear-gradient(to right, red, blue);

Si no establecemos paradas de color, el navegador dividirá el espacio disponible entre los colores que tenga que 
pintar.

2 colores 0% 100%
3 colores 0% 50% 100%

Para establecer las paradas se puede usar cualquier medida: px, em, %...
si las paradas/inicios empiezan en el mismo sitio se genera un corte solido
background-image: linear-gradient(red 50%, blue 50%)

linear-gradient(direction, color-1 stop, color-2 start [stop]...)
linear-gradient: linear-gradient(red 50%, blue 50% 70%, green 75%)

## Degradados radiales

https://developer.mozilla.org/es/docs/Web/CSS/gradient

http://rarup777.github.io/DIWEB/Practica7/Degradados.html

https://www.youtube.com/shorts/U7HTX-CLOUc bordes con degradados

sombras con degradados https://www.youtube.com/watch?v=P53OTmmiscI