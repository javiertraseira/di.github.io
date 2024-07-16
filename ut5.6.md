# UT5.6 Conexión mediante APIS

## Introducción a las API

```note
Una **API** (*Application Programming Interfaces*) es un conjunto de definiciones y protocolos que se utiliza para desarrollar e integrar el software de las aplicaciones, permitiendo la comunicación entre dos aplicaciones de software a través de un conjunto de reglas definidas generalmente en su documentación.
```

Una API es por tanto un intermediario entre dos sistemas, que permite que una aplicación se comunique con otra y pida datos o acciones específicas.

Las API son ampliamente utilizadas en la industria de desarrollo de software. La API establece cómo un módulo de un software se comunica o interactúa con otro para cumplir una o muchas funciones. Todo dependiendo de las aplicaciones que las vayan a utilizar, y de los permisos que les de el propietario de la API a los desarrolladores de terceros.

![](media/2c580af36445c4c17ffbc9c6187619b5.jpeg)

Ejemplos de APIs conocidas:

![](media/64e2268262f62356dfd38ac0157d2d3a.png)![](media/43acd7462efc197e5d20a86c0ca8828f.jpeg)![](media/70a010c5ecfab42c3e95254334a366bc.png)![](media/b4445029eed8e65c87cade3554bdf9a1.png)![](media/b5abc54c640a0db69278fbc53903438e.png)![](media/3d49939028957c3ada639cda00701115.png)

![](media/cf70ccb4d030c69e64eaa0d9493560b6.jpeg)![](media/11e522ddc51f678b890383add4aab0fa.png)

![](media/e5349a18d269fabec5b7d5a124a0eea0.png)![](media/36a41b599e070dd054ce80400a5a80dc.png)

![](media/0dfb3dd9ba1996bfe6e704a57b58f22d.jpeg)

## API REST

En la actualidad la mayoría de **APIs** son de tipo **RESTful.**

```note
**REST** (Representational State Transfer) es una interfaz para conectar varios sistemas basándose en el protocolo HTTP y que sirve para obtener o generar datos y operaciones.
```

Un **protocolo** es un conjunto de reglas que determina qué mensajes se pueden intercambiar y qué mensajes son respuestas apropiadas a otros.

**HTTP** es el protocolo que permite enviar documentos de un lado a otro en la web. Los datos en envían o se devuelven en un formato conocidos, como son el **XML** o **JSON**.

![](media/1a8448d016d17172b2642ecdb5437768.png)

### API no RESTful

Existen otras API no RESTful que utilizan convenciones más complejas, por encima de HTTP y que se apoyan en lenguajes enteros basados en *XML* como **SOAP**.

-  Si tuviésemos que hacer una analogía podríamos decir que **SOAP** sería como enviar un sobre en el que sería necesario mayor ancho de banda y trabajo adicional de tratamiento para preparar el sobre antes de enviarlo y luego al abrirlo en destino.
-  En el caso de **REST** sería como si mandaríamos directamente una postal sin más.

![SOAP](media/f6f2f83affb740bc9ca14ab74c322e38.jpeg)![REST](media/89f70ae2cf17f7f08d666a0549697b8f.jpeg)

### Operaciones

Las **API REST** se apoyan como hemos visto en el protocolo **HTTP**.

Hay diferentes tipos de **REQUEST** u <u>operaciones</u> que una API REST puede manejar, y estos son los más utilizados:

| **Request** | **Descripción**                                                                                       |
|-------------|-------------------------------------------------------------------------------------------------------|
| GET         | Para devolver datos del servidor; un listado o recurso concreto.                                      |
| POST        | Para agrega nuevos datos en el servidor. A menudo, este tipo se usa para registrar o cargar archivos. |
| PUT/PATCH   | Para actualizar datos ya existentes en el servidor.                                                   |
| DELETE      | No autorizado                                                                                         |

![](media/43c8a0c1bb8e96fdc006eca47ae6e1f9.png)

