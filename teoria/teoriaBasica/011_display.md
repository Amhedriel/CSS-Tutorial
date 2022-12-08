# Display

```HTML
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Display</title>
  <link rel="stylesheet" href="/styles/011display.css">
</head>
<body>
  <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, rerum?</p>
  <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, rerum?</p>
  <a href="#" class="link">Enlace</a>
  <a href="#" class="link">Enlace</a>
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
.text{
  background-color: cyan;
}
.link{
  background-color: #fff;
}
```
La propiedad ``display`` nos sirve para cambiar el contexto de los elementos dentro del navegador.

Si tenenmos elemento de bloque p elementos de línea, podemos modificar su comportamiento con la propiedad `display`, admite varios valores.

- `none;` Hace que el elemento no se muestre, pero sigue cargándose.

- `block;` Hace que el elemento sea de bloque.

- `inline;` Hace que el elemento sea de línea

- `inline-block;`Hace que el elemento sea de línea pero admite medidas y márgenes verticales

Dentro de ``display`` también estan `flex`, `grid` y muchas más de las cuales se hablará en CSS intermedio.

## **``display: none;``**

Si nosotros colocaramos `display: none;` lo que hacemos es ocultar el elemento, en html si está, pero no se dibuja en el navegador.

Dembemos tener cuidado porque si estamos cargando imágenes, vídeos y otras cosas, sigue retrasando la carga de la página aunque nostros no veamos que está cargando.

```CSS
.text{
  background-color: cyan;
  display: none;
}
```
## **``display: block;``**

Con `display: block;` lo que hacemos es que un elemento que no es de bloque se comporte como un elemento de bloque, si le damos al enlace un:

```CSS
.link{
  background-color: #fff;
  display: block;
}
```
Se convierte en un elemento de bloque que tiene todas las propiedades de un elemento de bloque, le podemos dar:

```CSS
.link{
  background-color: #fff;
  display: block;
  width: 100px;
  margin-bottom: 20px;
}
```
Y funciona tranquilamente porque para el navegador los enlaces ahora son elementos de bloque.

## **``display: inline;``**

Ahora queremos tener el caso contrario, que los elementos de bloque se comporten como elementos de línea.

```CSS
.text{
  background-color: cyan;
  /* display: none; */
  display: inline;
}
```
Y como vemos ahora están al lado uno de otro, si nosotros intentamos dar un ``width: 200px;`` pues esto no funciona

```CSS
.text{
  background-color: cyan;
  /* display: none; */
  display: inline;
  width: 200px;
}
```
Son párrafos pero al darles las características de línea han perdido sus características de bloque.

## **``display: inline-block;``**

Que hace que el elemento siga siendo en línea pero con las medidas y márgenes verticalesque e hechan de menos de los elementos en línea.

```CSS
.link{
  background-color: #fff;
  display: inline-block;
  width: 150px;
  /* display: block;
  width: 100px;
  margin-bottom: 20px; */
}

Podemos ver que el elemento crece pero sigue siendo un elemento de línea, y si le colocaramos un 

```CSS
  margin-top: 50px;
```
Admite margenes verticales, pero sigue siendo de línea.

Cuando tengamos un elemento en línea, y necesitemos que sea de línea si o sí, podemos utilizar `display: inline-block;` si necesitamos darle medidas, o márgenes verticales o ambas, no se utiliza muy a menudo pero a veces salva.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/010_colapsadoDeMargenes.md "Errores en márgenes") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/011_display.md "Display")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")