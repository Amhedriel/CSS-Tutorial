# Estilos del Navegador

## Estilos por Defecto del Navegador

Si hacemos un pequeño HTML como este:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Estilos por Defecto</title>
  <link rel="stylesheet" href="/styles/006estilosPorDefecto.css">
</head>
<body>
  <div class="container">
    <h1 class="tittle">ESTILOS POR DEFECTO</h1>
    <ul class="unorderedList">
      <li class="list-item-1">Item 1</li>
      <li class="list-item-2">Item 2</li>
      <li class="list-item-3">Item 3</li>
      <li class="list-item-4">Item 4</li>
    </ul>
  </div>
</body>
</html>
```
Para mejor visualización le daremos un poco de estilo:

```CS
body{
  background-color: #333;
}

.container{
  color: whitesmoke;
}
```
Ahora, si vemos esto mismo en diferentes navegadores, podremos observar que no se muestran de la misma forma, tienen ligeras diferencias entre sí, pareciera que no tiene mucha relevancia, si con un código tan pequeño podemos notar las diferencias, con un proyecto completo esto sería un problema. Aquí es en donde entra el término **Normalizar** los estilos, existen distintas formas de resetear los estilos del navegador, pero se recomienda utilizar siempre hasta que salga algo mejor es **Normalize**. 

Entremos a: 
* http://necolas.github.io/normalize.css/ y copiemos **Normalize.css**, 
* https://necolas.github.io/normalize.css/8.0.1/normalize.css, creamos un archivo `normalize.css` en la carpeta de `styles` 
* En nuestro proyecto y copiamos el contenido de **Normalize.css** a nuestro archivo `normalize.css`.
* Ahora, enlazamos nuestro `normalize.css` con el ``index.html`` pero siempre encima de nuestro `<link rel="stylesheet" href="styles.css`

```html
  <link rel="stylesheet" href="/styles/normalize.css">
  <link rel="stylesheet" href="/styles/006estilosPorDefecto.css">
```
Para despistados, lo debemeos poner por encima para que por cascada en caso de que se nosotros cambiemos algo esto se sobre escriba.

* Revisando `normalize.css` puede que no entendamos de momento, pero más adelante si volvemos a dar un vistazo entenderemos todo y porqué está puesto así y no de otra forma, podremos revisarlo y ver que está todo comentado y documentado, y nos dice que cosas arreglan. Debemos recordar que en nuestros proyectos siempre coloquemos este documento `normalize.css` así no importará en que navegadro se esté viendo, de esta forma sabremos que todas las fuentes, todos los margenes y todo el estado por defecto del navegador va a ser en mismo independientemente de que navegador sea.


```
```
```
```
```
```
```
```
```
```
```