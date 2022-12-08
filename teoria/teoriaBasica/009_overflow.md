# Overflow

Lo utilizamos para controlar el desbordamiento de las cajas, nosotros decimos que un contenido se desborda cuando la caja que lo contiene es menor que el contenedor.

```HTML
  <title>Border Radius</title>
  <link rel="stylesheet" href="./styles/styles4BR-dist.css">
</head>
<body>
  <div class="box">
    <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic quis incidunt, consequatur esse ea unde earum laboriosam quasi molestiae commodi perferendis perspiciatis asperiores omnis at officia beatae voluptatum reiciendis temporibus.
    Voluptates et facilis cum numquam aliquid necessitatibus, saepe itaque culpa nostrum ab voluptas rem deserunt exercitationem repellendus. Porro necessitatibus qui deserunt officiis? Maxime dolorum soluta iure id possimus dolore quidem.
    Dolore repellendus earum minus modi amet, eveniet at eaque quas dignissimos alias beatae sequi, quibusdam maiores neque odit ab blanditiis omnis cum itaque enim, deserunt cumque a. Totam, aut laborum?
    Obcaecati nobis doloribus at ab asperiores. Magni repellat libero, et quae ipsum necessitatibus in dolorem laboriosam illo voluptatem aspernatur vel tempora eius consequatur laborum odio id cum, natus architecto cupiditate?</p>
  </div>
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
  margin: 0;
}

.box{
  margin-left: auto;
  margin-right: auto;
  margin-top: 100px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
  color: black;
  /* border-top-left-radius: 50px 100px;
  border-radius: 50px 100px / 100px 150px; */
  /* border-radius: 50px; */
  /* border-top-left-radius: 50px;
  border-top-right-radius: 100px;
  border-bottom-left-radius: 150px;
  border-bottom-right-radius: 200px;
  border-radius: 50px 100px 150px 200 px; */
}
```
Podemos ver que el contenido se está desbordando de la caja, está saliendo del contenedor, con `overflow` podemos controlar este desbordamiento con 4 posibles valores

* `visible:` Valor por defecto, si colocamos este valor es igual a no colocar nada.
* `hidden:` Es para ocultar el contenido que se desborda. Si lo aplicamos en un solo eje, el otro se pondrá automaticamente en el valor ``scroll``. No se suele poner por separado.
* `scroll:` Hacemos que aparezca un barra ``scroll`` a su lado, en X en Y o en ambos y con
* `auto:` Aparecen las barras de ``scroll`` en caso que hagan falta.

`overflow` es un shorthand que engloba `overflow-x` y `overflow-y`.

```CSS
  overflow-y: hidden;
```

Con esto logramos que el contenido se esconda, pero se vuelve inaccesible.

```CSS
  overflow-y: scroll;
```
De esta forma nos aparece una barra de desplazamiento para poder movernos.

Y si ponemos auto

```CSS
overflow-y: auto;
```
No va haber ningún cambio, pero si tuvieramos menos contenido, no aparecería porque el contenido no se estuviera desbordando, pero con `scroll` si aparecería sin importar si rebasa o no.

Probemos desbordando el texto por los lados

```CSS
.text{
  width: 350px;
}
```
Con esto se está desbordando, pero nos aprace la barra en horizontal porque `overflow-y:` está en `auto;`, si estuviera con `scroll` igual se muestra aún siendo `overflow-y:`, cuando nostros damos valor a un solo eje el otro se auto configura.

Si nosotros colocaramos:

```CSS
.box{
  margin-left: auto;
  margin-right: auto;
  margin-top: 100px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
  color: black;
  overflow-y: auto;
  /* Probaremos con hidden esta vez */
  overflow-x: hidden;
}
```
Podríamos sobreescribir ese comportamiento de auto configuración, pero lo más normal es colocar `overflow: auto;`

