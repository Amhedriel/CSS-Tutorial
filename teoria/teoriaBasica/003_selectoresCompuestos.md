# Selectores Compuestos

Empezaremos dando un vistazo a los selectores agrupados

2. **Selectores Compuestos**
    * [Selectores Agrupados](#selectores-agrupados)
    * [Selectores Combinadores](#selectores-combinadores)
      * [Selectores Descendentes](#selectores-descendentes)
      * [Selector Hermano](#selector-hermano)
    * [Selecotores de Hijo Directo](#selectores-de-hijo-directo)

## Selectores Agrupados

Ahora daremos estilos a nuestro html 003, en este caso vamos a suponer que queremos dar los mismos estilos a todos los párrafos `<p></p>` pero utilizando su clase.

```html
<h1 class ="title">Selectores CSS</h1>

  <P class ="subtitle">Subtítulo</P>

  <p class ="text">
    Lorem ipsum dolor sit amet consectetur adipisicing elit, minima natus dolore? Eum, laboriosam! Consequuntur, quisquam enim numquam hic culpa ducimus?
  </p>
  <div>

    <p class="text-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit quisquam tempora tenetur inventore eum? Corporis eaque sed quo doloremque, deleniti nisi laudantium fugiat, enim saepe nihil reprehenderit! Nesciunt ad corporis magnam fuga aliquid iusto, veritatis suscipit cumque dolor.</p>

    <h2>Título secundario</h2>

    <p class="text-3">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestias, minus. Perferendis vitae amet maiores, ab veniam voluptas iste dolor cumque reprehenderit asperiores architecto illum laudantium laboriosam eaque ratione praesentium in adipisci.</p>

    <p class="text-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam dolores doloremque officia nemo labore molestias esse quae dignissimos atque nam, laboriosam enim accusamus in libero? Obcaecati illo sunt vel cupiditate facilis ratione pariatur nesciunt.</p>

  </div>
```
Y el CSS normalmente lo tendríamos de esta forma:
```CS
.text{
  background-color:steelblue;
}
.text-2{
  background-color:steelblue;
}
.text-3{
  background-color:steelblue;
}
.text-4{
  background-color:steelblue;
}
```

Pero si nos damos cuenta, estamos repitiendo muchas veces el mismo estilo, Don´t repeat yourself, entonces debe haber un modo de evitar esto, y esto se logra con los elementos agrupados.

Podemos crear un ``selector`` ``agrupado``, es decir: si yo quiero dar ese mismo ``background-color`` a todos los `text`
podemos separarlos por comas.

```CS
.text,
.text-2,
.text-3,
.text-4{
  background-color:steelblue;
}
```
Como vemos funciona exactamente igual pero es más facil de leer tanto para nosotros como para los navegadores.

## Selectores Combinadores

### Selectores Descendentes

Veamos el html para entenderlo un poco:

```html
<div>

    <p class="text-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit quisquam tempora tenetur inventore eum? Corporis eaque sed quo doloremque, deleniti nisi laudantium fugiat, enim saepe nihil reprehenderit! Nesciunt ad corporis magnam fuga aliquid iusto, veritatis suscipit cumque dolor.</p>

    <h2>Título secundario</h2>

    <p class="text-3">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestias, minus. Perferendis vitae amet maiores, ab veniam voluptas iste dolor cumque reprehenderit asperiores architecto illum laudantium laboriosam eaque ratione praesentium in adipisci.</p>

    <p class="text-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam dolores doloremque officia nemo labore molestias esse quae dignissimos atque nam, laboriosam enim accusamus in libero? Obcaecati illo sunt vel cupiditate facilis ratione pariatur nesciunt.</p>

</div>
```

Con el selector descendentes lo que podemos hacer es seleccionar un ``elemento`` adentro de otro `elemento`, si quisieramos seleccionar el `<h2></h2>` por ejemplo tenemos varias formas:

```CS
h2{
  background-color: teal;
}

```
Y con esto lo seleccionaríamos pero también seleccionaríamos a todos los `<h2></h2>` que tendríamos en el html, podríamos ponerle un clase, eso indicaría que este es único:

```HTML
<h2 class="title2">Título secundario</h2>
```
Al colocarle una clase este estilo podemos reutilizarlo 

```CS
.title2{
  background-color: teal;
}
```

Pero si otro elemento tiene igualmente `.title2` pero solo queremos dar estilo a los que estén dentro de `<div></div>` en ese caso necesitamos selectores descendientes separandolos por espacio:

```CS
div .title2{
  background-color: teal;
}
```
Tenemos el mismo resultado pero solo para el `<h2></h2>` que esté dentro el `<div></div>`.
Porque si nosotros tuvieramos otro `<h2 class="title2">Título secundario</h2>` veremos que este al estar fuera del `<div></div>` entonces no se verá afectado teniendo la misma clase.

Las buenas prácticas especifican que no se debe bajar más de un nivel.

A este tipo de selección se le llama selección de hijos, estamos dentro de un padre `<div></div>`y el `<h2></h2>` al estar adentro es el hijo.

### Selector Hermano(s)

Ahora veremos los 2 últimos selectores combinadores que existen
* **Selector de Hermano siguiente** **``(+)``**: nos permite seleccionar el elemento siguiente que serían los que estén en el mismo nivel de sangría. Si queremos seleccionar el `h2` a travéz de `p calss ="text-2"`:

```CS
.text-2 + .title2{
  background-color: tomato;
}
```
De esta misma forma podriamos utilizar ``etiquetas`` como ``clases``, con esto podemos seleccionar el hermano siguiente, el que se encuentra debajo o al lado, **NO** a los demás.

* **Selector de Hermano siguiente** **`(~)`**:

Pero también tenemos la posibilidad de seleccionar a todos los hermanos siguientes:

```CS
.text-2 ~ p{
  background-color: teal;
}
```
Con esto estamos seleccionando a los demás ``<p>`` que serían `<p class="text-3">` y `<p class="text-4">`, ahora, los seleccionaría sin importar la cantidad de elementos que tuvieran entre estos "hermanos siguientes". Esto también se puede hacer con **clases**
```html
<h1 class ="title">Selectores CSS</h1>

  <P class ="subtitle">Subtítulo</P>

  <p class ="text">
    Lorem ipsum dolor sit amet consectetur adipisicing elit, minima natus dolore? Eum, laboriosam! Consequuntur, quisquam enim numquam hic culpa ducimus?
  </p>
  <div>

    <p class="text-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit quisquam tempora tenetur inventore eum? Corporis eaque sed quo doloremque, deleniti nisi laudantium fugiat, enim saepe nihil reprehenderit! Nesciunt ad corporis magnam fuga aliquid iusto, veritatis suscipit cumque dolor.</p>

    <h2 class="title2">Título secundario</h2>

    <p class="text">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestias, minus. Perferendis vitae amet maiores, ab veniam voluptas iste dolor cumque reprehenderit asperiores architecto illum laudantium laboriosam eaque ratione praesentium in adipisci.</p>

    <h2>Título secundario</h2> 
    
    <p class="text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam dolores doloremque officia nemo labore molestias esse quae dignissimos atque nam, laboriosam enim accusamus in libero? Obcaecati illo sunt vel cupiditate facilis ratione pariatur nesciunt.</p>

  </div>
```

```CS
.text-2 ~ .text{
  background-color: teal;
}
```
Lo que selecciona sería desde `.text-2` y hasta `~ .text` que serían todos los que tengan la clase text.

Se podría hacer algo como esto:

```CS
.text-2 + .title2 + p {
  background-color: teal;
}
```

## Selectores de Hijo Directo

Selecciona **solo** los hijos directos.
Con el selector descendente si ponemos 

```html
  <h2 class="title2">Título secundario</h2>
  <div class="container">

    <p class="text-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit quisquam tempora tenetur inventore eum? Corporis eaque sed quo doloremque, deleniti nisi laudantium fugiat, enim saepe nihil reprehenderit! Nesciunt ad corporis magnam fuga aliquid iusto, veritatis suscipit cumque dolor.</p>

    <h2 class="title2">Título secundario</h2>
    
    <div>
      <p class="text-3">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestias, minus. Perferendis vitae amet maiores, ab veniam voluptas iste dolor cumque reprehenderit asperiores architecto illum laudantium laboriosam eaque ratione praesentium in adipisci.</p>
    </div>
    
    <h2 class="title2">Título secundario</h2>
    
    <p class="text-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam dolores doloremque officia nemo labore molestias esse quae dignissimos atque nam, laboriosam enim accusamus in libero? Obcaecati illo sunt vel cupiditate facilis ratione pariatur nesciunt.</p>

  </div>
```

```CS
.container p{
  background-color: tomato;
}
```

Con el selector descendente nos selecciona todos los elementos `<p></p>` que estén dentro de `<div class="container"></div>` pero si nosotros queremos una selección más precisa y queremos solo los que sean hijos directos entonces utilizaremos `(>)` con esto solo se seleccionaría los hijos directos.

```CS
.container > p{
  background-color: tomato;
}
```

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/002_tiposDeSelectores.md "Selectores CSS")
[Siguiente **&#129042;**](/teoria/teoriaBasica/003.1_selectoresPseudoClases.md "Selectores pseudo clases")

---

[*Volver* **&ldca;**](/teoria/teoriaBasica/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")