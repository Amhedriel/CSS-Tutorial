# Prepos

[Prepos](https://prepros.io/ "Ir a Prepos") es un programam comletamente gratuito con la única limitación que si no lo pagamos cada cierto tiempo nos sale una recomendación de comprarlo, sin embargo el programa se lo puede usar de manera completa sin limitaciones.

Una vez descargado, lo instalamos, lo colocamos en modo oscuro si queremos eh incluso personalizarlo si es que se sabe algo de los settings que presenta. Pero, es necesario usar Prepos en 2022?, la verdad es que no, porque hay otras herramientas que lo hacen, pero son más complejas, depende de su disponibilidad de entorno, precio, pero Prepos es muy manejable y útil.

Ahora para utilizar Prepos vamos a coger nuestra carpeta de CSS, abrir el proyecto en VSCode, en este caso a modo de ejemplo utilizaremos la carpeta de nuestro tutorial: [prepos](/prepos "Ir a carpeta prepos"), en esta misma carpeta debemos tener nuestro index.html, carpeta styles y el archivo style.css dentro de dicha carpeta, utilizaremos esta carpeta como si fuera el proyecto principal. Debemos buscar esta carpeta **prepos** y la arrastramos dentro de la aplicación o lo abrimos desde la aplicación selecionando la carpeta del proyecto y se abrirá.

Una vez abierto el proyecto como tal y hacemos click en la carpeta donde tenemos nuestro .css se despliega el contenido y al hacer click tenemos una serie de opciones, en este punto debemos conocer:

* **Output File:** Que sería el resultado del CSS después de que lo pre-procese **"Prepors"**.

* **File Options** -> *Process Automatically:* Que debemos marcarlo.

* **Autoprefixer** -> *Prefix CSS*: debe estar marcado.

Una vez configurado dividiremos la pantalla en 2 para tener visión de Code y Prepos a la vez, en VSCode veremos que tiene un nuevo archivo en la carpeta `prepos.config` que obviamente no debemos tocar.

Ahora bien, abrimos nuestro ``style.css`` y lo editamos en Code.

```cs
body{
  background-color: lightcoral;
}
```
Guardamos y automáticamente guardará un archivo nuevo `style-dist.css`. Si le hacemos doble click veremos que tiene un aspecto muy similar pero en una única línea de código:

```CS
body{background-color:lightcoral}
```
Este código que sale aquí es el código procesado al que se le añadirán los prefijos y otras cosas, nosotros segiremos trabajando sobre el archivo ``style.css`` pero en el index.html en lugar de cargar ese archivo , lo cambiaremos y pediremos que nos muestre el archivo `style-dist.css`, Este archivo es unicamente para que lo interprete el navegador.

Veamos como funciona el tema de los prefijos, volvamos al navegador y entremos a la página oficial de Autoprefixer, para copiar el ejemplo que nos dán y ver si nos sale el mismo resultado que muestran, y si comparamos hay varias cosas que no nos muestra, porque por defecto nos muestra 2 versiones e intentaremos ir más atrás, **Settings**-> **CSS Tools** -> *Autoprefixer*, en la opción de *target Browaers* vamos a borrar todo lo que nos da, y le diremos a que navegadores queremos apuntar, colocaremos `defaults` Enter, hecho esto cerramos las ventanas emergentes, cerramos `style-dist.css` si estaba abierto en nuestro proyecto.

Con las modificacionesque hicimos ya podemos ver el resultadoqu esperábamos, recordemos que se actualizan continuamente, tanto como los navegadores como las tecnologias que insiden en ellos, asi que algunas cosas ya serán estandar y no aparecerán pero otras nuevas entrarán y se realizará el mismo proceso de conversión.

Mencionar que **Prepos** tiene un servidor de desarrollo que se encuentra en **Server** y clickear en *Open Preview* y nos mostrará un servidor de desarrollo que se recarga automáticamente. Y Prepos tendría más opciones que usar Live Server, por ejemplo Prepos tiene un cambio visual más leve con pequeñas animaciones, no son bruscon como Live Server.

---

[*Volver* **&ldca;**](/README.md "") 
[*Subir* **&#11165;**](# "Ir al título")