# UT5.1 Bootstrap

## Introducción a Bootstrap

```note
**Bootstrap** es un framework CSS (y JS) utilizado para el desarrollo de interfaces web de forma estandarizada para que se adapten a cualquier dispositivo.
```

Bootstrap se desarrolló inicialmente por Twitter en 2010, para estandarizar las herramientas de desarrollo de la compañía.

Inicialmente, se llamó Twitter *Blueprint* y, un poco más tarde, en 2011, se transformó en código abierto y su nombre cambió para Bootstrap. Desde entonces se ha ido actualizado continuamente y ya se encuentra por la **versión 5**, con la que trabajaremos.

Bootstrap combina CSS y JavaScript para estilizar los elementos de una página HTML y proporcionarle interactividad respetando el principio de diseño responsive en todo momento. 

La documentación está disponible en <https://getbootstrap.com/docs/5.3>

![](media/7d6f06c1b29b7b47b3e7fa85e79fac00.png)![](media/1dff958f3fd08966a66844bcf7684baa.jpeg)

Bootstrap sigue el concepto de **mobile first**. Esto significa que la preocupación del Framework es primero desarrollar una página que funcione perfectamente en dispositivos móviles y luego en el escritorio.

Bootstrap además está plentamente basado en **Flexbox** y *CSS3*.

Las funciones disponibles en Bootstrap ofrecen una experiencia rica al usuario. Además está plentamente basado en Flexbox y usa las tendencias de diseño del mercado.

Actualmente es el Framework frontend de CSS más usado en 2023 (más de un 25%).

Características de **Bootstrap 5**:

-   Mobile First
-   Basado en Flexbox
-   Sistema Grid responsive
-   Variedad de componentes propios: navbar, card, botones, formularios, etc
-   Tipografía receptiva (adaptable según el dispositivo)
-   Compatibilidad con Javascript nativo y con plugins adicionales.
-   Compatibilidad con Sass

## CDN

La manera más sencilla de comenzar con *Bootstrap 5* es utilizar un **CDN.** (*Content Delivery Network*), es decir, un servidor donde se alojan todos los archivos de Bootstrap.

Usaremos el CDN de jsDelivr, apuntando a la versión 5.3.0 de Boostrap. Agregaremos el siguiente código en nuestro esqueleto de la página HTML principal:


```html
   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" >
```
💡 Se puede cambiar de versión de la URL según las necesidades.

Para la parte de Javascript también se puede agregar la URL de un CND, pero desde Bootstrap 5 ya no es necesario para funcionalidades básicas.

Las ventajas de utilizar esta forma de cargar Bootstrap son:

-   Reducir la carga de los servidores propios (importante si utilizamos un hosting compartido con recursos limitados)
-   Facilita que Bootstap 5 quede en caché del navegador y se vuelva a cargar cada vez que se visita una web que lo utilice.

Recordemos que Bootstrap también es un framework que utiliza multitud de complementos de JavaScript para mejorar el comportamiento de los elementos en nuestra página. Además es plenamente compatible con Javascript nativo. 
Para la parte de Javascript también se puede agregar la URL de un CND, aunque desde Bootstrap 5 ya no es necesario para la mayoría de funciones básicas.

El código para JS deberá de añadirse al final de la página HTML, justo antes del cierre de la etiqueta body de la página:

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
```

## Cuadrícula (Grid)

Bootstrap incluye un potente sistema de rejillas (grid) para la construcción de diseños de todas las formas y tamaños.

Bootstrap utiliza un modelo de cuadrícula basado en dos tipos de contenedores y una rejilla de hasta **12 columnas**, basada en Flexbox, con varios niveles que resulta muy práctica, y que como veremos podemos alterar cuando nos resulte conveniente.

El sistema de cuadrícula utiliza <u>tres clases</u> CSS principales para crear el diseño necesario: **.container**, **.row** y **.col**. El contenedor cubre el diseño completo, luego las filas y luego las columnas.

![](media/bc2e59fb452aa03ae5cedbfb7b61ade4.png)

En el siguiente ejemplo se crea tres columnas de igual ancho en todos los dispositivos usando las clases anteriores. Esas columnas están centradas en la página con el **.container** principal. Debemos utilizar la clase **row** para indicar el comienzo de una fila. Dentro de la fila dispondremos tantos **div** como columnas tenga dicha fila.

```html
    <div class="container"> 
    <div class="row"> 
        <div class="col"> 
        Columna 
        </div> 
        <div class="col"> 
        Columna 
        </div> 
        <div class="col"> 
        Columna 
        </div> 
    </div>
