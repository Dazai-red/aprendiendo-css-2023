# Los problemas de CSS

Los problemas más comunes de CSS son:
- Malas prácticas como selectores, especificidad...
- ¿Qué nombre le pongo a una etiqueta?

Y para solventar este problema existen varias soluciones como:

- Básicas (header, wrapper...)
- Metodologías


# Arquitectura y metodología
Cuando queremos definir como equipo cómo se desarrollará el proyecto nos encontramos que debemos definir:
- Estructura del CSS (Arquitectura)
- Cómo trabajar CSS (Metodología)

Y tienen como objetivo cumplir que CSS sea:
- Comprensible
- Predecible
- Reutilizable
- Escalable
- Modular

# Arquitectura VS Metodología

Como resumen rápido:
- **Arquitectura** se centra en la organización de carrpetas.
- **Metodología** se centra en cómo nombrar clases.

# Metodologías 

Una metodología es un método a seguir para conseguir un objetivo concreto.

El objetivo en CSS es ponerle nombre a las clases y en términos generales se pueden dividir en dos "conceptos:"

- Bloque o Estructura
- Funcionalidades o Herramientas

# Metodologías existentes

- BEM
- SUIT CSS
- CUBE CSS

# BEM

Es una metodología que se centra en el concepto de bloque o estructura.

Es decir las reglas de cómo definir clases se basan en la estructura de HTML teniendo en cuenta:

- **Bloque** es la < contenedora >
- **Elemento** Son las < hijas > de la < contenedora >
- **Modificador** Son < hijas > con propiedades diferentes

Web oficial: https://getbem.com

# Sintaxis de BEM

Sólo se usan class, nada de id.
Los nombres de las clases no usan ningún tipo de nomenclatura como Pascal Case o Kebab Case.

Y su sintaxis se basa en: 

|   | Carácter  | Sintáxis  |
| ------------ | ------------ | ------------ |
|  Bloque  |   | .bloque  |
| Elemento  |  __ (doble guión abajo) |  .bloque__elemento  |
|  Modificador  |  -- (dobleguión) |  .bloque__elemento--modificador |

# Ejemplos de BEM
Ejemplo 1:

```html
<div class="bloque">
    <div class="bloque__elemento"></div>
    <div class="bloque__elemento bloque__elemento--modificador"></div>
</div>
```
Ejemplo 2:

```html
<ul class="menu">
    <li class="menu__li"></li>
    <li class="menu__li menu__li--active"></li>
</ul>
```

Aquí un ejemplo de CSS con BEM
```css
.menu{}
.menu__li{}
.menu__li--active{}
```
# Ventajas y desventajas de BEM

Ventajas:
- Los nombres de las clases en CSS son fáciles
- Muy pensado para usar con preprocesadores (SCSS)

Desventajas:
- El HTML queda muy largo

# SUIT 

Es una metodología que parte del concepto de funcionalidad / utildades o herramientas.

Es decir los nombres de las clases se basan en propiedades como color, centrar...

Es una metodología recomendada para usar con ReactJS y las clases se organizan en base a:
- Utilidades
- Componentes

# Sintaxis de SUIT 
En la sintaxis de cada elemento debemos de tener en cuenta el tipo de nomenclatura que debemos aplicar:

|   | Carácter  | Nomenclatura  | Sintáxis |
| ------------ | ------------ | ------------ |------------ |
|  Utilidad  |  u- | normal  | u-propiedad |
| Namespace  |  -(antes) |  normal  | body-Header |
|  Componente  |   |  PascalCase | Header |
|  Elemento (Descendiente)  | -(después)  |  lowerCamelCase | Header-h1 |
|  Modificador  | --  |  lowerCamelCase | Header-h1--black |
|  State de un Componente  | .  |  lowerCamelCase | Header.isActive |

# Ejemplo de SUIT

```html
<header class="Header">
    <h1 class="Header-logo"></h1>
    <ul class="Header-menu">
        <li class="Header-li"></li>
        <li class="Header-li Header-li.Active"></li>
        <li class="Header-li"></li>
    </ul>
</header>
```

# Ventajas y desventajas de SUIT

Ventajas:
- Muy pensado para usar con preprocesadores (SCSS)
- Por regla general se recomienda usar con ReactJS

Desventajas:
- Es más difícil usarlo en una web clásica

# Cube

Es una metodología que parte del concepto de pensar en propiedades y extender el CSS más que en bloque o estructura.

En gran parte está pensada para usar con **Logical Properties** aunque **están en Working Draft**, así que aún no debemos usarlas.

Pero podemos usar esta metodología con las propiedades actuales.

# Organización de CUBE

La organización de las clases son:

- Tokens/Utilidades: Una clase para cada propiedad CSS
- Bloques: Una clase para cada tipo de bloque

Y con el atributo data-* añadimos las:
- Excepciones: Relacionados con el State del bloque

# Sintaxis de las clases y ejemplo
Al estar basado en BEM tiene varias caracteríasticas:
- Sólo usamos clases
- Nombres de las clases se escriben kebab-case
- En HTML las clases se separan con [] o | 
- Las clases deben de escribirse en este orden:
Bloque contenedora | Bloque elemento | Utilidades

```html
<!-- Separando las claes con | -->
<div class=" contenedora | bloque | color-base padding-top" data-state="inactive"></div>
<!-- Separando las clases con [] -->
<div class=" [contenedora] [bloque]  [color-base padding-top]" data-state="inactive"></div>
```
# Organizar carpetas en CUBE

Aunque es una metodología, en el caso de usar preprocesadores como SASS o LESS se recomienda crear diferentes archivos para las utilidades y bloques

# Ventajas y desventajas de CUBE
Ventajas:
- Fácil de escalar

Desventajas:

- El HTML nos queda muy sobrecargado con los [] o |

# Resumen de Metodologías

|   | Concepto  | Nomenclatura Clases  | Orden de clases | Dónde se usa |
| ------------ | ------------ | ------------ | ------------ | ------------ |
|  BEM  |  Bloque / Estructura | Dobles guiones (normales y bajos)  | Si | Webs y Apps |
|  SUIT  |  Utilidades / Funcionalidad | Depende del tipo del elemento  | No | ReactJS |
|  CUBE  | Propiedades CSS | kebab-case  | Si | Webs y Apps |
