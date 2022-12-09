# Position

La propiedad ´position´ nos permite posicionar los elementos. Hay algunos conceptos que debemos conocer para entender `position`.

- **Flujo de Renderizado** Por norma general, los elementos se dibujan de izquierda a derecha y de arriba hacia abajo. El punto 0,0 de los elementos, por norma general, es la esquina superior izquierda.

- **Espacio Reservado** Es el espacio que tiene un elemento asignado en el navegador. Cuando nosotros creamos un elemento HTML da igual el que sea siempre habrá un espacio que está ocupando ese elemento, y ese es el espacio que le reserva el navegador a ese elemento. Vimos anteriormente que ese espacio se podía modificar con `width height` con ``margin`` para aumentar ese espacio reservado, pero al final eso es un espacio que el navegador asigna para que ningún otro elemento entre dentro de ese espacio reservado.

- **Elemento Posicionado** Esto significa que el elemento tiene la propiedad `position` con un valor distinto de **"static"**, que es el valor que tiene esta propiedad por defecto. Cuando modificamos `position` y le ponemos cualquier otro valor que no sea `static` decimos que un elemento está posicionado porque estamos habilitando la opción de poder mover/posicionar ese elemento en cualquiera de los 3 ejes.

- **Stackin Context** Contexto de apilamiento. Es el orden en el que se apilarán las cajas que se superponen dentro del mismo contenedor. Este es muy importante y tendrá su apartado propio.

## Agregando `position` a un elemento

Al posicionar un elemento se habilitan 5 propiedades que podemos utilizar para mover los elementos en los 3 ejes.

- **`top`** El elemento se moverá desde la parte **superior** la distancia que le indiquemos.

- **`rigth`** El elemento se moverá desde la parte **derecha** la distancia que le indiquemos.

- **`bottom`** El elemento se moverá desde la parte **inferior** la distancia que le indiquemos.

- **`left`** El elemento se moverá desde la parte **izquierda** la distancia que le indiquemos.

- **`z-index`** Nos permite mover el elemento en el contexto de apilamiento **(eje Z)**, sería como la profundidad   de ese elemento, supongamos que son cajas en 3D, la caja que este en frente la determina el `z-index`

***NOTA*** Si a un elemento le declaramos la propiedad ``top`` y/o `left`, las propiedades ``bottom`` y/o `right` no funcionarán. Este caso se da cuando lads propiedades afectan al mismo eje, es decir si el navegador tiene que elegir a hacer caso a ``top`` o ``bottom``, va a hacer caso a `top` y a ``bottom`` lo va a ignorar completamente, pasa lo mismo con `left` y `right`.

Los posibles valores que le podemos dar a `position` son:

- **`static`** Es el valor que tiene por defecto un elemento, con este valor el elemento **NO ESTÁ POSICIONADO** y por lo cual no podemos moverlo.

- **`relative`** El elemento mantendrá su posición y medidas en el flujo de renderizado y mantendrá su espacio reservado. Si lo movemos lo hará usando su posición en el html como punto de referencia.

- **`absolute`** El elemento perderíasus medidas y su espacio reservado. Si lo movemos usará el elemento padre posicionado como referencia. Si no tiene ninguno, usará el elemento html de referencia.

- **`fixed`** El elemento perderá sus medidas y su espacio reservado. Si lo movemos utilizará el elemento html de referencia, y además se quedará fijo en esa posición aunque hagamos `scroll`.

- **`sticky`** Es una mezcla de ``position: relative`` y `fixed`. Con este tipo de posicionamiento los valores `top`, `left`, `bottom` y `right` no sirven para mover el elemento, si no para indicarle en que punto pasará a tener un comportamiento de posicionamiento `fixed`, hasta llegar a ese punto se comportará como si tuviera `relative`.

---

[**&#11176;** *Anterior* &#11007;](/teoria/teoriaBasica/014_boxShadow.md "Sombras") 
[Siguiente **&#129042;**](/teoria/teoriaBasica/015.1_positionRelative.md "Posición relativa")

---

[*Volver* **&ldca;**](/teoria/README.md "Menu principal") 
[*Subir* **&#11165;**](# "Ir al título")