Las API tienen un conjunto predefinido de puntos finales: direcciones únicas dentro de la **URL** del host, responsables de su funcionalidad.

Todas las API tienen una **documentación** pública donde se explica todos los puntos finales, tipos de valores devueltos, etc.

### Propiedades

Propiedades API REST:

-   Todo es un **recurso** y debe tener un identificador único (llamado **URL**)
-   Al recurso deben de aplicársele una **operación** específica permitida.
-   Los datos de la API estarán representados por un formato (*XML*, *JSON*, etc.)
-   La API devolverá un estado o **código de respuesta**.

![](media/a6b74076d9b5ea8bd00a8837680fe80a.jpeg)

### Documentación API

![](media/44f26294ed3c483ad865653c060013ce.png)![](media/50da6cc8a5de0381868fc1df3d414005.png)

[https://petstore.swagger.io](https://petstore.swagger.io/)

### Códigos de respuesta HTTP

Al solicitar un servicio de una API REST, esta responderá con **códigos de respuesta:**

-   Los códigos de **100-199** indican códigos **informativos**
-   Todos aquellos códigos de **200-299** indican códigos de respuesta **válidos.**
-   Los códigos que comiencen por **400-499** son códigos que indican **error** del cliente.
-   Los códigos que comiencen por **500-599** son códigos que indican **error** del servidor.

| **Código** | **Descripción**                         |
|------------|-----------------------------------------|
| **200**    | Ok                                      |
| 201        | Confirmar resultado petición PUT o POST |
| 400        | Solicitud incorrecta                    |
| 401        | No autorizado                           |
| 403        | Prohibido                               |
| **404**    | No encontrado                           |
| 408        | Tiempo de espera de la solicitud        |
| 500        | Error interno del servidor              |
| 503        | Servicio no disponible                  |


## APIs en Javascript

### Recuperar datos por fetch

Las APIs interactúan con el código usando uno o más objetos JavaScript, que sirven como contenedores para los datos que usa la API (contenidos en las propiedades del objeto), y la funcionalidad que la API provee (contenida en los métodos del objeto).

La primera forma de obtener dichos datos, y la más sencilla, es utilizando *fetch*, que es una nueva implementación de Javascript para ello. 
El único parámetro requerido de *fetch()* es una url. El método por defecto en este caso es **GET**.

```javascript
fetch('http://example.com/movies.json') 
```

### Enviar datos por fetch

El segundo parámetro de *fetch* es opcional, y recibe parámetros extras acerca del tipo de petición que vamos hacer, si queremos enviar datos, bajo qué tipo va a ir o si se va a enviar algún tipo de headers.

El método **POST** se utiliza para enviar datos al servidor y crear un nuevo recurso.

```javascript
fetch(url, { 
method: 'POST’,
body: JSON.stringify({ 
	id:1, 
	name: "Taylor", 
	surname: "Swift" 
	}), 
headers:{ 
	'Content-Type': 'application/json’ 
	} 
})
```

###  Solicitudes XMLHttpRequest 

Para recuperar datos de una API en JavaScript de forma clásica se ha utilizado siempre *XMLHttpRequest*, que es un estándar de la W3C y basado en AJAX. AJAX es una tecnología que hace las páginas dinámicas sin necesidad de recargarlas.

```javascript
var xhttp = new XMLHttpRequest(); // Crear un nuevo XMLHttpRequest 

xhttp.onreadystatechange = function() 
{ // Si nada da error
 if (this.readyState == 4 && this.status == 200) { 	
  // La respuesta viene en formato texto, hay que hacer un run parse
  console.log(JSON.parse(this.responseText)); } 
}; 
// Endpoint de la API y método que se va a usar para llamar 
xhttp.open("GET", "https://pokeapi.co/api/v2/pokemon", true);
xhttp.setRequestHeader("Content-type", "application/json"); 
// Para mandar parámetros a la API, podríamos hacerlo desde el método send()
xhttp.send(null); 
```

###  Solicitudes mediante Axios 

Tanto *XMLHttpRequest* como *fetch* son nativas de JavaScript, pero *Axios* es una librería externa que tendremos que importar en nuestro proyecto antes de usarla.

Axios tiene algunas ventajas adicionales como el parsear automáticamente las respuestas JSON y el poder usar tokens.

###  Conversión de los datos

Para la conversión de los datos en *JSON* (salvo en Axios) se puede usar cualquiera de estas dos formas:

```javascript
var data = JSON.parse(xhr.responseText);   
var data = response.json(); //Recomendado cuando se usa fetch con async/await
```

Una vez que se obtienen los datos, pueden utilizarse según las necesidades de la aplicación.

###  Asincronismo

Para asegurarnos que una operación ha terminado antes de que empiece otra, utilizaremos las **operaciones asíncronas**. Cuando trabajamos con *fetch* podemos crear crear función asíncrona cambiando su definición de la siguiente forma:

```javascript
async function fetchData() { 
try { 
	let response = await fetch("https://api.ejemplo.com/data"); 
	let data = await response.json(); // Trabajar con los datos obtenidos 
} catch (error) { 
console.error("Error:", error); } 
}
```

- *async* se utiliza para definir una función asíncrona.
- *await* se utiliza para esperar a que la respuesta se resuelva antes de continuar con el código.

### Inserción de datos en una web

El método *fetch()* devuelve lo que se denomina *promesa*. Después del método fetch() se debe incluir un then() a una **función** anónima para manejar la respuesta:

```javascript
fetch(url) 
   .then(function() {
   // Manejar la respuesta
})
```

Si la promesa devuelve *resolve*, la función anónima dentro del then será ejecutada. En caso contrario devolverá un *reject* y por tanto habrá que añadir un catch para capturar dicho error:

```javascript
fetch(url) 
   .then(function() { 
    // Manejar la respuesta
     }) 
    .catch(function() {
    // Manejar el error
    })
```

Habrá que utilizar el método *json()* visto para convertir los datos de la respuesta a JSON:

```javascript
fetch(url) 
 .then((response) => {  
    return response.json(); 
   })
```
Como los datos JSON aún deben procesarse, debe agregarse otro *then()* a la declaración con otra función que tenga un argumento llamado, por ejemplo, *data*:

```javascript
fetch(url) 
 .then((response) => {
   return response.json(); 
  }) 
 .then((data) => { 
  // Tratamiento de los datos JSON
   })
 ``` 
Dentro de la función definida anteriormente podemos crear una variable para almacenar los datos completos devueltos en formato JSON.

Después cada elemento podrá iterarse usando el método *map* y otra **función** para construir una estructura en *HTLM* que añadieremos posteriormente con *innerHTML*.

```javascript
fetch(url).then((response) => { 
 return response.json(); 
}).then((data) => { 
 let tableData = ""; 
 data.map((valores) => { 
 tableData += `<tr> 
  <td>${valores.nombre}</td> 
  <td>${valores.apellidos}</td> 
  </tr>`; 
  }); 
 }) 
document.getElementById("fila").innerHTML = tableData;
```

## APIs en Java

### Solicitar peticiones mediante URL 

Primeramente se crea un objeto de tipo *URL* con la dirección de servicio de petición a dicha API y a continuación nos conectaremos con un objeto de conexión *HttpURLConnection* y se le establecerá que el método de conexión sea **GET** para a continuación proceder con la conexión.

```java
try {
URL url = new URL(“https://weather.com/api/location“);
HttpURLConnection conn = (HttpURLConnection) url.openConnection();
conn.setRequestMethod(“GET”);
conn.connect();

} catch(Exception e)
```

### Verificar código devuelto

Para verificar si la petición es válida, se habrá de obtener el código **200** tal y como hemos visto ya.

Para ello recuperaremos del objeto de conexión dicho código mediante el método getResponseCode() 
Si no se devuelve un código 200 se generará una excepción y sino se continuará con el siguiente paso 3 para leer el flujo de datos devuelto (JSON o XML).

```java
...
HttpURLConnection conn = (HttpURLConnection) url.openConnection();
conn.setRequestMethod(“GET”);
conn.connect();

int responsecod = con.getResponseCode();

if (responsecod != 200 ) {
         throw new RuntimeException(“”);
} else {


}
```

### Leer el flujo de datos devuelto 

En este paso se leerá el flujo de datos devuelto (que podría ser JSON o XML).
Usaremos un objeto *StringBuilder* y un *Scanner* que leerá del url mediante el método *openStream()*.

```java
...
} else {
  StringBuilder cadenaDevuelta = new StringBuilder();
  Scanner sc = new Scanner(url.openStream());
  while (sc.hasNext()) {
   cadenaDevuelta.append(sc.nextLine());
  }  sc.close();

  System.out.println(CadenaDevuelta);
}
```

### Conversión de los datos

El trabajo con objetos *JSON* en Java no es nativo como en Javascript. No obstante, existen librerías como *JSON in Java* con la que se puede añadir como dependencia (en Maven) y que permiten el manejo de objetos JSON. 


## Postman

**Postman** es una aplicación que permite realizar peticiones de una manera simple para **testear APIs** de tipo **REST** propias o de terceros, entre otras múltiples funciones. Cuenta con una versión libre y con planes de pago para su uso (para equipos de desarrollo completos).

![](media/e486682bdc015b48c9b524cc22caacf1.jpeg)

Algunas de las funciones principales de Postman:

-   **Envío de Solicitudes**: Postman permite enviar solicitudes HTTP (GET, POST, PUT, DELETE, etc.) a cualquier API directamente desde su interfaz de usuario. Esto facilita la prueba y el desarrollo de las funciones de la API sin necesidad de escribir código.
-   **Pruebas Automatizadas**: Postman permite escribir y ejecutar pruebas automatizadas para verificar la respuesta de la API. Puedes establecer condiciones y expectativas sobre los datos devueltos por la API y recibir informes detallados sobre si las pruebas han pasado o fallado.
-   **Entorno Colaborativo**: Postman proporciona funcionalidades colaborativas que permiten a los equipos compartir y colaborar en el desarrollo y prueba de APIs. Esto facilita el trabajo conjunto en proyectos que involucran APIs.
-   **Generación de Documentación**: Se puede utilizar Postman para generar automáticamente documentación para tu API basada en las solicitudes definidas.
-   **Monitorización de APIs**: Postman ofrece una función llamada "Monitores" que permite automatizar la ejecución de colecciones de solicitudes a intervalos regulares.

### Interfaz

![](media/76c8a77f25517fda7070d9d0cf6d54f1.jpeg)

1.  Crear una nueva colección y dentro una nueva solicitud
2.  Establecer el método HTTP del menú desplegable (*GET,POST, PUT, DELETE..)*
3.  Establecer la API a utilizar en el campo URL.
4.  Para establecer el cuerpo de la solicitud hacer clic en la pestaña *Headers*
5.  Pestaña de envío de datos *form-data.*
6.  Columna con campos Clave (key) de la API.
7.  Columna con los valores del campo seleccionado.
8.  Botón de envío.

Los datos devueltos por la API en formato *JSON* aparecerán en el campo *Body*:

![](media/dffb8f9151edd21c29551a35e5f7056a.jpeg)

### Testing APIs

Para realizar pruebas (testing) de APIs en Postman lo haremos desde el apartado *Test*, en código Javascript. Ya existe una batería de pruebas preestablecida que nos puede ayudar a crear los distintos test que necesitemos.

![](media/d14e3b1e3d92af453d506c0974fbdcf0.jpeg)

Para una guía completa de referencia [https://learning.postman.com/docs/writing-scripts/script-references/test-examples/](https://learning.postman.com/docs/writing-scripts/script-references/test-examples/) 
