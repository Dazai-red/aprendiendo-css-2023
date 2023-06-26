# Funciones CSS
Con la evolución del diseño adaptativo y su creciente complejidad, el propio CSS evoluciona constantemente y proporciona a los autores un mayor control. Las funciones min(), max(), y clamp(), que ahora son compatibles con todos los navegadores modernos, son algunas de las herramientas más recientes para crear sitios web y aplicaciones más dinámicas y adaptativas.

Cuando se trata de una tipografía flexible y fluida, un cambio de tamaño controlado de los elementos y el mantenimiento de un espaciado adecuado, las funciones min(), max() y clamp() pueden ayudar.

Las funciones matemáticas calc(), min(), max() y clamp() permiten utilizar expresiones matemáticas con la suma (+), resta (-), multiplicación (*) y división (/) como componentes de los valores.

## calc

 La función calc es especial por 3 razones: 
- Es capaz de realizar cálculos (mucho potencial con variables)
- Las operaciones se pueden realizar con diferentes tipos de unidades
- los cálculos se realizan en tiempo de ejecución es decir que 
  cada vez que haya una modificacion en el navegador todas las funciones
  calc son recalculadas.

La sintaxis es: valor operador valor

##  clamp(), min(), max()

- Son funciones mátematicas de CSS
- Nos permiten trabajar contenedores y tipografías flexibles
- Realizan el cálculo y presentan el valor resultante de uno de ellos.

Al usar estas funciones podríamos evitar usar media queries 

### min()

Evalua 1 o más expresiones separadas por coma sus parametros, y usa el valor mas pequeño de esas expresiones como su valor.

Las expresiones pueden ser expresiones matemáticas (usando operadores aritmeticos), valores literales, u otras expresiones, tales como attr(), que se evaluan a un tipo de argumento válido (like < length >).

Se pueden usar distintas unidades de medida para cada valor en la expresion, si se desea. Tambien puede usar parentesis para establecer orden de percedencia si lo requiere.

- Expresiones matematicas que involucran porcentajes para los anchos y altos en columnas de tabla, grupos de columnas de tabla, filas de tablas, y celdas de tablas en ambos layout fijo y tablas pueden ser tratados como si se hubiera especificado auto
- Es permitido anidar max() y otros funciones min() como valores de expresiones. Las expresiones son completamente matematicas asi que puede usarse adicion directa, resta, multiplicacion y division sin usar la funcion calc() en si.
- La expresion pueden ser valores combinando los operadores de adicion ( + ), resta ( - ), multiplicacion ( * ) y division ( / ) , aplicando las reglas estandares de precedencia de operadores. Asegurese de poner un espacio en cada lado de los operandos de + y -. Los oprandos en la expresion pueden ser cualquier valor de sintaxis <length>.
- Usted puede (y con frecuencia necesitara) combinar los valores min() y max(), o usar min() dentro de las funciones clamp() o calc().
- Usted puede proveer mas de 2 argumentos, si tiene multiples restricciones para aplicar.

### max()

Es exactamente igual que min pero de forma inversa en vez de evaluar el valor más pequeño de esas expresiones evalua el mayor.

### clamp()

A diferencia de min-max que pueden recibir un conjunto de párametros clamp solo recibe 3 párametros 1º valor minimo 2º 3º valor deseable máximo

básicamente une la función min y max en una sola funcion y te permite definir un rango minimo y máximo y un valor deseable.

Con esta función podemos evitar crear media queries y llenar toda nuestra hoja de media queries.

Tambíen podemos hacer uso de todas estas funciones con fuentes 

## El ancho perfecto #
De acuerdo con El estilo tipográfico de los elementos (The Elements of Typographic Style), escrito por Robert Bringhurst, "se considera que entre 45 y 75 caracteres es una longitud de línea satisfactoria para una página de una sola columna en una carátula de texto en formato serif con un tamaño de texto determinado".

Para garantizar que sus bloques de texto no sean más estrechos que 45 caracteres ni más anchos que 75, utilice clamp() y la unidad ch (avance de caracteres de ancho 0):


```css
p {
  width: clamp(45ch, 50%, 75ch);
}
```

Esto permite que el navegador defina el ancho del párrafo. Establecerá el ancho al 50%, a menos que el 50% sea más pequeño que 45ch, en cuyo caso se seleccionará 45ch, y a la inversa si el 50% es más ancho que 75ch. En esta demostración, la tarjeta por sí misma quedará sujeta:

https://www.youtube.com/watch?v=IO4c89TbJUE

https://www.youtube.com/watch?v=A5posek-upk

