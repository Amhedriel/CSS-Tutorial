# Fundamentos de CSS

* [¿Cómo Funciona?](#¿cómo-funciona-css)
* [Cascada](#cascada)

## **¿Cómo funciona CSS?**

A grandes rasgos con algo llamado:

* Especificidad -> Establece cómo de específico es un selector para saber que estilo aplicar.

El cálculo se realiza con la siguiente fórmula:

Aquí un ejemplo de las formas que tenemos para seleccionar el `<h1></h1>` CSS
~~~CS
// h1 cambiando el background-color:
h1{
  background-color: red;
}
// La clase title
.tittle{
  background-color: blue;
}
// id title
#title{
  background-color: green;
}
// h1 con la clase title
h1.tittle{
  background-color: yellow;
}
// h1 con la id title
h1#title{
  background-color: teal;
}
// h1 con la clase title e id title
h1.tittle#title{
  background-color: tomato;
}
~~~

Y modificaremos este HTML
~~~html
<!DOCTYPE html>
<html lang="zxx">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fundamentos de CSS</title>
  <link rel="stylesheet" href="/styles/004especificidad">
</head>
<body>
  <h1 id="title" class="title">Fundamentos de CSS</h1>
</body>
</html>
~~~
Ahora bien veremosque todo va a dar estilos a h1, pero evidentemente solo uno de ellos prevalecerá.

Veremos que la página tiene el color tomato
~~~CS
h1.title#title{
  background-color: tomato;
}
~~~

Lo que significa que esta es la regla ganadora, aunque decimos que es en Cascada CSS tiene sus selectores prioritarios y aún colocando esta regla al principio de todo, seguirá siendo la predominante por su especificidad.

La fórmula que sigue el navegador es sumar su valor de especificidad:

  * Etiquetas y pseudoelementos 001
  * Clases, atributos y pseudoclases 010
  * Id 100
  * Estilos en línea 1000
  * !important ***gana a todo***

Estos valores se pueden representar con comas, que es como lo representa la W3C y Visual Studio.
Si nos posicionamos sobre un elemento con el puntro del mouse podremos la especificidad del selector.
~~~CS
h1.title#title{
  background-color: tomato;
}
~~~
Esta regla suna por: Una etiqueta h1, si lo vemos en la tabla representa uno/1, una clase que sería 010 y un id que es 100, por lo tanto la especifidad de este selector es `(1.1.1)` y ya está. Al no manejar bien esta tabla puede causar problemas con los estilos, lo que causa el uso de mala praxis como:

~~~CS
.tittle{
  background-color: blue !important;
}
~~~

En teoria este `!important` le gana a todo en especifidad, pero no estoy tan seguro.

Se recomienda siempre usar clases para CSS.

## Cascada

La cascada funciona siempre que la especifidad sobre el ``elemento`` sea la misma:

~~~cs
.title{
  background-color: blue;
}

.title{
  background-color: green;
}

.title{
  background-color: red;
}

~~~

Aqui si funcionará la cascada, debido a que la especifidad sobre el ``elemento`` es la misma.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/003.1_selectoresPseudoClases.md "Dar formato según el estado") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/005_herenciaEnCSS.md "Herencia")

---

[*Volver* **&ldca;**](/teoria/teoriaBasica/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")