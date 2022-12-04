# Prefijos Propietarios

Al principio de este tutorial vimos que CSS funcionaba en módulos independientes, esto permitia que cada módulo pudiera crecer sin depender del resto, eso lo vimos con respecto al funcionamiento interno de CSS, tenemos el otro lado, que es el tema de los navegadores que da igual cuanto avance CSS si los navegadores no implementan estas mejoras, aquí es donde entran el tema de los **prefijos propietarios**, esto significa que cuando una propiedad CSS se convierte en un estandar los navegadores necesitan implementarla, si esta propiedad ya es recomendación y entra a ser parte de CSS los **prefijos** ya no hacen falta, pero hasta que sea una propiedad como tal, necesitamos colocar ciertos **prefijos** para que los navegadores sean capaces de interpretarlas.

## Autoprefixer CSS

Autoprefixer lo que hace es añadir esos **prefijos** por nosotros, no tiene sentido que nos aprendamos los **prefijos** que se deben poner y mucho menos ponerlos a mano, porque cuando no hagan falta tendríamos que ir a nuestro proyecto y eliminarlos todos, para eso existe autoprefixer:

```CS
// Veremos este ejemplo con este bloque de código que aún no estaban implementados en los navegadores

.example{
  display: grid;
  transition: all .5s;
  user-select: none;
  background: linear-gradient(to bottom, white, black);
}

```
Pero en el resultado veremos que `display` muestra:

```CSS
/* Veremos que en display nos aparece -ms-grid; el prefijo -ms
 quiere decir que estará optimizado para Microsoft Sistems */
.example{
  display: -ms-grid;
  display: grid;
   /* tenemos -webkit-transition: all .5s; -webkit es por el tema de Chrome */
  -webkit-transition: all .5s;
   /* Y -o-transition: all .5s; y -o es para el navegador Opera de IOs */
  -o-transition: all .5s;
  transition: all .5s;
  user-select: none;
   /* -moz es para Mozilla Fire Fox */
  -moz-user-select: none;
  ...
}
```

Entonces, gracia a estos prefijos podemos implementar estas mejoras y que el navegador sea capáz de interpretarlo, para que todo esto se nos escriba autpmáticamente no tenemos que ir a **Autoprefixer** y pegar nuestro código, lo que haremos es instalar un programa que se encarga de eso por nosotros.

En este caso usaremos elñ programa llamado [Prepos](/teoria/herramientasRecursos/Prepos.md "Ir a Preopos.md 'Herramientas/Recursos'").
