# Herencia

La herencia es la capacidad de algunos elementos de heredar algunas propiedades de sus elementos en contenendores, esto sería de Padres, Abuelos, BisAbuelos, de cualquier `elemento` que los contenga.

Si nosotros tenemos un html así:

```html
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Herencia en CSS</title>
  <link rel="stylesheet" href="/styles/005herencia.css">
</head>

<body>
  <h1 id="title" class="title">Herencia en <span>CSS</span></h1>
  <span>CSS</span>
</body>
```
Dentro de ``<h1></h1>`` tuvieramos un `<span></span>` y fuera de `<h1></h1>` tuvieramos otro `<span>CSS</span>` el aspecto sería distinto.
Lo que le está dando ese estilo no es la etiqueta `<span></span>`, si no la herencia que está cogiendo del `<h1></h1>`, esto funciona porque si no se heredaran ciertas propiedades sería muy caotico trabajar con CSS.

Se hirá viendo el manejo de herencias por sentido comun, por hay algunos que se heredan como el color:

```CS
.title{
  color: cyan;
}
```
Entonces veremos que ambos tienen el mismo color, hay otro tipo de propiedades, com oel tamaño de la fuente que también se heredan

```CS
.title{
  color: cyan;
  font-size: 10px;
}
```
Veremos que todo `<h1></h1>` encoje proporcionalmente, hay ciertas situaciones en las que `color` y `font-size` no se heredan, si por ejemplo tuvieramos un parrafo `<p></p>`

```html
<body>
  <h1 id="title" class="title">Herencia en <span>CSS</span></h1>
  <span>CSS</span>
  <p class="text" class="link">Lorem ipsum dolor sit amet consectetur adipisicing elit. Iure laudantium unde, tempore sapiente ipsum ratione dicta? 
    <a href="#">ENLACE DE EJEMPLO</a>  At esse vitae illo eaque iste similique atque, vel ex a impedit eveniet rerum!</p>
</body>
```
Nos daremos cuenta que el párrafo tiene un estilo y el enlace, tiene otro si nosotros a este `<p></p>` le pisieramos `.text`
```CS
.text{
  color: red;
}
```
Vemos que el enlace no heredó ese estilo eso es porque los enlaces no heredan de las propiedades del padre. Eso sucede porque los enlaces deben ser distinguidos por cuestión de funcionabilidad, si quisieramos dar un estilo a esto, modificaríamos el eanlace con su clase `link` para poder cambiar su color.

```CS
.link{
  color: red;
}
```
Sin embargo, no es la mejor manera de cambiar el color del enlace, entonces, para poder hacer un código óptimo de CSS tenemos que forzar la herencia en este tipo de situaciones, lo podemos forzar con la palabra reservada `inherit` y con esto le estamos diciendo que el color es una propiedad que nosotros queremos forzar, la herencia de color.
```CS
.link{
  color: inherit;
}
```
Y con esto el color del enlace será rojo.

Pero si quisieramos cambiar el color a gris por ejemplo para el modo oscuro, colocaríamos dicho color en el elemento padre y automáticamente cambiarían todos los hijos que tengan herencia `inherit`.

```CS
.text{
  color: lightgrey;
}

.link{
  color: inherit;
}
```
Y este valor `inherit` nos vale para cualquier propiedad que por defecto no se herede, pero queramos forzar la herencia.

También es posible que nosotros queramos la situación contraria, que nosotros no queremos que algún elemento herede características del padre o el abuelo.

```html
<!-- Lista creada para el ejemplo 2 -->
  <ul class="list">
    <li class="list-item">item 1</li>
    <li class="list-item">item 2</li>
    <li class="list-item">item 3</li>
    <li class="list-item">item 4</li>
  </ul>
```
```CS
/* Segundo ejemplo */

body{
  background-color: #333;
}

.list{
  color: indianred;
}
```
podemos ver que nuestra lista está heredando el color en todos los `<li></li>` y esta vez nosotros queremos que uno al menos no lo herede.

```html
  <ul class="list">
    <li class="list-item">item 1</li>
    <li class="list-item">item 2</li>
    <li class="list-item">item 3</li>
    <li class="list-item-extra">item 4</li>
  </ul>
```
Aunque tenga otra clase veremos que sigue heredando el color, para evitar eso tenemos `initial`, es decir vuelve a tu estado inicial, todo aquello que estés heredando ignoralo, y quedate con los estilos por defecto, esto de heredar suele traer problemas porque hay ciertos estilos que no sabemos de donde salen, que hay ciertas propiedades que se están aplicando y no lo encontramos.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/004_especificidadYCascada.md "Fundamentos de CSS")
[Siguiente **&#129042;**](/teoria/teoriaBasica/006_estilosNavegador.md "Estilos del Navegador")

---

[*Volver* **&ldca;**](/teoria/teoriaBasica/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")