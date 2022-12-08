# Outline

Es muy similar a `border`, pero tiene sus diferencias

```HTML
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Outline</title>
  <link rel="stylesheet" href="/styles/012outline.css">
</head>
<body>
  <div class="border">Border</div>
  <div class="outline">Outline</div>
</body>
</html>
```

```CSS
*{
  box-sizing: border-box;
}
body{
  background-color: #333;
  color: #fff;
}
.border,
.outline{
  background-color: #666;
  width: 100px;
  padding: 10px 25px;
  margin: 50px 100px;
}
.border{
  border: 2px solid cyan;
}
.outline{
  border: 2px solid cyan;
}
```
Outline es la propiedad que nod permite dibujar un borde por fuera del modelo de caja.

Es un shorthand que engloba:

* ``outline-width:`` Controla el ancho del ``outline``

* ``outline-style:`` Controla el estilo del ``outline``

* ``outline-color:`` Controla el color del ``outline``

Tiene las mismas propiedades y sintaxis que ``border`` pero con algunas diferencias.

- No ocupa sitio, ya que no forma parte del `box-model`, por lo que si hacemos un borde muy grande acabaremos empujando las cajas de alrededor, con `outline` esno no pasa

- No se puede redondear, porque esto no pertenece al modelo de caja no podemos redondearlo

- No se pueden controlar los lados de forma independiente, a diferencia de `border`.

- Cuenta con una propiedad que es `online-offset` que esto nos permite aumentar o disminuir la distancia del `outline` respecto a la caja que pertenece


```CSS
.border{
  border: 2px solid cyan;
}

.outline{
  outline: 2px solid cyan;
}
```
Si nos damos cuenta el aspecto es practicamente el mismo, con la diferencia que si le colocamos `outline: 20px` la caja o se está moviendo, si le ponemos `outline: 200px` esto se pone por encima de los demás, pero no estorbaría a la otra caja.

```CSS
.outline{
  outline: 200px solid cyan;
}
```
Si lo hacemos con `border` si que hay diferencias

```CSS
.outline{
  border: 200px solid cyan;
}

En la página ya nos mueve la caja, aparece líneas de scroll, y esto ocupa sitio, entonces el `outline` nos sirve muy bien para este tipo de cosas.

```CSS
.outline{
  outline: 10px solid cyan;
  border: 5px solid lightcoral;
}
```
como vemos el `borde` termina en cierto punto, asi que online siempre se dibuja por fuera de la caja 3:51:30

```
```
```
```
```
```
```







---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/011_display.md "Errores en márgenes") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/012 "Display")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")