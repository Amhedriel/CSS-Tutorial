# Habiltar el panel del desarrollador

Para el desarrollo con CSS se pueden utilizar diferentes herramientas, en este caso veremos 3 modos de ingresar a las herramientas para el desarrollador:

1. **Boton derecho**, si en el navegador en el que estamos revisando nuestro proyecto presionamos el botón derecho de nuestro mouse, iremos a la última opción que es ***"inspeccionar"*** y ver las opciones en el panel que se habilita.

2. **Ctrl + Shift + i**, que nos habilita el mismo panel de que vimos arrriba.

3. **Pulsar F12**, pero existe la posibilidad de que no esté disponible en todos los navegadores, pero en los principales si funcionan.

## Panel de desarrollador

Para un mejor manejo o vista podemos ir al apartado de tres puntos **...** en caso de Edge, pero en Chrome son tres puntos en vertical, seleccionaremos "Del lado de la base" -> "Dessacoplar en una ventana independiente".

Separada la ventana entonces clickeamos en el primer ícono de la ventana, iremos a settings y si queremos lo colocamos en modo oscuro para una mejor visión, se puede ampliar el contenido haciendo zoom con Ctrl + +.

Ahora, la parte que nos interesa estan en las pestañas de **"Elementos"** en el panel grande y **"Styles"** en el panel derecho, porque es aquí donde veremos la vista previa de nuestros elementos.

En la parte izquierda tenemos nuestra estructura HTML tal como lo creamos, y al hacer click en los elementos de HTML podremos ver los datos de nuestro CSS, lo mejor es que en el panel derecho inferior nos mostrará los estilos por defecto que ya tienen esos elementos en cuyo caso nosotros no los estemos modificando, y en el panel sobre este veremos los que nosotros sí estamos modificando, y si clickeamos sobre el archivo .css que nos muestra ahí, nos enviará a nuestro archivo .css mostrandonos todos los cambios que realizamos.

Veremos en el siguiente apartado como normalizar las hojas de estilo para que en todos los navegadores sean iguales, pero por ahora veremos como funcionan las herramientas de desarrollo.

Como dijimos del panel pequeño derecho, nosotros tenemos la primera pestaña.

* **Estilos/Styles** que es en donde veremos lo que aplicamos a cada uno de nuestros elementos, si clickeamos en, por ejemplo `span`

```html
  <h1 id="title" class="title">Herencia en <span>CSS</span></h1>
  <span>CSS</span>
```

Nos indicará que tiene un `element.style {}` también que a ``Heredado de h1#title.title`` con el código de herencia:

```CS
.title{
  color: cyan
  font-size: 10px;
}
```
Y de h1 está heredando por defecto en el panel de *"hoja de estilo del agente de usuario"*:

```cs
h1{
  font-size: 2em;  // Esta opción está tachada porque no lo puede heredar .title
  font-weight: bold;
}
```
* **Calculado/Computed** Aqui tenemos la información de manera distinta, al pinchar a una opción veremos todas las propiedades que se han aplicado y porque se han aplicado, si nosotros desplegamos, por ejemplo: 
* `color` donde nos enseña el color en RGB, nos mostrará `cyan` que es el color del resultado del RGB y el responsable de que nuestro elemento tenga este color, en este caso `cyan .title`.

Un pequeño ejemplo con colores sería:

```CS
.title{
  color: cyan
  font-size: 10px;
}

// Cambiaremoso el color con una especificidad más alta, es mala praxis pero solo para este ejemplo

#title{
  color: red;
}

```

Y cuando veamos el panel de Calculado/Computed veremos que el ``color cyan`` de `.title` ahora está tachado, y el que se ah aplicado actualmente es el `color red` de `#title` por su especifidad mayor, entonces aquí tenemos una lista de que propiedades se han aplicado y cual no, y el motivo del porque no se han aplicado, además al lado de esta información nos está indicando en que línea de código en nuestro archivo.css está aplicando esta propiedad. De esta foram podemos depurar muy bien nuestro código CSS, escribamos algo y no se aplique podemos venir a nuestro **Calculado/Computed** y revisar el porqué no se está aplicando.

