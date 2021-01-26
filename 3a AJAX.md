# Asynchronous Javascript And XML (AJAX)

AJAX es la combinación de objetos/funciones del navegador para:

- Realizar peticiones de datos con Javascript.
- Mostrar dichos datos con HTML DOM.

Permite actualizar páginas web de forma asíncrona sin
recargar la página completa.

## Cross-Origin HTTP Request (CORS)

Un recurso de un dominio A hace peticiones de otro recurso a un dominio B. Habitual para:

- Ficheros de estilos CSS.
- Imágenes.
- Scripts Javascript.

Por motivos de seguridad, los navegadores no permiten realizar peticiones HTTP a otros dominios desde scripts.

## Peticiones AJAX

### _Legacy_

#### IE5, IE6

```js
xhttp = new ActiveXObject("Microsoft.XMLHTTP");
```

#### Chrome, IE7+, Firefox, Safari, Opera

```js
xhttp = new XMLHttpRequest();
```

- Crear una petición:

```js
xhttp.open(method, url, async);
// method: GET, POST, PUT, DELETE...
// async: true/false
```

- Enviar una petición:

```js
xhttp.send(); // GET
xhttp.send(string); // POST
```

- Procesar respuesta:

```js
xhttp.onreadystatechange = callback;
/* callback: función que se ejecutará cada vez que cambie el estado de la propiedad readyState */
```

- Estados posibles de `readyState`:
  - 0: petición no inicializada.
  - 1: conexión establecida con el servidor.
  - 2: petición recibida.
  - 3: petición procesándose.
  - 4: petición terminada y respuesta preparada.
- Otras propiedades del objeto `XMLHttpRequest`:
  - `status`: código de estado devuelto por el servidor tras procesar la petición (200, 400, 404...).
  - `statusText`: texto asociado al código de estado.

```js
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
    // this hace referencia a xhttp
    if (this.readyState == 4 && this.status == 200) {
        dataAsString = this.responseText;
        // dataAsXML = this.responseXML ;
    }
};
xhttp.open("GET", "http://server.com/api/example", true);
xhttp.send();
```

### ECMAScript 6 (2015)

- Reemplazo de `XMLHttpRequest` por `fetch`.
- Soportado en la mayor parte de los navegadores desde 2017. No soportado en:
  - Internet Explorer.
  - Opera Mini.
  - Blackberry browser.

```js
Promise<Response> fetch(resource [, init ]);
```

- Parámetros de entrada:
  - `resource`: recurso que se solicita (url, objeto Request).
  - `init`: configuración de la petición:
    - `method`: tipo de petición (GET, POST, PUT, DELETE...).
    - `headers`: cabeceras que se incluyen en la petición.
    - `body`: cuerpo del mensaje (Blob, FormData, BufferSource, ReadableStream...).
    - `mode`: modo en el que se hará la petición (cors, no-cors, same-origin).
    - `credentials`: credenciales para realizar la petición.
    - `cache`: modo de cache.
    - `redirect`: modo de redirección usado.
- Valores de retorno:
  - `Promise` que se resuelve en un objeto `Response`:
    - Es un proxy que permite asociar código para gestionar qué hacer si la función asíncrona termina de forma correcta o devuelve un código de error.
    - Dispone de tres métodos:
      - `promise.then()`: se ejecuta cuando la petición asíncrona termina de forma exitosa.
      - `promise.catch()`: se ejecuta cuando se produce una excepción.
      - `promise.finally()`: se ejecuta al final, independientemente del resultado de la petición asíncrona.
  - Propiedades de `Response`:
    - `ok`: booleano que indica si la respuesta fue exitosa.
    - `status`: código de estado de la respuesta (200, 400, 404...).
    - `statusText`: mensaje correspondiente al código de estado.
    - `headers`: cabeceras.
    - `type`: tipo de la respuesta.
    - `url`: url de la respuesta.
  - Métodos de `Response`: Leen el _stream_ de la respuesta y devuelven una `Promise` que se resuelve en otro objeto.
    - `arrayBuffer()`: devuelve una `Promise` a un `ArrayBuffer`.
    - `blob()`: devuelve una `Promise` a un `Blob`.
    - `formData()`: devuelve una `Promise` a un `FormData`.
    - `json()`: devuelve una `Promise` a un `JSON`.
    - `text()`: devuelve una `Promise` a un `USVString` (texto).
