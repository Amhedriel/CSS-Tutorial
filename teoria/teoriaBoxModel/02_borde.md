# Border

Esta propiedad de **Box Model** nos permite modificar el borde de la caja, modificar, lo que sucede es que la caja ya tiene un ``border`` por defecto, si miramos el box model ya existe, pero no tiene medidas y por eso no se dibuja, lo que podemos hacer a través de la propiedad `border` es modificarlo, darle mediads, colores y hacerlo visible.

`border` es también un shorthand que agrupa 3 propiedades:

* ``border-width:`` ancho del borde
* ``border-style:`` estilo del borde
* ``border-color:`` color del borde

Para hacer una demostracion de trabajo con esto podemos utilizar la plantilla ``index.html`` de `padding` y el css igualmente de ``padding`` que es `styles3P.css`.

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Padding</title>
    <link rel="stylesheet" href="/styles/styles3P-dist.css">
  </head>
  <body>
    <header class="header">MENU</header>
    <h1 class="title">Box model</h1>
    <div class="block">Elemento de bloque</div>
    <a href="#" class="inline">Elemento de línea 1</a>
    <div class="buttons">
      <button class="button">SOY UN BOTÓN</button>
    </div>
  </body>
</html>
```
```CSS


body{
  background-color: #333;
  color: #fff;
  margin: 0px;
}

.header{
  background-color:steelblue;
}
.title{
  width: 300px;
}

.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  /* margin-top: 100px;
  margin: 0; */
  margin-right: auto;
  margin-left: auto;
  /* padding: 50px 20px 100px 70px; */
}

.inline{
  background-color: lightseagreen;
  color: inherit;
  /* padding: 50px 20px 100px 70px;
  margin-left: 100PX; */

}

.buttons{
  background-color: steelblue;
  padding-top: 20px;
  padding-bottom: 20px;
  margin-top: 30px;
}

.button{
  margin-left: 130px;
  padding: 25px 50px;
}
```

Estaremos modificando esta plantilla para este componente `border`, en todo caso para volver atrás y recordar `padding` simplemente se deben copiar el código de arriba y colocarlos es sus respectivos documentos.

Muy bien ahora veamos cómo utilizar Las propiedades de `border`.

Nosotros por ejemplo al `button` le ponemos `border;` con un ancho de `5px` y que podamos verlo con el valor de la propiedad `solid` con el color `red;` con esto veremos el borde del elemento `button`

```css
.button{
  margin-left: 130px;
  padding: 25px 50px;
  border: 1px solid red;
}
```
Esta propiedad `border: 1px solid red;` es un resumen de:

```CSS
.button{
  margin-left: 130px;
  padding: 25px 50px;
  /* Sin border: 1px solid red; nosotros escribiriamos: */
  border-width: 5px;
  border-style: solid;
  background-color: red;
}
```
Hasta aquí pareciera que ``border`` es una propiedad censilla... resulta que `border-width:`, `border-style:` y `background-color:` también son **Shorthands**, que engloban cada uno de los bordes:

* ``border-width:`` ancho del borde.
  * ``border-top-width``
  * ``border-right-width``
  * ``border-botton-width``
  * ``border-left-width``

* ``border-style:`` estilo del borde
  * ``border-top-style``
  * ``border-right-style``
  * ``border-botton-style``
  * ``border-left-style``

* ``border-color:`` color del borde
  * ``border-top-color``
  * ``border-right-color``
  * ``border-botton-color``
  * ``border-left-color``

## Listado de valores para ``style:``

- ``none`` Borra el borde.
- ``hidden`` Es el valor por defecto, porque aunque tiene borde no lo vemos.
- ``dotted`` Esto nos dá un borde con puntos y el `border-width:` indica la separación de los puntos.
- ``dashed`` Con líneas en lugar de botones, `border-width:` controla el ancho de las líneas.
- ``solid`` Dibuja el borde en pantalla.
- ``double`` Es un borde doble, `border-width: 15px;` hace un borde de ``5px`` un espacio de ``5px`` y la última línea de ``5px``.
- ``groove`` Hace un sombreado 3D con luz de abajo/derecha hacia arriba/izquiera con su respectiva sombra.
- ``ridge`` Hace un sombreado 3D con luz de arriba/izquiera hacia abajo/derecha con su respectiva sombra.
- ``inset`` Un pintado tipo retrato con luz abajo/derecha y sombra arriba/izquiera.
- ``outset`` Un pintado tipo retrato con luz arriba/izquiera y sombra abajo/derecha.

Sin embargo, ``border`` es más complejo, pero se hirá observando en el transcurso del tutorial.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBoxModel/01_contenido.md "Content") 
[Siguiente **&#129042;**](/teoria/teoriaBoxModel/03_padding.md "Padding")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")