```

![](media/dcf49a2808ff7e847513eef61ed72271.png)

Para indicar el tamaño de columna debemos utilizar la siguiente sintaxis:

    col-\#

El valor del **\#** será uno entre **1 y 12**. El restante del valor indicado será el que debamos de distribuir entre el resto de columnas (sumando 12). Si usáramos *col-auto* el tamaño se ajustaría respecto al contenido del elemento.

```html
    <div class="container"> 
    <div class="row"> 
        <div class="col-2"> 
        Columna-2 
        </div> 
        <div class="col-4"> 
        Columna-4
        </div> 
        <div class="col-6"> 
        Columna-6
        </div> 
    </div>
```

![](media/f0251ebb94bc2cd2b8111462300a4477.png)

### Breakpoints

El sistema de cuadrícula de Bootstrap puede a su vez adaptarse a seis **breakpoints** predeterminados basados en *media queries*:

![](media/breakpoints_bootstrap.png)

De esta manera el prefijo de clases cambiará a *col-{breakpoint}* tal y como se muestra en la siguiente tabla:

|                      |  **\<576px** | **sm** **≥576px** | **md** **≥768px** | **lg** **≥992px** | **xl** **≥1200px** | **xxl** **≥1400px** |
|----------------------|--------------|-------------------|-------------------|-------------------|--------------------|---------------------|
| Contenedor max-width | Por defecto  | 576px             | 768px             | 992px             | 1200px             | 1400px              |
| Prefijo de clase     | **.col-\#**  | **.col-sm-\#**    | **.col-md-\#**    | **.col-lg-\#**    | **.col-xl-\#**     | **.col-xxl-\#**     |
| \# de columnas       | 12           |                   |                   |                   |                    |                     |

![](media/2ce1b4a87101d252ec2f699e4d56f4dc.png)

Usando un solo conjunto de clases *.col-sm-\#,* se puede crear un sistema de cuadrícula básico que comience apilado (por defecto) siempre que sea menor que **sm** y tenga la siguiente distribución de dos filas a partir del breakpoint pequeño (sm).

```html
    <div class="container"> 
    <div class="row"> 
        <div class="col-sm-8">col-sm-8</div> 
        <div class="col-sm-4">col-sm-4</div> 
    </div> 
    <div class="row"> 
        <div class="col-sm">col-sm</div> 
        <div class="col-sm">col-sm</div> 
        <div class="col-sm">col-sm</div> 
    </div> 
    </div>
```

![](media/a8b552f86b32abd96d4aef75bd822730.png)

![](media/6020e7c34502d79529b3737167b08e7f.png)

Se pueden hacer combinaciones según diferentes tamaños (para sm y xl) y así obtener:

```html
    <div class="container"> 
      <div class="row"> 
       <div class="col-xl-3 col-sm-5 background">columna1<p> Lorem ipsum dolor sit amet,   consectetur adipiscing elit, sed do eiusmod tempor incididunt.</p></div> 
       <div class="col-xl-9 col-sm-7 background">columna2<p> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor.</p></div> 
       </div> 
    </div>
```

![](media/ced415d22cfcc46804995ee57e9d73b9.png)

![](media/c890926478f5a27ac6da167924844936.png)
![](media/71ab04427c00d1ea4243046471339027.png) 

### Contenedor

Ya hemos dicho que el contenedor es el elemento de diseño más básico en Bootstrap y es imprescindible para aplicar nuestro sistema de cuadrícula predeterminado. 

El contenedor puede personalizarse de la siguiente forma en su definición:

- *.container* por defecto establece un *max-width* en cada breakpoint responsive.
- *.container-fluid*  mantiene el ancho 100% de la ventana siempre.
- *.container-{breakpoint}* mantiene el ancho 100% hasta el breakpoint indicado.

```html
<div class="container-fluid"> 
<!-- Contenido fluído aquí --> 
</div>
```

 
### Columnas de fila

Para establecer un número columnas predeterminadas, se pueden utilizar las clases responsive **.row-cols-\#** y así establecer rápidamente la cantidad de columnas que mejor representen el contenido y diseño.

Mientras que las clases .col-\# normales se aplican a las columnas las de columnas de fila se establecen en el **.row** principal.

```html
    <div class="row row-cols-2"> 
     <div class="col">Columna</div> 
     <div class="col">Columna</div> 
     <div class="col">Columna</div> 
     <div class="col">Columna</div>
    </div> 
