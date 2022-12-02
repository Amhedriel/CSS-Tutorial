# Metodología BEM

BEM (Block Element Modifier) es debido a que todas las clases que escribiribamos se regirán por estas 3 partes. Es una metodología que nos proporciona un manera de nombrar a nuestras clases en HTML para poder usarlo de forma eficaz en CSS, BEM nos ayudará a mantener nuestro código flexible, modular y sencillo. Sobre todo a lidiar con problemas sobre especificidad.

## Bloque

Es una parte independiente en nuestro HTML, no necesita de otros ``elementos`` para existir. Por ejemplo, una galería de imágenes o un menú, no necesita de otros ``elementos``, por lo que u nbloque, por sí misma puede existir sin depender de nada más para existir.

Los bloques tienen el nombre de lo que representará, ejemplos: Header, Menu, Galeria, Footer.

```html
<section class="galeria">

</section>
```
Aquí nombramos una sección con la clase galeria.

## Elementos

Los ``elementos`` están ligados a los bloques o sea un elemento siempre estará dentro de un bloque, debiso a que es parte de él y por ende es dependiente del bloque, por ejemplo una imagen necesita de una galería de imágenes para existir; un menu tiene enlaces, y esos enlaces son dependientes del bloque, ya que no pudeden existir en otro bloque que no sea un menu, y para nombrar a los ``elementos`` primero se deberá escribir el nombre del bloque padre.

Los ``elementos`` tendrán el nombre primero del bloque al que pertenece, dos guiones bajos y después el nombre de lo que representará: **``"header__title"``**, **``"menu__item"``**, **``"galeria__img"``**. De esta manera le damos semántica a nuestro HTML.

```html
<section class="galeria">
  <img src="" class="galeria__img">
</section>
```
## Modificador

Los modoficadores son usados en ``elementos`` o bloques, se usan para representar una característica diferente que tendrá el modoficador o `elemento`.

Los modoficadores tendrán

Los modoficadoresse escribirán primero con el nombre del bloque o del ``elemento`` después otra vez el nombre del ``elemento``, dos guiones medios y la característica diferente que tendrá este bloque o elemento, **`"boton--active" "header--wave"`**.

```html
<button class="boton">Dame click</button>
<button class="boton">Dame click</button>
<!-- clase boton que representa el bloque, otra vez la clase boton con 2 guiones medios y la característica active, para denotar que este elemento tiene un característica diferente -->
<button class="boton boton--active">Dame click</button>
```
---

Ahora veamos un menú de navedación que se haría con la Metodología BEM.
```html
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navegación con BEM</title>
  <link rel="stylesheet" href="/styles/BEM.css">
</head>
<body>
  <header>
    <!-- El bloque es este nav -->
    <nav class="nav">
    <!-- Aqui tenemos el primer elemento y/o característica que es el logo -->
      <img src="/media/patternRojoDoradoNavidad.svg" alt="logo" class="nav__logo">
      <!-- Este div es el contenedor de los enlaces, nav porque es dependiente del bloque nav, dosguiones bajos y la característica links, porque esos elementos son los qque contiene (a) -->
      <div class="nav__links">
        <!-- Cada enlace va a tener la clase nav__link, porque es la clase asignada a este menú, links en plural porque es el contenedor de los links, y link en singular cada elemento del contenedor -->
        <a href="#" class="nav__link">Acerca de</a>
        <a href="#" class="nav__link">Contactos</a>
        <!-- Este último enlace es diferente por lo que tendrá un modificador más que es nav__link--active -->
        <a href="#" class="nav__link nav__link--active">Inicio</a>
      </div>
    </nav>
  </header>
  <main>

  </main>
  <footer>

  </footer>
</body>
</html>
```

Y el CSS explicado:
```CS
body{
  font-family: Arial, Helvetica, sans-serif;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.nav{
  background-color: #264de4;
  padding: 0 100px;
  // Este color blanco no afecta a los elementos <a></a> por lo que no cambia el color de dichos elementos
  color: white;
  // Esto hará que la imagen se coloque al lado de los enlaces
  display: flex;
  // Esto que los centrará verticalmente
  align-items: center;
  // Para que se peguen a las esquinas
  justify-content: space-between;
  heigth: 70px;
}

.nav__logo{
  // Al logo le daremos una altura basada en su padre al 100%
  height: 100%;
}

.nav__link{
  // Para que el color afecte a dichos <a></a> haremos que hereden el color del bloque/padre nav
  color: inherit;
  // Le diremos que los links no tengan decoración, que generalmente son las líneas bajas de subrayado
  text-decoration: none;
}
```
Ahora en el caso de preguntar el porque primero se deb poner `class="nav__link` y después el modificador `nav__link--active"` es muy fácil, porque si yo uso el modificador solamente `class="nav__link--active"` entonces perdería los cambios relacionados con `class="nav__link"` que tienen los otros `<a></a>` por ende con `class="nav__link--active"` podemos hacer más modificaciones que solo con `class="nav__link"`

```CS
.nav__link{
  color: inherit;
  text-decoration: none;
  margin-left: 2rem ;
}

.nav__link--active{
  border-bottom: 2px solid white;
}
```
Para esto es BEM para no tener que estar repitiendo código y hacerlo de forma modular, ya que si no tuvieramos en la clase a ``nav__link`` con `nav__link--active` en el link, tendríamos que repetir código para que se muestre todo como quisiéramos:

```CS
.nav__link{
  color: inherit;
  text-decoration: none;
  margin-left: 2rem ;
}

.nav__link--active{
    color: inherit;
  text-decoration: none;
  margin-left: 2rem ;
  border-bottom: 2px solid white;
}
```
Y gracias a evitar esto es lo que se utiliza la metodología BEM y así si queremos modificar solamente un elemento en específico usamos un modificador y yá, en este caso `nav__link--active`