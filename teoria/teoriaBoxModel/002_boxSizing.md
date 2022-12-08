# Box sizing

Es la propiedad que nos permite controlar el calculo que hace el navegador a la hora de modificar las propiedades ``content``, ``padding`` y ``border``.

Los 2 valores que podemos darle son:

- ``content-box`` Valor por defecto.
- ``border-box`` Cálculo del tamaño del elemento incluyendo el `padding` y el `border`.

Para ver la necesidad de esta propiedad iremos al bloque e inspeccionar con el F12 y en **Styles** poder ver el BoxModel y cómo se comporta.

Utilizaremos las mismas planillas que manejamos con `styles3P.css` solo dejaremos comentados algunas cosas.

Usaremos el bloque:

```CSS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
  margin-left: auto;
  /* margin-top: 100px;
  margin: 0; */
  /* padding: 50px 20px 100px 70px; */
}
```
Que tendrá un tamaño de 200 * 200px, si le damos un `padding: 20px;` veremos que la caja a crecido, ahora tiene 200 * 200 + 20 * 20 que le hemos añadido.

```CSS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
  margin-left: auto;
  padding: 20px;
  /* margin-top: 100px;
  margin: 0; */
  /* padding: 50px 20px 100px 70px; */
}
```
Por lo cual la caja mide 240 * 240, 200 de ```height``` + 20 de ``padding top`` y + 20 ``padding botton`` = 240, lo mismo en ambos lados, antes había que usar calculos y, para tener una caja de 200px cuadrada, se tenía que cuadrar con 160px de ``width height`` y 20px para cada lado del `padding` haciendo un total de 200px de en total, pero gracias a esta propiedad estos cálculos ya no hacen tanta falta.

Si nosotros queremeos que esta caja mida 200 * 200 tenemos la opción de modificar el valor del nox sixing, por defecto su valor es 

## `content-box`

Es decir: el cálculo que hará para asignar medidas será el del contenido únicamente.

## `border-box`

pero si queremos que sume todas las propiedades del **box model** tenemos la opción de poner `border-box` como valor del ``box-sizing`` de esta forma el navegador va a hacer el cálculo del tamaño del elemento icluyendo el `padding` y el `border`:

```CSS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
  margin-left: auto;
  padding: 20px;
  /* border-box */
  box-sizing: border-box;
}
```
Como vemos automaticamente el a calculado que si el total tiene que ser 200, tiene que darle 160 al contenido y 20 de ``padding``, esto de `border-box` realmente se refiere a la caja del `border`, agrupa el `border-box`, el ``padding-box`` y el `content-box`.

La propiedad `box-sizing: padding-box` no exite, entonces solo tenemos `border-box` o `content-box`, para que calcule en función de eso, y si nosotros le añadiéramos un `border` a la caja, el navegador va a recalcular y va a restar tamaño del contenido.

```CSS
.block{
  background-color: purple;
  width: 200px;
  height: 200px;
  margin-right: auto;
  margin-left: auto;
  padding: 20px;
  box-sizing: border-box;
  /* Border */
  border: 5px solid red;
}
```
Se añade el borde y como vemos ahora es 150 de ``content``, 20 de ``padding`` y 5 de `border`, en total son los 200 * 200 que le hemos asignado porque: 150 + 40 + 10 = 200.

No tiene sentido colocar este ``box-sizing: border-box;`` en cada uno de los elementos, para eso tenemos una buena práctica que es ***Utilizar el selector Universal ``(*)``***, en ete caso concreto, el selector universal sí esta bién usarlo y se lo suele usar así:

```CSS
*{
  box-sizing: border-box;
}
```
Y de esta forma a todas las cajas que le demos tamaño van a respetar ese tamaño y realizarán el cálculo automáticamente para que añada el `padding` y el `border`, entonces siempre que iniciemos un proyecto con CSS, la primero propiedad que asignar es `*{box-sizing: border-box;}` y a partir de ahí podemos trabajar con las medidas tranquilamente.

Recordemos que en esto el `margin` no cuenta.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBoxModel/001_boxModel.md "") 
[Siguiente **&#129042;**](/teoria/teoriaBoxModel/02.1_borderRadius.md "")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")