```

![](media/4ae22f2c5d837fca6e684cbd4311d7fe.png)

### Anidamientos

Para **anidar** el contenido con la cuadrícula predeterminada, se debe agregar un nuevo .row y un conjunto de columnas **.col-\#** dentro de una columna **col-\#** ya existente. Las filas anidadas deben incluir un conjunto de columnas que sumen 12 o menos, aunque no es obligatorio usar las 12 columnas disponibles en los anidamientos.

```html
    <div class="row"> 
    <div class="col-lg-6"> 
    <h1>Columna 2</h1> 
    <div class="row"> 
        <div class="col-lg-6"> <h2>Columna 2a</h2> </div> 
        <div class="col-lg-6"> <h2>Columna 2b</h2> </div> 
        </div> 
    </div>
```

![](media/91912598cdc31d4379f0ab62cab2862a.jpeg)

### Gutter

Los **gutters** son el padding horizontal entre las columnas, que se utilizan para espaciar y alinear de manera responsive el contenido en el sistema de cuadrícula de Bootstrap.

Las clases **.gx-\#** se pueden usar para controlar los anchos de los gutters horizontales.

```html
    <div class="container px-4"> 
    <div class="row gx-5"> 
    <div class="col"> 
    <div class="p-3 border bg-light">Padding de columna personalizado</div>
    </div>
    <div class="col"> 
    <div class="p-3 border bg-light">Padding de columna personalizado</div> 
    </div> 
    </div> 
    </div>
```

![](media/b151c102770f1a66c571fda1e6591dc9.png)

### Espacios en blanco (offset)

Para generar espacios en blanco (*offsets*) podemos utilizar la clase **.offset-\#**

Con dicha clase moveremos las columnas a la derecha tantas posiciones como el número indicado en la clase **.offset-\#**

```html
    <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
    </div>
