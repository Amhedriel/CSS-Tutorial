# Sintaxis de CSS

La estructura completa de *selector* + *declaración* es llamada **regla**.

Veamos de qué consta dicha regla:

* [Selector](#selector "")
* [Propiedad](#propiedades "")
* [Valor](#valor-de-la-propiedad "")
* [Propiedad: Valor;](#valor-de-la-propiedad "")


## Selector

Es el elemento HTML al que le vamos a aplicar estilos. Esta selecciona el(los) elemento(s) a dar estilo, para dar estilo a un elemento diferente, simplemente cambiamos *selector* en una nueva **regla**.

Empezamos la regla con un ``selector`` abrimos y cerramos llaves ``{}`` y dentro es donde estarán las ``propiedades:`` que queremos cambiar seguido por el ``valor;`` del cambio deseado:

```CS
selector{
  propiedad: valor;
}
```
## Propiedades

Maneras en las cuales dar estilo a un ``elemento`` HTML. En CSS, seleccionas qué ``propiedad`` quieres afectar en tu regla.

No hay un límite de ``propiedades`` que podamos asignar a un ``elemento`` para conseguir el estilo que buscamos.

```CS
selector{
  propiedad: valor;
  propiedad1: valor;
  propiedad2: valor;
  propiedadN: valor;
}
```
## Valor de la propiedad

A la derecha de la ``propiedad``, después de los 2 puntos, tienes el **nuevo valor de la propiedad**, para elegir una de las muchas posibles apariencias para una ``propiedad`` determinada (existen muchos valores para todas las propiedades).

Con o visto hasta aquí podemos dar este ejemplo:

```CS
body{
  background-color: aquamarine;
}
```
Donde estamos **seleccionando** el elemento `<body></body>` de nuestro documento HTML y cambiando su ``propiedad`` predeterminada de `background-color:` que generalmente es blanco a un color `aquamarine;`

Que se puede observar con Live Server desde [aqui](/html/sintaxis.html "sintaxis,html").

## Propiedad: Valor;

A la combinación de ambos se le denomina como declaración y esta declaración como ` background-color: aquamarine;` especifica a cual de las ``propiedades`` del elemento quieres dar estilo.


Ahora bien, visto todo el tema de sintaxis y la terminología a la hora de sabemos nombrar a cada uno de los componentes.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/README.md "Menu principal") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/002_tiposDeSelectores.md "Selectores CSS")

---

[*Volver* **&ldca;**](/teoria/teoriaBasica/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")