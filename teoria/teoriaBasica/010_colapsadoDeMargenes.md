# Colapso de Márgenes

Hablemos sobre el colapsado de márgenes, que es un fallo de CSS y al principio ocasiona muchos problemas.

```HTML
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Colapsado de Márgenes</title>
  <link rel="stylesheet" href="/styles/010colapsomargenes.css">
</head>
<body>
  <header class="header"></header>
  <div class="box-1"></div>
  <div class="box-2"></div>  
</body>
</html>
```
```CSS
*{
  box-sizing: border-box;
}
body{
  background-color: #333;
  color: #fff;
  margin: 0;
}

.header{
  background-color:cyan;
  height: 100px;
  margin-bottom:20px;
}

.box-1,
.box-2{
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 20px;
  padding: 15px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
}
```

Vamos a hacer una prueba para ver cual es el problema de colapsado de márgenes, veremos como se comportan las cajas y al ``box-2`` vamos a darle un:

```CSS
.box-2{
  margin-top: 20px;
}
```
Recordemos que tiene un `margin-bottom: 20px;` la separación de las dos cajas es de 20px, por lo que esperariamos sumar 40px, sin embargo no ha cambiado absolutamente nada, inspeccionemos con F12

Si vemos `.box-1` vemos que el margen termina justo donde empieza el otro.

En el ``.box-2`` el margen termina al final de la otra caja.

Este problema siempre se tuvo en CSS, es que los márgenes verticales colapsan.

## Márgenes verticales colapsan

Que si nosotros tenemos un ``margin-botton`` para un elemento y un ``margin-top`` para otro y si sus márgenes se encuentran, se solapan, si le ponemos un `margin-top: 30px;` el margen solo aumentaría 10px, porque ya teníamos uno de 20px, o sea, se solapan los de 20 y el sobrante equivale a 10px realmente, esto es un problema que no tiene solución, la única solucion que encontramos los desarrolladores es darle `margin-botton` a los elementos e ir bajando el resto de elementos, es decir: si nosotros queremos distancia de 30px haríamos:


```CSS
.box-1,
.box-2{
  margin-left: auto;
  margin-right: auto;
  /* Sacar este margin */
  /* margin-bottom: 20px; */
  padding: 15px;
  background-color: lightcyan;
  width: 300px;
  height: 300px;
}
 /* Y agregar este en lugar del margin-bottom: 20px; */
.box-1{
  margin-bottom: 30px;
}
```
Entonces es muy recomendable que siempre vayamos empujando los elementos hacia abajo con `margin-bottom:` en caso de querer separarlo.

### **NOTA**

No usar `margin-bottom:` y `margin-top:`, porque los márgenes no se aplican como quisiéramos, esto solo pasa en margenes verticales no en horizontales.

## Padres e Hijos

Y también tenenmos otro problema sobre padres eh hijos.

```html
  <header class="header">
    <h1 class="title">Colapsado de márgenens</h1>
  </header>
```
Ni bien colocamos este título, el `header` baja, esto sucede con el colapsado de márgenes entre padres e hijos, esto realmente es culpa por el ``margin`` por defecto del `<h1></h1>`, si al ``title`` le damos un ``margin: 0;`` se "soluciona" entre comillas, lo que hemos hecho a sido quitarle los márgenes al título.

```CSS
.title{
  margin: 0;
  margin-top: 50px;
}
```
Si le damos este `margin-top: 50px` lo lógico sería que bajara del `header` y este se quedara pegado arriba, pero esto no es lo que pasa.

Parra arreglarlo tenemos 3 trucos distintos

1. Si le damos al contenedor un ``overflow: hidden;`` solucionaría el problema. Esto arregla el colapsado de padres e hijos.

2. Si le damos un ``padding-top:`` da igual la cantidad que se le asigne `` 0,1px;`` y esto también soluciona el problema, lo que pasa es que stamos agregando un espacio entre la parte superior de la caja y el margen que se está colapsando, con esto se soluciona.

3. Añadiendo un `border-top: 1px solid cyan;`para que no se note, esto también soluciona el problema.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/009_overflow.md "Overflow") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/011_display.md "Display")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")