```

![](media/3353c13dd5c87eeb3e676eef29adebcb.png)

### Margin y padding

Bootstrap también tiene clases para controlar el **margin** y el **padding** para no tener que recurrir a CSS, usando para ello el formato siguiente:

    {propiedad}{lados}-{tamaño}

Donde *propiedad* puede ser:
- m - para clases que establecen margin
- p - para clases que establecen padding

Y *lados* puede ser:
- t - para clases que establecen margin-top o padding-top
- b - para clases que establecen margin-bottom o padding-bottom
- x - para clases que establecen tanto *-left como *-right
- y - para clases que establecen tanto *-top como *-bottom
- (*blanco*) para clases que establecen un margin/padding en los 4 lados del elemento.

Por último, el *tamaño* puede variar entre 0 y 5.

### Ancho respecto los padres

Podemos utilizar también la clase \w-{25%|50%|75%|100%} para dar soporte al ancho respecto al contenedor padre.

Así de esta forma podemos tener:

```html
<div class="w-25 p-3" style="background-color: #eee;">Width 25%</div> 
<div class="w-50 p-3" style="background-color: #eee;">Width 50%</div> 
<div class="w-75 p-3" style="background-color: #eee;">Width 75%</div> 
<div class="w-100 p-3" style="background-color: #eee;">Width 100%</div> 
<div class="w-auto p-3" style="background-color: #eee;">Width auto</div>
```

![](media/4cb7ssfdfwe4rwe4rsdf6756fghe11.png)


### Ocultar elementos

Con la clase \d-{tamaño}-{none|block} podemos mostrar u ocultar elementos que indiquemos para ciertos tamaños.

| **Efecto** | **Clase**    | 
|-----------|---------------------|
|  Ocultar para todos   |  d-none | 
|  Ocultar solo para xs    |  d-none d-sm-block|flex | 
|  Ocultar solo para sm    |  d-sm-none d-md-block|flex | 
|  Ocultar solo para md    |  d-md-none d-lg-block|flex | 
|  Ocultar solo para lg    |  d-lg-none d-xl-block|flex | 
|  Ocultar solo para xl    |  d-xl-none d-xxl-block|flex | 
|  Visible para todos   |  d-block | 
|  Visible solo para xs   |  d-block d-sm-none | 
|  Visible solo para sm   |  d-none d-sm-block d-md-none | 
|  Visible solo para md   |  d-none d-md-block d-lg-none | 
|  Visible solo para lg   |  d-none d-lg-block d-xl-none | 


### Alineación: align-content

Bootstrap trae también la posibilidad de alinear las columnas en forma vertical con las regla de estilo que provee **Flexbox** CSS en el que está basado, el **align-content**.

![](media/b3681310a4804be679a16275e5eb5975.jpeg)
![](media/d0688bf8d1525eab6e76ced7e83ef334.jpeg)
![](media/c0487af2afb48885383387816f448f30.jpeg) 

### Alineación: justify-content

La propiedad **jusfify-content** funciona al igual que en Flexbox alineando en horizontal:

![](media/afd2cdf555224cb9fd3fb71efeaf5478.jpeg)

## Contenido

### La clase table

Con solo utilizar la clase **table** en nuestro código dentro del elemento **table** (\<table class="**table**"\>) podemos obtener lo siguiente directamente:

![](media/8a8b79f735b2caaad356b1d693af0f20.png)

![](media/e17b85a6c4c376389b65c805d344f05c.png)

Las reglas que define Bootstrap 5 permiten mostrar las filas separadas por una línea horizontal, los textos de la cabecera en negrita y la tabla se expandirá por defecto a todo su contenedor.

Pueden utilizarse numerosas clases auxiliares (table-primary, table-secondary, table-danger) para darle formato a color a las filas o columnas de una **table** y que pueden consultarse en la página de documentación de Bootstrap.

![](media/5be5694ebdf2cda878e9dd2e82b4fcea.png)

### Botones

Para crear botones en Bootstrap se utilizará **btn**, y alguna de las siguientes **clases** listadas a continuación con la siguiente apariencia:

![](media/e8c719bfcfb1828c19d9d693fa04bcf0.jpeg)

Utilizar este estándar ayuda a que los visitantes se sientan cómodos navegando ya que seguramente sus colores/formas les sean familiares de otros sitios/interfaces.

Disponemos de diferentes clases para definir el tamaño de los botones: *.btn-sm*, para botones pequeños y *.btn-lg*, para botones grandes. 

Por ejemplo:

```html
<button type="button" class="btn btn-sm">btn-sm</button> 
<button type="button" class="btn btn-lg">btn-lg</button>
```

Para que un botón aparezca **activado** o **desactivado** utilizamos las clases .active y .disabled. Se pueden usar para botones, inputs y enlaces.

```html
<button type="button" class="btn btn-lg btn-primary" disabled>Boton primario</button>
```

### Imágenes

Las imágenes en Bootstrap se hacen responsive con **.img-fluid**. Esto aplica un **max-width: 100%** y **height: auto** a la imagen para que se escale con el ancho de su elemento padre.

```html
    <img src="..." class="img-fluid" alt="...">
```

![](media/452f144515c107e2b8f7552176152d98.png)

Las siguientes clases se utilizan para personalizar la apariencia de **imágenes**:

![](media/f1c2bf257b685e4dbd6929f35eadb52c.jpeg)

```html
    <img src="..." class="rounded" alt="...">
    <img src="..." class="circle" alt="...">
    <img src="..." class="thumbnail" alt="...">
```

### Alertas

Las alertas están disponibles para cualquier longitud de texto. Para un estilo adecuado, se pueden usar una de las ocho clases contextuales existentes. Por ejemplo:

```html
    <div class="alert alert-primary" role="alert"> Una simple alerta primary </div> 
    <div class="alert alert-secondary" role="alert"> Una simple alerta secondary </div> 
    <div class="alert alert-success" role="alert"> Una simple alerta success </div> 
    <div class="alert alert-danger" role="alert"> Una simple alerta danger</div>
