# Flexbox

## Fundamentos

### base

- Es un modelo de layout que permite que las cajas sean flexibles, es un valor de la propiedad display
- Existe display: flex y display inline-flex para que el contenedor sea bloque o linea.
- Se necesita de un contenedor (flex-container) y al menos un hijo (flex-item) al padre se le indica display flex a los hijos no es necesarios indicarle nada.
- Las cajas flexibles son los items, el contenedor es el contexto al que pertenecen los items.
- Hay más elementos que se consideran flex-item por ejemplo los after y before de un elemento flex-item tambien se consideran flex-item es decir serán flexibles.
- El texto tambien se considera un hijo del contenedor por ejemplo si tenemos un flex container y escribimos texto dentro de la etiqueta, ese texto actuara como flex-item aunque tecnicamente no sea una caja esto nos permite jugar con el para alinearlo o para colocarlo donde necesitemos.

En este ejemplo se ve un flex container con 3 hijos los hijos son los que realmente sean flexibles **Solo los hijos directos** es decir si tuvieramos elementos dentro de un flex item esos elementos no serían flex item, deberiamos de indicar display flex a los items si quisieramos que se comportase así. 

![](modelo-flexible.png)

### Ejes

Cuando escribimos display flex en un contenedor hay cosas que pasan internamente una de ellas es que se generan dos ejes:

- Existen dos ejes para colocar y alinear elementos.
- Por defecto el eje principal es horizontal y de izquierda a derecha y el eje secundario es vertical de arriba a abajo.
- Se pueden intercambiar los ejes y la dirección de ambos.
- se genera un principio (main start, cross start) y un fin (main end cross end)