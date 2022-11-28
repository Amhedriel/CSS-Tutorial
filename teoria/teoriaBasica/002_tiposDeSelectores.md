# Selectores CSS

Estaremos viendo los distintos usos de los **selectores**, que son la forma que tenemos de elegir a los **elementos** que le vamos a dar estilos.

Categorizando los estilos tenemos:


1. **Selectores Simples**

    * [Selectores elementales](#selectores-elementales "")
      * [Selector Universal](#selector-universal "")
      * [Selector de Elemento, Tipo o Etiqueta](#selector-de-elemento-tipo-o-etiqueta "")
    * [Selectores por ID y Clase](#selectores-de-atributo-id-y-clase "")
    * [Selectores por atributo](#selectores-por-atributos "")

2. **Selectores Compuestos**
    * [Selectores Agrupados]( "")
    * [Selectores Combinadores]( "")
    * [Pseudo-clases]( "")
    * [Pseudo-elementos]( "")


## Selectores Elementales

Veremos primero los 2 tipos que tenemos de selectores simples, tenemos:

* Selector Universal -> *
* Selector de Tipo o Etiqueta -> Nombre de la etiqueta

### Selector Universal

El selector universal selecciona todo lo que está en el documento web, este selector se debe utilizar con mucho cuidado y solo se utiliza en ciertos momentos muy concretos, en mi caso particular lo uso para las fuentes de texto de todo mi documento, pero generalmente se utilizan en el box-model o box-sizing, no es bueno abusar de él o por ejemplo; `*{margin: 0;}` esto
es una mala praxis.

~~~CS
*{
  background-color: lightcoral;
}
~~~

### Selector de Elemento, Tipo o Etiqueta

Simplememte sería poner el nombre de la ``etiqueta``

~~~CS
h1 {
  background-color: lightskyblue;
}
~~~
Y con eso ya lo tuviéramos seleccionado.
Si quisieramos por ejemplo dar estilo a los `<p></p>`

~~~CS
p{
  background-color: lightgreen;
}
~~~

Lo que cambia el color del fondo de los párrafos

Observamos que afecta a los 2 **\<p>** que tenemos en el .html, si tuviéramos mas **\<p>** todos se seleccionarían, este es un selector que se aplica normalmente en el ``reseteo`` que veremos más adelante aunque también se llama `normalizar estilos`.

Recordemos los selectores Universales y los selectores de Etiqueta se usan en casos muy concretos, los más utilizados y recomendables son los selectores de clase.

## Selectores de atributo ID y Clase

Veremos como funcionan los selectores de atributos, tenemos 3 tipos de selectores de atributo.

* id -> id del elemento.
* clase -> clase del elemento.
* otros atributos -> que no sean Id o Clases.

### **id**

Necesitamos tener ``elementos`` que contengan un Id; es importante que sepamos que los **selectores** de **``id``** son `case-sensitive` (significa que se respetan las mayúscula y minúsculas) pero de manera normalizada tanto **Ids** como **clases** se aplican de forma `lower-case` (minúsculas).

~~~html
<h1 id="title">Título</h1>
~~~
~~~CS
#title{
  background-color: lightgreen;
}
~~~

No es de buena práctica dar estilos con **id**, principalmente son identificadores únicos, por eso solo puede haber uno; y uno de los principios de CSS es que los estilos sean reutilizables, cosa que no es compatible con tener estilos que solo se apliquen a un ``elemento``.

### **class**

El selector **class** selecciona elementos con un atributo de clase específico. Es el que se recomienda siempre, para seleccionar una clase debemos poner punto (.) y el nombre de la clase:

~~~CS
.title{
  background-color: lightsalmon;
}
~~~

Respecto al número de clases que se pueden poner a un elemento, no tiene límite de colocar clases, se recomienda ver la metodología Bem y cómo con 2 o 3 clases se pueden aplicar estilos estables y escalables dentro de lo posible.

Podemos utilizar la ``clase`` para dar estilos a más de un solo elemento, siempre y cuando este elemento tenga el mismo nombre de ``clase``:

~~~html
<body>
  <h1 id="title" class="title">Título</h1>
  <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Enim, laborum? Natus earum, aliquid similique repellat officiis accusamus libero, optio quasi cum perferendis iste sed quos laudantium dignissimos ducimus culpa! Sit quas amet earum atque soluta ad minus placeat obcaecati quasi quis omnis, doloremque natus repellat eaque dolorem totam. Iste vitae quam, labore quo inventore, hic id cumque quasi iusto consectetur dolores corporis!</p>

  <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita voluptates officiis ratione laudantium in cumque voluptatem corporis, culpa saepe fuga a enim, eum, iste aliquid. Optio est veniam odio rem nostrum natus quaerat ratione.</p>

  <h2 class="subtitulo">Subtítulo</h2>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem dolor maxime harum, nesciunt unde debitis iusto aperiam eaque, voluptas recusandae expedita adipisci quas saepe fugiat quaerat aut magni odit animi.
  Illo voluptas modi sunt soluta aspernatur similique doloribus numquam quisquam tenetur iusto facere maxime totam, dolore dolor? Est maxime, aliquam eos earum libero eveniet, enim error distinctio obcaecati ut aliquid?
  Nemo nisi labore magni doloremque neque itaque saepe architecto, laudantium similique asperiores ab modi, officia repellendus a error odit! Dolorum aut eius architecto ut ducimus quaerat rem hic porro aliquid.
  Fuga architecto praesentium delectus a neque repellat fugit mollitia doloribus cupiditate illo magni modi optio similique, nostrum, dicta voluptates est dolore, nesciunt aspernatur voluptatum! Sint eligendi repellat rem quos explicabo!  </p>

  <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam sint laborum repellendus fuga ipsa, asperiores doloribus quis amet vitae. Voluptatum, qui ullam totam et velit voluptate. Illum molestias quod iusto.</p>
</body>
~~~

~~~CS
.text{
  background-color: lime;
}
~~~

Notemos que los dos \<p> con clase `class="text"` están siendo afectados por la clase que tienen en nuestro documento .html.

Con esto podemos consguir que con una sola línea le asignemos estilo a varios elementos y de esta forma conseguimos estilos reutilizables.

También se puede especificar que solo los elementos HTML específicos se vean afectados por una clase. Para hacer esto, comencemos con el nombre del elemento, luego escribir el carácter de punto **(.)**, seguido del nombre de la clase.

Si tuvieramos elementos para dar estilo a todos los \<p> que tengan `class="hometown`:

~~~CS
p.hometown {
  background-color: yellow;
}
~~~

Este elemento **\<p>** tendrá un estilo de acuerdo con `class="center"` y a la vez `class="large"`

```html
<p class="center large">Este parrafo hace referencia a tener 2 clases.</p>
```

## Selectores por atributos

Veremos como seleccionar otro tipo de atributos que no sean ids o clases, para ello deberemos utilizar los corchetes **`[]`** y dentro ponemos el nombre del atributo que queremos seleccionar, en .html veremos 4 enlaces y un párrafo para este ejemplo:

~~~html
  <a href="https://google.com">Enlace a google</a>
  <a href="#color-modo-random">Color random</a>
  <a href="#seccion-verde">Color verde</a>
  <a href="#color-rojo">Color rojo</a>
  <p lang="en-GB">Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis, autem nobis odio assumenda sed quibusdam incidunt iste ex voluptate delectus, natus, non dolorum tempora temporibus optio. In cum maxime debitis sit dolorem assumenda consequatur ea!</p>
~~~

Vamos a poner un atributo para que sea generico ``[atributo]``, pero en el ejemplo de css actual tenemos el `[href]`
~~~CS
[href]{
  background-color: mediumpurple;
}
~~~

Y veremos que todos los enlaces están seleccinados por su atributo `href=""`

Esta es la forma más sencilla de utilizar el selector de atributos.

### Atributo más el Valor

Para ser más especificos nosotros podemos utilizar `atributo` y `valor`, cómo usar esto?, buscaremos un atributo que nos cuadrara y utilizar ese ``atributo`` y ese ``valor``. 
~~~CS
[href="https://google.com"]{
  background-color: orangered;
}
~~~
Es importante las comillas porque si no se las pone directamente no funciona, si tenemos más de una palabra obligatoriamente debemos usar las comillas dobles.

Son muy importantes las comillas y si el valor que colocamos en ``href`` es el mismo que tiene, se va a seleccionar. 

### Atributo para comprobar si empieza por ese valor

`[atributo^="valor"]` con este selector lo que hacemos es comprobar si el atributo empieza por ese valor

~~~CS
[href^="color"] {
  background-color: goldenrod; 
}
~~~

~~~html
  <a href="https://google.com">Enlace a google</a>
  <a href="color-modo-random">Color random</a>
  <a href="#seccion-verde">Color verde</a>
  <a href="color-rojo">Color rojo</a>
~~~
Observemos que en el html tenemos 2 \<a> que tienen el atributo inicial ``color``entonces cambiará elestilo de dichas etiquetas.

### Atributo universal de elementos
`[atributo*="valor"]` con este vamos a conseguir es que se seleccione el valor que coincida independientemente del lugar donde esté.

~~~CS
[href*="color"] {
  background-color: goldenrod; 
}
~~~

~~~html
  <a href="https://google.com">Enlace a google</a>
  <a href="color-modo-random">Color random</a>
  <a href="#seccion-verde">Color verde</a>
  <a href="color-rojo">Color rojo</a>
~~~
Aunque en este caso veamos que se comporta igual que en el anterior (cambiando los `href="color..."`)

Si digamos que en lugar de `color` estuvieramos buscando ``modo`` como no tenemos un elemento que empiece por ``modo`` o termine por`modo`, colocaremos un ejemplo para ver cómo funciona con este modificador `[href*="modo"]`


~~~CS
[href*="modo"] {
  background-color: blue; 
}
~~~
~~~html
  <a href="https://google.com">Enlace a google</a>
  <a href="color-modo-random">Color random</a>
  <a href="#seccion-verde">Color verde</a>
  <a href="color-azul">Color azul</a>
~~~

Con este modificador no importa el orden que tengan los atributos ya sea al principio, al medio o al final. porque  si tiene el valor que le decimos lo va a seleccionar, los buscará y si lo encuentra en aglún lugar de sus atributos los cambiará por lo que pedimos
### Atributo de seleccion al final

Nos falta el de seleccionar si termina por la palabra que le decimos `[atributo $= valor]`, y de este modo podemos seleccionar el valor si termina por esa palabra, en nuestro caso tenemos un \<a> que termina por `azul`

~~~CS
[href$="azul"] {
  background-color: steelblue; 
}
~~~
~~~html
  <a href="https://google.com">Enlace a google</a>
  <a href="color-modo-random">Color random</a>
  <a href="#seccion-verde">Color verde</a>
  <a href="color-azul">Color rojo</a>
~~~
1:07:00
~~~CS

~~~
~~~CS

~~~



* [Universal]( "")
* [De tipo]( "")
* [Clases]( "")
* [Descendiente]( "")