```

![](media/alerts_bootstrap.png)

### Navbar

Un **navbar** es una barra de navegación superior responsive con menús, submenús, y otros componentes, como una barra de búsqueda entre otros, y que tiene las siguientes características:
- La barra de navegación es <u>adaptable</u> y fluida de forma predeterminada, lo que significa que se amplía o reduce en función de la anchura del viewport.
- Las navbars requieren un envoltorio *\.navbar* con las clases *\.navbar-expand{-sm|-md|-lg|-xl}*, que determinan cuándo se colapsa la barra en un sólo botón.
- Existen diversas clases para darle color a un navbar como *.bg-light* o *.bg-dark*.

![](media/3242365346345120978978.png)

Podemos crear una barra <u>estándar</u> con:

    \<nav class="navbar .navbar-expand{tamaño}">

Para agregar **enlaces** dentro de la barra de navegación, usar el elementos *\<ul>* con la clase *class="navbar-nav"*. Luego agrega elementos *\<li>* con una clase *.nav-item* seguido de un elemento *\<a>* con una clase *.nav-link*:

```html
<nav class="navbar navbar-expand-sm bg-light"> 
<div class="container-fluid"> 
<ul class="navbar-nav"> 
<li class="nav-item"> <a class="nav-link" href="#">Link 1</a> </li> 
<li class="nav-item"> <a class="nav-link" href="#">Link 2</a> </li> 
<li class="nav-item"> <a class="nav-link" href="#">Link 3</a> </li> 
</ul> 
</div>
</nav>
```

![](media/navbar_bootstrap1.png)

Si eliminamos el *navbar-expand* tendremos un menú de navegación siempre en vertical:

```html
<nav class="navbar bg-light"> 
<div class="container-fluid"> 
<ul class="navbar-nav"> 
<li class="nav-item"> <a class="nav-link" href="#">Link 1</a> </li> 
<li class="nav-item"> <a class="nav-link" href="#">Link 2</a> </li> 
<li class="nav-item"> <a class="nav-link" href="#">Link 3</a> </li> 
</ul> 
</div>
</nav>
```
![](media/navbar_bootstrap2.png)


Para crear **submenús desplegables** dentro de un elemento de la barra de navegación indicaremos que el elemento es dropdown y dentro anidaremos un elemento ul con la clase dropdown-menú y dentro sus respectivos *\<li>* con sus respectivos enlaces *\<a>*.

```html
<nav class="navbar navbar-expand-sm bg-dark navbar-dark"> 
<div class="container-fluid"> 
    <div class="collapse navbar-collapse" id="collapsibleNavbar"> 
    <ul class="navbar-nav"> 
    <li class="nav-item"> <a class="nav-link" href="#">Enlace</a> </li> 
    <li class="nav-item dropdown"> <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown">Desplegable</a> 
    <ul class="dropdown-menu"> 
        <li><a class="dropdown-item" href="#">Subenlace1</a></li> 
        <li><a class="dropdown-item" href="#">Subenlace2</a></li> 
    </ul> 
    </li> 
</ul> 
</div> 
</div> 
<nav>
```

![](media/navbar_bootstrap3.png)


## Formularios

Bootstrap aplica estilos a los elementos de tipo formulario para convertirlos en elementos responsive, mejorando su apariencia y permitiendo crear diferentes alineaciones como en el resto de elementos de Bootstrap ya conocidos:
- **Controles de Formulario**: Bootstrap estiliza las entradas de texto y áreas de texto con soporte para múltiples estados.
- **Select**: Se mejoran los elementos select predeterminados del navegador con una apariencia inicial personalizada.
- **Checks y radio buttons**: Utiliza botones de radio y checks personalizados para seleccionar opciones de entrada.
- **Rangos**: Reemplaza las entradas de rango predeterminadas del navegador.
- **Etiquetas flotantes**: Diseñadas para flotar sobre los campos de entrada.
- **Layout**: Permite utilizar cuadrículas complejas con los formularios.
- **Validaciones**: Permite validar formularios con estilos y comportamientos de validación nativos o personalizados.

Bootstrap aplica estilos a los elementos de tipo formulario para convertirlos en elementos responsive, mejorando su apariencia y permitiendo crear diferentes alineaciones como en el resto de elementos de Bootstrap ya vistos. 

Básicamente, la estructura general de un formulario sería como la siguiente:
- Usar *label* for para describir cada control de formulario (para la accesibilidad)
- No olvidar utilizar el atributo *type* para cada uno de los elementos *input* del formulario (por ejemplo, *email* para las direcciones de correo electrónico o *number* para información numérica)


```html
<form> 
<div class="mb-3"> 
    <label for="exampleInputEmail1" class="form-label">Correo</label> 
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Introduzca correo"> 
    <label for="inputPassword5" class="form-label">Contraseña</label> 
    <input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock"> 
    <div id="passwordHelpBlock" class="form-text"> Tu contraseña debe tener entre 8 y 20 caracteres, conteniendo letras y números.
