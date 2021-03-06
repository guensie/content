---
title: "Tutorial de Bootstrap: Aprende Bootstrap 4 en 10 minutos"
subtitle: "Después de decadas de lucha, la luz a llegado !! con este tutorial de Bootstrap, diseñar un sitio web va a ser pan comido.   

Es casi estupido, y tambien imposible pensar hacer un sitio web sin un framework de CSS como Bootstrap 4 ."

cover: "https://ucarecdn.com/4cc6fa0b-2530-4052-aa7e-8dac03788ac3/"
textColor: "white"
date: "2018-01-11"
tags: ["fale"]
---
 
## **¡Al fin, Bootstrap 4 a llegado!!**
***

Hay una luz al final del túnel y no es Chuck Norris con una linterna. ¡Finalmente alguien arregló CSS!  Es una librería hecha por [Mark Otto](https://twitter.com/mdo?lang=en) y [Jacob Thornton](https://twitter.com/fat) personas normales, programadores como tu y yo, y ¡lo hicieron genial!

Dos chicos mientras trabajaban en Twitter, estaban sufriendo los mismos problemas que nosotros con HTML y CSS. Hartos de esta situación (como nosotros), decidieron crear una **hoja base que puede ser importada en cualquier sitio web**. Esto hizo el trabajo de todos los desarrolladores front-end 4 veces más fácil.

![bootstrap 4](https://ucarecdn.com/335ed387-cbf9-4ffa-9529-1ccf2084e393/-/resize/300x/)

Además, Bootstrap te da una docena de elementos nuevos que vas a querer usar siempre y que actualmente no existen en CSS+HTML: Los componentes de Bootstrap.

## Layouts: Solucionado el Modelo de Cajas
***

Uno de los defectos en CSS, es la forma en que funcionan los layouts: trabajar con **float**,  **display** y **position** ¡es lo peor! Así es como Bootstrap lo soluciona:

# Ahora todo está dividido en Filas y Columnas

Los creadores de Bootstrap, replicaron el mismo concepto que tienen las `<tables>`, pero en vez de usar tablas usaron `<div>` (contenedores de cajas). Ellos no podían crear sus propias etiquetas en HTML, porque eso requiere una nueva versión de HTML e iba a hacer a Bootstrap incompatible con los navegadores actuales. Las tags debían ser las mismas - por eso decidieron anular el comportamiento que trae un `<div>` por defecto.

```html
Esto es una fila: <div class="row">
Esto es una columna: <div class"col–sm–x">
```
![bootstrap tutorial](https://ucarecdn.com/3884f515-dd7a-48f2-b238-9e2ec26de02d/-/resize/700x/)

Bootstrap ha dividido el ancho de la pantalla en  `12 slots` (ranuras) - cada una de ellas con el 8.33% del ancho total de la fila. El tamaño de una columna, puede estar entre 1 y 12 slots.

Por otro lado, las columnas fueron hechas para vivir dentro de las filas (como pasa entre `<td>` y `<tr>`),  siempre necesitas abrir una fila antes de abrir una columna.  Todas las columnas en una fila deben sumar un máximo de 12 ranuras.

![bootstrap tutorial](https://ucarecdn.com/1b7f5dc4-029a-475d-8bfd-fac1b739966c/-/resize/500x/)

## Nuestro primer Ejemplo de Diseño:
***

Tal cual como hicimos en el capítulo sobre diseños, vamos a crear una página con dos grandes secciones, una barra lateral a la derecha y un contenido principal a la izquierda:

<iframe width="100%" height="300" src="//jsfiddle.net/BreatheCode/th7uLrow/4/embedded/html,css,result/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>

<div align="right"><small><a href="//jsfiddle.net/BreatheCode/th7uLrow/4/embedded/html,css,result/">Click aquí para ver el demo en una ventana nueva</a></small></div>

## Bootstrap es 100% Sensible
***

Es muy fácil decidir como tu página web se verá en pantallas de diferente tamaño; cuando añades cada columna dentro de las filas, necesitas asignar una clase con el siguiente formato:

```html
<div class="col–md–x">
```

|**Col**   |**md**   |**x**
|:---------|:--------|:----|
|Significa que este elemento debe comportase como una columna de Bootstrap.   |Significa que estoy especificando solo para dispositivos con tamaño de pantalla "medium".   |Especifica cuantos slots quiero que abarque la columna (recuerda que puede abarcar max 12 slots por fila).   |

[[info]]
| :point_up:Bootstrap device sizes:   |Smartphones   |Big-phone/small-tablet   |Tablets   |Desktops   |Extra-large desktops   |
|:----------|:---------------|:-------------|:-----------|:------------|:---------|
| &nbsp;           |Nothing    |sm       |md       |lg      |xl        |

[[warning]]
| :point_up:Note: si no especificas el tamaño de pantalla (ej. usando 'sm', 'md', or 'xl'), el sitio web va a renderizar para teléfonos móbiles por defecto.

## Define Móvil, Tablet y Escritorio (Desktops) al mismo tiempo
***

Vamos a configurar el diseño (usando las clases de columnas xs, sm, md y lg) para estas dos filas en todos los dispositivos al mismo tiempo:

![bootstrap 4](https://ucarecdn.com/e15c594c-9b46-4c27-bf5a-a5bbb5ef952a/-/resize/1500x/)

```html{numberLines: true}
<!-- Apila las columnas en el móvil ocupando el ancho completo y el otro medio ancho --> 
<div class="row">
  <div class="col-12 col-md-8">.col-12 .col-md-8</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- Las columnas comienzan en un 50% de ancho en dispositivos móviles y alcanzan hasta un 33,3% de ancho en el Desktops --> 
<div class="row">
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- Las columnas son siempre del 50% de ancho, en dispositivos móviles y de Desktops --> 
<div class="row">
  <div class="col-6">.col-6</div>
  <div class="col-6">.col-6</div>
</div>
```

## Esqueleto Basico de Bootstrap 4
***

Ya sabemos sobre el esqueleto basico de HTML5 que todo sitio web necesita. Ahora solo debes agregar unas lineas en tu esqueleto para hacerlo "compatible con Bootstrap":

```html{numberLines: true}
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
  </body>
</html>
```

Recuerda, Bootstrap es solo una pagina de estilo, Es por eso que es muy simple agregarlo a tu sitio web. Utiliza el `<link>` tag para incluir los estilos, y oportunamente el uso de javascript `<script>` tag  para incluir los archivos de javascript de Bootstrap.

La funcionalidad de Javascript en Bootstrap requiere que sea incluido primero las librerias propias de jQuery y Javascript.  No necesitas saber sobre esto aún.   Solo incluye las librerias de JS usando el tag de script y después lo entenderás.

[[info]]
|:link: Here you can find some [great Bootstrap files to get you started.](https://getbootstrap.com/docs/4.0/getting-started/introduction/)

## Componentes de Bootstrap 4
***

HTML es súper básico, tiene pocas etiquetas - ya los sabíamos. Pero cuando revisas la web hoy en día, ves algo totalmente diferente… actualmente las páginas web tienen menús, iconos, barras de carga, etc. ¿Dónde están esas etiquetas? ¡Ninguna de ellas están definidas en HTML!

Todos los desarrolladores tienen que falsificar estos elementos adicionales cada vez que crean un sitio web, tienen que hacer todo desde cero y eso toma muchísimo tiempo.

Cuando importas un bootstrap en tu página web, tendrás un nuevo set de componentes a tu disposición. Esta es una pequeña parte de esos elementos:

![bootstrap 4](https://ucarecdn.com/8e9ff37a-28f7-4179-8f5d-9278ff7efd55/-/resize/800x/)


### Esto son los componentes más usado e importantes de Bootstrap:
***

#### **Barra de Navegacion o The NavBar**

Esto es tan popular que se encuentra en el 99% de los menús de todos los sitios web.  Normalmente contiene el logo de la compañia y una series de links - dependiendo de la logistica de negocio de la página. 

Aquí hay un ejemplo de como se ve un NavBar en un sitio web:

![bootstrap tutorial](https://ucarecdn.com/6351de1c-6d90-4502-8823-4b751981db9f/-/resize/1000x/)

[[info]]
| :link:[**Lee más sobre el "NavBar" aquí**](https://getbootstrap.com/docs/4.0/components/navbar/)

```html{numberLines: true}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="container">
                <a class="navbar-brand" href="#">Website Brand</a>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNavDropdown">
                    <ul class="navbar-nav ml-auto">
                        <li class="nav-item active">
                            <a class="nav-link" href="#">
                                <a class="btn btn-success">Create a new post</a>
                            </a>
                        </li>
                        <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                Settings
                            </a>
                            <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
                                <a class="dropdown-item" href="#">Action</a>
                                <a class="dropdown-item" href="#">Another action</a>
                                <a class="dropdown-item" href="#">Something else here</a>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
```

#### **The Card**

Esta es probablemente el componente de Bootstrap más usado, cada sitio web tiene unas cuantas "Card" porque es ideal para listar objeto de una forma bonita.  Algunos ejemplos del uso de "Card" pueden ser:

+ La sección de "equipo" de un sitio web donde listas los distintos empleados.
+ Típico muro de Pinterest.
+ Cualquier red social como Instagram, Facebook, twitter, etc.

Aquí hay un ejemplo de como puede verse un sitio web con "The Card":

![bootstrap 4](https://ucarecdn.com/39d36b52-330f-4ce9-beab-2004e325749c/-/resize/350x/)

[[info]]
| :link: [**Lee más sobre el "The Card" aquí**](https://getbootstrap.com/docs/4.0/components/card/)

```html{numberLines: true}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" src="..." alt="Card image cap">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```



#### **El Modal**

Todo el mundo odia el modal, es debido a que es super molesto, siempre preguntando si te quieres incribir a una revista! 🙂

Así es como se muestre un modal por defecto con Bootstrap.

![bootstrap 4](https://ucarecdn.com/6bcba673-a543-4bf1-a80b-083914b91bef/-/resize/400x/)

[[info]]
| :link:[**Lee más sobre el "Modal" aquí**](https://getbootstrap.com/docs/4.0/components/modal/)

```html{numberLines: true}
div class="modal" tabindex="-1" role="dialog">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>Modal body text goes here.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary">Save changes</button>
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
```


[[warning]]
| :point_up:Importante! El Modal necesita de Javascript para poder funcionar.  Recuerda incluir los archivos de Javascript que son necesarios en el típico esqueleto de Bootstrap: jQuery, Popper and Bootstrap.js

## Lo que realmente necesitas saber sobre Bootstrap
***

La documentación oficial de Bootstrap es increible!! No necesitamos copiar y pegar todos los post.  Por favor visita los siguientes sitios web y enfócate en leer estos temas:

+ [The grid system.](https://getbootstrap.com/docs/4.1/layout/grid/)
+ [Styling Forms.](https://getbootstrap.com/docs/4.1/components/forms/)
+ [List of components available to use on your website.](https://getbootstrap.com/docs/4.1/components/alerts/)
+ [Utilities or Helper classes:](https://getbootstrap.com/docs/4.1/utilities/borders/) Very useful and constantly used classes to do stuff like centering the text, centering a column or container, adding a background, etc.



## Gana RE2PECT.
***

El éxito no viene de la noche a la mañana.  Este es tu primer logro.  Dejame pregunterte, te sientes capaz de usar HTML, CSS, Layouts y Bootstrap?  No te mientas!

No más Lecciones sobre este tema - es momento de entregar.  Tu atención de enfocarse en el proyecto de clase.  Recuerda vivir bajo los valores de los desarrolladores. Calma.

<iframe src="https://www.youtube.com/embed/RqHNyyvfafE" frameborder="0" allowfullscreen></iframe>

<div align="right"><small><a href="https://www.youtube.com/embed/RqHNyyvfafE">Click here to open video in new window</a></small></div>




















