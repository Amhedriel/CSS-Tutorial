# Text-align

Esta propiedad de primeras para sencilla, pero tiene sus complicaciones.

```html
<!DOCTYPE html>
<html lang="zxx">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="/styles/013textAlign.css">
  <title>Alineación de texto</title>
</head>
<body>
  <p class="text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Incidunt ea, cupiditate cumque aut est dolor saepe labore voluptate corporis quos ratione autem perferendis quod omnis error ex. Quaerat, corporis vel?
  Dignissimos nostrum id sequi, ad praesentium dolore quibusdam rem laborum? Rem corporis tenetur consequuntur minus fuga repudiandae reprehenderit, expedita, dolores beatae exercitationem harum natus ipsum eligendi excepturi provident! Earum, nisi?
  Mollitia, optio cupiditate iusto commodi, quod minus in consequuntur facere voluptates aut voluptatum, quaerat fugit ea culpa. Accusantium dicta, quibusdam recusandae fugit vitae magni sit inventore quo eligendi, provident aperiam.
  Accusantium deleniti nisi enim cupiditate autem, quae distinctio aliquam obcaecati dolor voluptatibus rem reprehenderit sapiente, sed assumenda. Distinctio dolore natus autem voluptatem ducimus officia similique at dignissimos voluptate! Magnam, ea.
  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusamus hic repellat maiores autem, repellendus a sunt aut, commodi eos quaerat necessitatibus quasi corporis? Perspiciatis mollitia minima corporis enim distinctio placeat dolorem. Nobis et adipisci aperiam, amet numquam consectetur minima saepe.</p>
  <div class="box">Border</div>
  <a href="#" class="link">Soy un enlace</a>
  <img src="/media/Haseo.png" alt="" class="img">
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

.box{
  background-color: #666;
  width: 100px;
  padding: 10px 0;
  margin: 20px 0;
  border: 2px solid cyan
}
```
``text-align`` es la propiedad que nos permite alinear horizontalmente el contenido de un elemento de bloque siempre que el contenido ***NO TENGA ANCHO DECLARADO***

Aceta 4 posibles valores:

* ``text-align: left;`` Alinea el contenido a la izquierda.
* ``text-align: right;`` Alinea el contenido a la derecha.
* ``text-align: center;`` Alinea el contenido al centro.
* ``text-align: justify;`` Alinea el contenido de forma justificada, No se recomienda usarlo.

## **``text-align: left;``**

Veamos ahora el párrafo con `<p class="text">` y usemos la primera propiedad
```CSS
.text{
  text-align: left;
}
```
Y no pasa absolutamente nada, por defecto cuando escribimos el contenido suele estar alineado a la izquierda, si ponemos:

```CSS
.text{
  text-align: right;
}
```
El texto se alinea a la derecha, con ``center``

```CSS
.text{
  text-align: center;
}
```
Se centra y con ``justify``

```CSS
.text{
  text-align: justify;
}
```

El texto se expande y ocupara todo el contenido, no muy recomedable para usar por motivos visuales.

## Cajas

Si nosotros utilizamos `text-align:` dentro de `box`, el contenido que esta adentro no tiene ancho declarado, la ``caja`` sí pero el ``content`` no, si ponemos:

```CSS
.box{
  background-color: #666;
  width: 100px;
  padding: 10px 0;
  margin: 20px 0;
  border: 2px solid cyan;
  /* Aqui empieza las modificaciones al contenido de la caja */
  text-align:right;
}

```
Que envía el contenido a la derecha, pero solo el contenido, no el contenedor, al igual que `text-align:center;`.

SI queremos centrar la caja:

```CSS
.box{
  background-color: #666;
  width: 100px;
  padding: 10px 0;
  margin: 20px 0;
  border: 2px solid cyan;
  text-align: center;
  /* Con margin podemos centrar el contenendor */
  margin-left: auto;
  margin-right: auto;
}
```
Se centra la caja, pero no el contenido.

## Enlaces o `link`

Si el ``link`` o `<a></a>` para ser más exactos queremos centrarlo, colocamos `text-align: center;` podemos observar que no pasa absolutamente nada, ``text-align: center;`` centra el contenido de los elementos de ``bloque``, un ``link`` es ``inline``, por lo tanto no se centrará nunca.

Por lo tanto, si queremos centrar el `link` de bemos colocarale un ``display: block;``:

```CSS
.link{
  color: inherit;
  background-color: green;
  margin-bottom: 20px;
  display: block;
  text-align: center;
}
```
Y de esta forma el `link` se centraría.

Otro problema si le ponemos `display: inline-block;` entonces ``text-align:`` no funciona, debe ser "SOLO" con elementos de bloque `display: block;`, nosotros pudimos centrar el contenido porque ahora mismo el `link` está ocupando todo el ancho disponible, si agregamos un `background-color: green;` lo vemos más visualmente; en este caso `text-align: center;` funciona porque no tiene un ancho declarado, si nosotros le ponemos un `width` el contenido se centra pero la caja no, si no tuvieramos un `background-color: green;` no lo notaríamos.

Pero en casi de que queramos centrar esta caja haríamos lo mismo que con ``.box``:

```CSS
.link{
  color: inherit;
  background-color: green;
  margin-left: auto;
  margin-right: auto;
  width: 200px;
  margin-bottom: 20px;
  display: block;
  text-align: center;
}
```
Con ``text-align:`` solo vamos a centrar el contenido.

## Imágenes un pequeño vistazo

Si le ponemos ``text-align: center;``:

```CSS
.img{
  text-align: center;
}
```
No pasa absolutamente nada, el problema es que las imágenes por defecto son `display: inline-block;` porque si le damos medidas como:

```CSS
.img{
  width: 500px;
  text-align: center;
}
```
Acepta la medida, por lo tanto es ``inline-block``.box

Si queremos centrar una imagen, debemos ponerle `display: block;`, nosotros ya deberíamos saber porque `text-align: center;` no está haciendo nada, tenemos un elemento de bloque `display: block;` y estamos centrando su contenido `text-align: center;`, pero el contenido es la propia imagen y la imagen está ocupando todo el tamaño de la caja.

Entonces:

```CSS
.img{
  display: block;
  text-align: center;
}
```
Debemos colcar:

```CSS
.img{
  display: block;
  margin-left: auto;
  margin-right: auto;
  /* text-align: center; */
}
```
Para poder centrar la imagen, y aqui `text-align` no tiene que estar porque no hará nada.

Si lo que estamos haciendo es tener una imagen en un contenedor y lo que queremos es centrar la imagen dentro de ese contenedor:

```html
  <div class="img-container">
    <img src="/media/Haseo.png" alt="" class="img">
  </div>
```
```CSS
.img-container{
  text-align: center;
}
```

En este caso `text-align: center;` Si va a tener efecto, siempre y cuando la imagen no tenga un `display: block;`, porque con `display: block;` la imagen está ocupando todo lo que puede, esto para el contenedor esta imagen ocuparía todo el ancho, por lo que si quitamos el `display: block;` nuestra imagen se puede centrar.
```CSS
.img-container{
  text-align: center;
}

/* .img{
  display: block;
  text-align: center;
} */

```
Con esto debemos tener claro si queremos centrar un caja o el contenido de una caja.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/012_outline.md "Outline") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/014_boxShadow.md "Sombras")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")