</div> 
</form>
```

![](media/navbar_bootstrap4.png)

### Menús select

Los menús de selección se definen mediante la etiqueta *\<select>* y solo necesitan la clase personalizada *form-select* para activar los estilos de Bootstrap. Los estilos están limitados a la apariencia de *\<select>* y no pueden modificar los *\<option>* debido a las limitaciones del navegador.

```html
<select class="form-select"> 
<option selected>Abre este menú select</option> 
<option value="1">Uno</option> 
<option value="2">Dos</option> 
<option value="3">Tres</option> 
</select>
```

![](media/select_bootstrap.png)

### Checks y radios

Los checks y radio buttons predeterminados del navegador se reemplazan con la ayuda de la clase *\.form-check*, una serie de clases para ambos tipos de entrada que mejoran el diseño y el comportamiento de sus respectivos elementos HTML.

```html
<div class="form-check"> 
    <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
    <label class="form-check-label" for="flexCheckDefault"> Casilla de verificación por defecto </label> 
    </div> 
    <div class="form-check"> 
    <input class="form-check-input" type="checkbox" value="" id="flexCheckChecked" checked> 
    <label class="form-check-label" for="flexCheckChecked"> Casilla de verificación marcada </label> 
    </div> 
    <div class="form-check"> 
    <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1"> 
    <label class="form-check-label" for="flexRadioDefault1"> Radio por defecto </label>
    </div>
    <div class="form-check"> 
    <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2" checked> 
    <label class="form-check-label" for="flexRadioDefault2"> Radio marcado por defecto </label> 
</div> 
```

![](media/checkradios_bootstrap.png)

### Validaciones

La validación de formularios puede hacerse de forma estándar mediante el propio **HTML5**. Esto se realiza mediante el uso de atributos de validación en los elementos del formulario. Para ello podremos utilizar en los campos las siguientes propiedades:
- **required**: Especifica si un campo de formulario debe completarse antes de que se pueda enviar el formulario.
- **minlength** y **maxlength**: Especifican la longitud mínima y máxima de los datos de texto 
- **min** y **max** : Valores mínimo y máximo de los tipos de entrada numéricos.
- **type**: Especifica si los datos deben ser un número, una dirección de correo electrónico o algún otro tipo de preajuste específico.
- **pattern**: Especifica una expresión regular que define un patrón que los datos que se introduzcan deben seguir.

La validación de formularios HTML puede aplicarse también a través de las pseudoclases de CSS *:invalid* y *:valid*, aunque para ello necesitaremos código Javascript (lo veremos más adelante). Se aplica a los elementos *\<input>*, *\<select>* y *\<textarea>*. Para los mensajes de feedback se puede combinar como *valid-feedback* o *invalid-feedback*.

```html
<form class="row g-3 needs-validation" novalidate> 
<div class="col-md-6"> 
    <label for="validationCustom03" class="form-label">Ciudad</label> 
    <input type="text" class="form-control" id="validationCustom03" required> 
    <div class="invalid-feedback"> Proporciona una ciudad válida. </div> 
</div> 
<div class="col-md-3"> 
    <label for="validationCustom05" class="form-label">Código postal</label> 
    <input type="text" class="form-control" id="validationCustom05" required>
    <div class="invalid-feedback"> Proporciona un código postal válido. </div> 
</div>
<div class="col-12"> <div class="form-check"> 
    <input class="form-check-input" type="checkbox" value="" id="invalidCheck" required> 
    <label class="form-check-label" for="invalidCheck"> Acepta los términos y condiciones </label> 
    <div class="invalid-feedback"> Debe estar de acuerdo antes de enviar. </div> 
</div> </div> 
<div class="col-12"> 
    <button class="btn btn-primary" type="submit">Enviar formulario</button>
</div> 
</form>
```

![](media/navbar_bootstrap5.png)


### Procesar los datos del formulario

Para procesar los datos enviados por el formulario, necesitarás emplear un lenguaje de programación del lado del **servidor**(backend), como JavaScript, PHP, o cualquier otro de tu elección. El código de procesamiento del formulario se colocará en el atributo action del elemento *\<form>*.
