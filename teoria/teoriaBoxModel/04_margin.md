# Margin

Esta propiedad nos permite generar espacio entre elementos, `margin` es un shorthand lo que significa que es una propiedad abreviada y nos permite controlar los 4 lados posibles a los que podemos dar márgenes.
`margin` engloba:

* margin-top: Margin superior
* margin-right: Margin derecho
* margin-bottom: Margin inferior
* margin-left: Margin izquierdo

Esta propiedad admite hasta 4 propiedades que van en sentido horario:

* Si colocamos 4 valores -> margin: top right bottom left;
* si colocamos 3 valores -> margin: top left/right bottom;
* si colocamos 2 valores -> margin: top /bottom left/right;
* si colocamos 1 valor -> margin: top/right/bottom/left;

O sea, con `margin` pondríamos el primer valor para top, segundo para right, tercero para bottom y último para left.

Veamos un ejemplo de esto:

```HTML
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="/styles/styles-dist.css">
  <title>Box Model</title>
</head>
<body>
  <h1>Box model</h1>
  <div class="block">Elemento de bloque</div>
  <a href="#" class="inline">Elemento de línea con texto extendido para ver el ejemplo de: los elementos en línea tienen medida por su contenido.</a>
</body>
</html>
```

```CS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin: 100px 50px 10px 200px;
}

.inline{
  background-color: lightseagreen;
  color: inherit;
  width: 200px;
  height: 200px;
}
```
Podemos ver que el alto u ancho solo afecta al elemento en bloque, pero no sucede con el elemento en línea, porque se mantiene sin cambio con respecto al ancho y alto que se le dá.

## Elementos en línea

Hasta aquí la **propiedad** `margin` parece sencilla pero hay ciertas cosas que en los elementos en línea no funcionan igual, si nosotros tenemos dos elementos en línea casi no se distinguen que sean elementos separados:

```HTML
<!-- Modificamos el html para este ejemplo -->
<body>
  <h1>Box model</h1>
  <a href="#" class="inline">Elemento de línea 1</a>
  <a href="#" class="inline">Elemento de línea 2</a>
  <div class="block">Elemento de bloque</div>
</body>
```
```CS
.inline{
  background-color: lightseagreen;
  color: inherit;
  margin-bottom: 100px;
  margin-right: 100px;
}

```
Vemos que al colocar un `margin-bottom: 100px;` no tenemos ningun cambio en nuestro elementos en línea, ya que la distancioa con el elemento en bloque es debido al `margin: 100px 50px 10px 200px;` que nosotros le dimos.

Entonces colocamos `margin-right: 100px;` y vemos que sí funciona de hecho si coloco `margin-left: 100px;` también funciona, debemos tener cuidado con esto porque los elementos en línea solo tienen márgenes horizontales no verticales, y los elementos de bloque tienen ambos.

## Elementos de bloque

Cuando tenemos un elemento de bloque, podemos mover ese bloque con márgenes automáticos

```CS
// Si le decimos al navegador que calcule el margen

.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
}
```
Con `margin-right: auto;` vamos a pegar el elemento a la izquierda, si le ponemos `margin-left: auto;` pegamos el elemento a la derecha, muy importante saber que este elemento sea de bloque y que tenga un ancho declarado, es decir que hayamos establecido un ancho porque por ejemplo, el box model que tenenmos `<h1>Box model</h1>` es un elemento de bloque, vamos a ponerle una clase:

```HTML
  <h1 class="title">Box model</h1>
```
Y es posible que pensemos que si a `title`

```CS
.title{
  margin-left: auto;
}
```
El elemento debría irse a la derecha, pero vemos que eso no pasa, y es debido a que es un elemento de bloque, vamos a darle un `background-color: lightcoral;` veremos que la caja ya está de ese lado

```CS
.title{
  margin-left: auto;
  background-color: lightcoral;
}
```
Sin embargo si tiviera un ancho declarado, y le damos un `width: 300px;` ese trozo si se iría a la izquierda del todo

```CS
.title{
  margin-left: auto;
  background-color: lightcoral;
  width: 300px;
}
```
### ***NOTA***

Recordemos tener el ancho declarado `width: ;` porque si no el truco de `margin-left: auto;` no va a funcionar.

---

## Márgenes Automaticos

Utilizando los márgenes automáticos también podemos centrar un elemento de bloque, si le decimos que el `margin-left: auto;` es auto y el `margin-right: auto;` igual es auto, podemos ver que el elemento se centra, esto es porque le estamos diciendo que calcule automáticamente el márgen, entonces él lo que hace es dar el mismo margen, tanto a la derecha como a la izquierda, en el caso del título centraríamos la **caja**, pero no el **texto**.

```CS
.title{
  background-color: lightcoral;
  width: 300px;
  margin-right: auto;
  margin-left: auto;
}

.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
  margin-left: auto;
}
```
Si utilizáramos este truco en el título centramos la caja, porque vemos el fondo, pero si quitamos el fondo, vemos el texto a un lado, para centrar el texto dentro de un elemento de bloque tenemos otra propiedad que veremos más adelante.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBoxModel "") 
[Siguiente **&#129042;**](/teoria/teoriaBoxModel/ "")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")