```CSS
.box{
  margin-left: auto;
  margin-right: auto;
  margin-top: 100px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
  color: black;
  /* shorthand solo */
  overflow: auto;
}
```
De esta forma si se desborda aparece ``scroll``, esto no solo lo utilizamos con desborde de texto, hay situaciones donde ``overflow`` nos ayuda a conseguir el diseño que buscamos.

Hagamos un ejercicio:

```HTML
<body>
  <div class="box">
    <div class="box-1">
      <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Iste aliquam amet, harum quaerat ut rerum consequatur inventore? Ut aliquid possimus atque praesentium nostrum alias, ab mollitia magnam pariatur officiis consequuntur.</p>
    </div>
    <div class="box-2">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea, cumque pariatur dolor ducimus maxime repellat ipsum. Atque mollitia dicta minima deleniti reprehenderit natus non eligendi asperiores.</p>
      <!-- <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic quis incidunt, consequatur esse ea unde earum laboriosam quasi molestiae commodi perferendis perspiciatis asperiores omnis at officia beatae voluptatum reiciendis temporibus.
      Voluptates et facilis cum numquam aliquid necessitatibus, saepe itaque culpa nostrum ab voluptas rem deserunt exercitationem repellendus. Porro necessitatibus qui deserunt officiis? Maxime dolorum soluta iure id possimus dolore quidem.
      Dolore repellendus earum minus modi amet, eveniet at eaque quas dignissimos alias beatae sequi, quibusdam maiores neque odit ab blanditiis omnis cum itaque enim, deserunt cumque a. Totam, aut laborum?
      Obcaecati nobis doloribus at ab asperiores. Magni repellat libero, et quae ipsum necessitatibus in dolorem laboriosam illo voluptatem aspernatur vel tempora eius consequatur laborum odio id cum, natus architecto cupiditate?</p> -->
    </div>
  </div>
</body>
```

```CSS
*{
  box-sizing: border-box;
}

body{
  background-color: #333;
  color: #fff;
  margin: 0;
}

.box{
  margin-left: auto;
  margin-right: auto;
  margin-top: 100px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
  color: black;
  border-radius: 50px;
  /* border-top-left-radius: 50px 100px;
  border-radius: 50px 100px / 100px 150px; */
  /* border-radius: 50px; */
  /* border-top-left-radius: 50px;
  border-top-right-radius: 100px;
  border-bottom-left-radius: 150px;
  border-bottom-right-radius: 200px;
  border-radius: 50px 100px 150px 200 px; */
}

.text{
  width: 350px;
}
```
Con esto podemos ver que nuestro texto no se mira bien. 
Podemos agregar:

```CSS
.box-1, .box-2{
  padding: 10px;
}
```
Y vemos que el problema se arregla. Pero si agregamos el clásico `background-color: cyan;`

```CSS
.box-1,
.box-2{
  padding: 10px;
  background-color: cyan;
}
```
Tenemos el problema que se nos está desbordando el contenido y estamos perdiendo el fondo que teníamos, si ponemos `overflow: hidden;`

```CSS
.box{
  margin-left: auto;
  margin-right: auto;
  margin-top: 100px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
  color: black;
  border-radius: 50px;
  overflow: hidden;
}
```
Tenemos el resultado que buscábamos, porque lo que se desborda se esconde por detrás del `box`.
Recordemos que los ``<p>`` también tienen margen por defecto, le quitaremos eso.

```CSS
.text{
  /* width: 350px; */
  margin: 0;
}
```
Con esto queda mejor.

Otro ejemplo podría ser un slide de fotos lo que tenemos ralmente es un foto al lado de otra y tenemos un contenedor que hace de ventana visible, y lo que vamos haciendo es mover ese contenedor para que solo se vea la foto que entra en el marco visible, y eso lo podemos consguir también con `overflow: hidden;` para que el resto de fotos no se muestren.

Se puede usar `odverflow` con un texto dinámico de igual forma, por si es necesario `scroll` y no se rompa el diseño.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/008_boxModel.md "Box Model") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/010_colapsadoDeMargenes.md "Colapso de Márgenes")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")