# Box Shadow

Ahora veremos esta propiedad `box-shadow` se creó en un inicio para efectos de sombra a nuestras cajas, con esto podemos conseguir como una especie de efecto 3D, en escencia estamos creando un clon de la caja respetando la forma de su `box-model` (ancho, alto, redondez).

La sintaxis de `box-shadow` es distinta en función de lo que queremos, tenemos estos valores:

- ``offset-x`` desplazamiento en x (obligatorio).
- ``offset-y`` desplazamiento en y (obligatorio).
- `blur-radius` desenfoque de la sombra.
- `spread-radius` expansión de la sombra.
- `color` de la sombra, si no lo especificamos herredará del elemento al que pertenenece.
- `inset` determina si la sombra será interior o exterior.

```HTML
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="/styles/014boxShadow.css">
  <title>Box shadow</title>
</head>
<body>
  <div class="box">BOX</div>
  
</body>
</html>
```
```CSS
*{
    box-sizing: border-box;
}

.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 30px;
  box-shadow: 10px 200px;
}

```

Como podemos ver, ahora tenemos un clon de nuestra caja, respetando el `border-radius: 30px;` y el ancho y alto, si modificamos algo se ajustan.


```CSS
/* Un desplazamiento de 10px en X, lo cual lo desplaza de izquierda a derecha y
200px de desplazamiento hacia arriba o hacia abajo */
  box-shadow: 10px 200px;
```
Pero si lo modificamos de este otro modo:

```CSS
.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 30px;
  /* Con 5px en ambos valores */
  box-shadow: 5px 5px;
}
```

Tendríamos lo que se considera una sombra, y el tercer valor que tenenmos es el ``blur-radius``, esto es el desnfoque de la sombra, seria como un desenfoque Gauciano en Phtoshop, si aumentamos 10px
```CSS
  box-shadow: 5px 5px 10px;

```
Lo que tenenmos es un desenfoque de 10px.

El color por defecto es negro, pero eso sucede porque en HTML el color de la letra es negro, si nosotros establecieramos un color a esta caja.

```CSS
.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 30px;
  box-shadow: 5px 5px 10px;
  color: red;
}

```
El contenido y la sombra se colorea roja.
El color siempre va al final, en esta propiedad es completamente opcional, si ponemos en el último valor de nuestro `box-shadow: 5px 5px 10px blue;` la sombra pasaría a ser azul y no así el contenido de la caja. 

## ``pread-radius``

Esto sería la expansión de la sombra, cuanto queremos que se expanda en este caso le daremos 10px:

```CSS
.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  color: red;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 30px;
  box-shadow: 5px 5px 10px 10px blue;
}
```
Es como añadirle ``padding`` a la sombra, le estamos añadiendo 10px al tamaño original, también puede ser en negativo `box-shadow: 5px 5px 10px -10px blue;`

## ``Inset``

Determina si la sombra se va a dibujar por dentro o por fuera.

```CSS
.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  color: red;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  border-radius: 30px;
  /* la sombra se dibuja por dentro, y gracias a los valores que establecimos tiene un efecto de como relieve */
  box-shadow: inset 0 0 20px 0 #111;
}

```
Hay muchas maneras de utilizar estos valores:

```CSS
box-shadow: inset 10px 0 20px 0 #111;
```
Aqui estamos desplazando la sombra 10px hace un efecto de semi degradado de izquierda a derecha,

Si le dieramos -10px sería el mismo efecto pero por el otro lado:
```CSS
box-shadow: inset -10px 0 20px 0 #111;
```
Y si de paso agregamos algo de eje vertical tenemos otros efectos:

```CSS
box-shadow: inset -10px -10px 20px 0 #111;
```

Cuando nosotros utilizamos el valor `inset` los valores cambian.

---

Otra ventaja que tiene box-shadow es que no nos tenemos que limitar a una única sombra,

```CSS
.box{
  background-color: darkcyan;
  width: 200px;
  padding: 50px;
  color: red;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  /* border-radius: 30px;
  box-shadow: inset 0 0 20px 0 #111; */
  box-shadow: 5px 5px red;
}

Y ahí tenemos una caja que se a movido 5px y 5px, pero si ponemos una **`,`** y añadimos otra sombra:

```CSS
  box-shadow: 5px 5px red, 10px 10px blue;
```
Y aparece otra sombra azul, detrás de la roja, no hay límite de sombras que podemos crear y una de las ventajas de `box-shadow` es que funciona parecido a `outline`, que no ocupa sitio, si tuviéramos más elementos este `box-shadow` no estaría enpujando ninguna de las cajas, entonces con este efecto se pueden conseguir efectos muy llamativos.

Debemos tener cuidado de no poner una sombra justo detrás de otra, porque luego no se ve.

```CSS
  box-shadow: 5px 5px red, 5px 5px blue;
```
Con esto el `box-shadow: blue` no se vería porque tiene los mismos valores que el rojo, por lo tanto esixte, pero esta detrás

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/013_textAlign.md "Text align") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/015_position.md "Posicion")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")







