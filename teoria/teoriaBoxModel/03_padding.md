# Propiedad padding

Esta propiedad nos permite generar espacio interno entre el borde y la caja de contenido, el borde de la caja son los límites que tiene la caja, eso es el borde, y al igual que `margin` se lo considera un shortHand que nos permite controlar los 4 lados posibles a los que dar ``padding``:

* padding-top: padding superior
* padding-right: padding derecho
* padding-bottom: padding inferior
* padding-left: padding izquierdo

Esta propiedad admite hasta 4 propiedades que van en sentido horario:

* Si colocamos 4 valores -> padding: top right bottom left;
* si colocamos 3 valores -> padding: top left/right bottom;
* si colocamos 2 valores -> padding: top /bottom left/right;
* si colocamos 1 valor -> padding: top/right/bottom/left;

* [Elementos de bloque](#elementos-de-bloque)
* [Elementos en línea](#elementos-en-línea)
* [Cuando usar margin o paddings¿?](#cuando-usar-margin-o-paddings¿)
* []()

Generalmente asignar valores a alguna propiedad siempre se hará en el sentido del reloj, excepto cuando se indique lo contrario.

En el caso de `padding` no tenemos las mismas limitaciones que tenemos con `margin` en relación a los elementos de bloque y línea

## Elementos de bloque

```CSS
/* Podemos colocar el Shorthand padding para dar relleno a todos los lados por igual */
padding: 100px;

/* Que sería lo mismo que hacer esto */
padding-top: 100px;
padding-right: 100px;
padding-bottom: 100px;
padding-left: 100px;

/* Pero si queremos tener diferentes medidas en menos lineas, nuevamente podemos usar el ShortHand padding */
padding: 50px 20px;

/* Con esto decimos que queremos 50px arriba y abajo, 20px derecha e izquierda  */
/* Si agregamos un valor más */
padding: 50px 20px 100px;

/* Tendríamos 50px arriba, 20px derecha e izquierda y 100px abajo*/
/* Con 4 valores */
padding: 50px 20px 100px 70px;

/* Con los 4 valores tenemos: 50px arriba, 20px derecha, 100px abajo y por último 70px izquierda */
```
## Elementos en línea

Con los elementos en línea esto funciona igual, en este caso no hay limitaciones

```CSS
padding: 100px;

/* Se lo puede resumir, porque esto es lo mismo que con los elementos de bloque */

padding-top: 100px;
padding-right: 100px;
padding-bottom: 100px;
padding-left: 100px;

/* Con los 4 valores tenemos: 50px arriba, 20px derecha, 100px abajo y por último 70px izquierda */
padding: 50px 20px 100px 70px;
```

## Cuando usar margin o paddings¿?

Esto ya depende de la situación, debemos preguntarnos que queremos hacer, si el objetivo es **separar** nuestra caja de los elementos que lo rodean, debemos utilizar `margin`, y si debemos aumentar el tamaño de la caja y separar los bordes del contenido, usaremos `padding`.

Veamos un ejemplo con un botón.

```HTML
    <div class="buttons">
      <button class="button">SOY UN BOTÓN</button>
    </div>
```
```CSS
.buttons{
  background-color: steelblue;
}
```
Y con esto que queremos hacer, lo priemro es darle más espacio a los bordes de la caja para que el boón no esté tan encerrado. Como queremos aumentar el tamaño de la caja lo que debemos hacer es:

```CSS
.buttons{
  background-color: steelblue;
  padding-top: 20px;
  padding-bottom: 20px;
}
```
Ahora queremos que el botón se separe un poco del borde. Intentaremos dejarlo más o menos por la mitad, existe una propiedad para hacer esto, pero ahora veremos cómo hacerlo con ``margin`` por fines didácticos.

Le daremos un `margin-left:`, porque yo quiero que esta caja se desplace, no quiero aumentar su tamaño.

```CSS
.button{
  margin-left: 130px;
}
```

Con esto está más o menos centrado el botón, ahora queremos que el botón tenga más espacio para "respirar", que los bordes no estén tán pegados al botón, por esto mismo lo que buscamos es aumentar el tamaño de la caja, por eso usaremos `padding` y se lo daremos en 2 valores porque no quiero la misma separación verticalmente que horizontalmente.

```CSS
.button{
  margin-left: 130px;
  padding: 25px 50px;
}
```

Con esto podemos tener más claro lo de utilizar `margin` o `padding` y saber cual es la propiedad que debemos utilizar.

UNo más, si por ejemplo queremos separar el botón de nuestro elemento en línea debemos utilizar `margin` para separar el contenido u no agrandar la caja con `padding`, porque seguirían juntos solo con el contenido más alejado.

```CSS
/* Agregando un margin para separar cajas */
.buttons{
  background-color: steelblue;
  padding-top: 20px;
  padding-bottom: 20px;
  margin-top: 30px;
}
```

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBoxModel/02_borde.md "Border") 
[Siguiente **&#129042;**](/teoria/teoriaBoxModel/04_margin.md "Margin")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")