# Propiedad Z-Index

Es la propiedad que nos permite ordenar los elementos superpuestos para controlar cual se coloca por delante y cual por detrás, Y es necesario tener `position: relative;` para que funcione.

Recordemos el "stacking context" que es el contexto de apilamiento y decide que va por delante de qué si tenemos elementos superpuestos con eta convención se decide que va delante de qué, ese es el contexto de apilamiento. 

Con `z-index` podremos manipular ese orden de apilamiento.

```HTML
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="/styles/016propiedadZ-Index.css">

  <title>Z-Index</title>
</head>
<body>
  <div class="container">
    <div>
      <div class="box box-1">Box 1</div>
    </div>
  </div>
  <div class="box box-2">Box 2</div>
  <div class="box box-3">Box 3</div>
</body>
</html>
```
```CSS
*{
  box-sizing: border-box;
}
body{
  margin: 0;
  background-color: #333;
  color: #fff;
}
.container{
  width: 200px;
  height: 200px;
  background-color: #555;
}
.box{
  width: 100px;
  height: 100px;
  text-align: center;
  color: #333;
}
.box-1{
  background-color: cyan;
}
.box-2{
  background-color: lightgreen;
}
.box-3{
  background-color: lightcoral;
}
```
Para probar empecemos agregando al `box-2`

```css
.box-2{
  background-color: lightgreen;
  position: relative;
  top: 50px;
}
```
Esta caja se pondría por encima de la `box-3`, porque en el HTML el `box-2` aparece por delante.

Esto lo podemos manipular con `z-index` para utilizarla primero debemos tener un elemento posicionado, por lo tanto vamos a darle:

```CSS
.box-3{
  background-color: lightcoral;
  position: relative;
}
```
Y con esto la caja `box-3` se pone por encima, esto tiene que ver con el contexto de apilamiento y es porque si 2 elementos están posicionados el valor de HTML es el que prevalece, al tener los 2 elementos posicionados vuelve a prevalecer el orden del HTML.

Si queremos que `box-2` vuelva a estar al frente, coloquemos `z-index`

```CSS
.box-2{
  background-color: lightgreen;
  position: relative;
  top: 50px;
  /* Propiedad z-index */
  z-index: 1;
}
```
Vuelve a estar encima porque hemos modificado su contexto de apilamiento, al no poner nada.

```CSS
.box-2{
  background-color: lightgreen;
  position: relative;
  top: 50px;
}
```
El valor por defectode ``z-index`` es `auto`, le estamos dicioendo al navegador que calcule automáticamente cuál es su orden de apilamiento. Si colocamos ``z-index: auto;`` es como no poner nada.

Para que un elemento esté por delante se pueden usar valores numerales, el más alto es el que estará al frente:

```CSS
.box-3{
  background-color: lightcoral;
  position: relative;
  z-index: 10;
}
```
Por que tiene un valor mayor este se colocará por encima.

---

## Normas con `z-index`

No utilizar números consecutivos, porque no es buena idea, debido a que en las aplicaciones al ser escalables suelen agregarse mas elementos por lo tanto al tener varios `z-index` con números consecutivos deberemos cambiar todos los `z-index` para poder añadir ese nuevo elemento; Separar entonces con una cantidad que nos permita libertad, de 10 en 10 o de 100 en 100.

Padres e hijos, es otro problema de `z-index` con decir que el padre jamás se colocará por delante del hijo es suficiente, pero lo que si se puede hacer es poner al hijo detrás del padre con un `z-index: -1;` sería suficiente.

```CSS
.box-1{
  background-color: cyan;
  z-index: -1;
}
```
Con un número negativo es suficiente, pero tenner en cuenta que si le ponemos un valor de `z-index` al padre aunque sea de 0 esto ya no funciona. El padre no debe tener un `z-index` declarado si queremos poner al hijo por detrás

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/015.4_positionSticky.md "Posición Sticky") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/017_stackingContext.md "Contexto de Apilamiento")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")