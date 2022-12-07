# Alto y ancho

Empecemos agregando algo de html para los ejemplos

```html
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
  <a href="#" class="inline">Elemento de línea</a>
</body>
</html>
```
Y para empezar cambiemosel color al body y sus elementos

```CS
body{
  background-color: #333;
  color: #fff;
}
```
Un fondo oscuro y letras blancas, para no cansar tanto la vista, ahora agreguemos CSS a algunos elementos y veamos que pasa:

```CS
// El elemento de bloque tendrá el fondo de color púrpura
.block{
  background-color: purple;
}
// Mientras que el de línea sería verde-agua-claro con el color de letras heredado, porque recoerdemos que el color de
//los elementos de ancla són azules subrayados.
.inline{
  background-color: lightseagreen;
  color: inherit;
}
```

Las propiedades de alto `height` y ancho `width` se colocan generalmente dentro de nuestro archivo .css en este caso cambiaremos el alto y ancho de un elemento de bloque:

```CS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
}
```

A nuestro elemento de bloque se le está dando un ancho y alto de 200px formando un cuadrado.

Con los elementos en linea no funcionan así:

```CS
.inline{
  background-color: lightseagreen;
  color: inherit;
  width: 200px;
  height: 200px;
}
```
Ninguno de estos alto y ancho funcionan, porque los elementos en línea ***no tienen medidas***, el tamaño lo determina su contenido, lo veremos agregando texto a nuestro `index.html`:

```HTML
  <h1>Box model</h1>
  <div class="block">Elemento de bloque</div>
  <a href="#" class="inline">Elemento de línea con texto extendido para ver el ejemplo de: los elementos en línea tienen medida por su contenido.</a>
```
Recordemos que solo podemos darle medidas a los elementos de bloque.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBoxModel/04.1_erroresMargin.md "Margin Errors") 
[Siguiente **&#129042;**](/teoria/teoriaBoxModel/001_boxModel.md "Box Model")

---

[*Volver* **&ldca;**](/teoria/teoriaBasica/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")