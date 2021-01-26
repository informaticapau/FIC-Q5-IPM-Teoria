# Diseño de interfaces web

## Aplicaciones web

Son aplicaciones Cliente/Servidor. Originalmente la web no se diseñó para desarrollar aplicaciones sino para compartir recursos (documentos e imágenes).

### Elementos

| Cliente   | Middleware | Servidor |
| :-------- | :--------- | :------- |
| Navegador | Http       | Genérico |

### Middleware

Lógica de intercambio de información entre aplicaciones. Asiste a una aplicación para interactuar o comunicarse con otras aplicaciones, paquetes de programas, redes, hardware o sistemas operativos.

Simplifica el trabajo de los programadores en la tarea de generar las conexiones y sincronizaciones que son necesarias en los sistemas distribuidos. De esta forma, se provee una solución que mejora la calidad de servicio, así como la seguridad, el envío de mensajes, la actualización del directorio de servicio...

Funciona como una capa de abstracción de software distribuida, que se sitúa entre las capas de aplicaciones y las capas inferiores (sistema operativo y red) proporcionando una API para la fácil programación y manejo de aplicaciones distribuidas.

## Herramientas de desarrollo web

### HTML5

Versión más reciente de HTML estandarizada por el W3C. Se encarga de la distribución de los elementos en el documento.

### CSS3

Versión más reciente de CSS estandarizada por el W3C. Se encarga de la apariencia de los elementoss del documento.

### ECMAScript

Variedad de JavaScript estandarizada por ECMA. Añade interacción.

### Páginas de interés

- <https://www.w3.org/>
- <https://validator.w3.org/>
- <https://caniuse.com/>
- <https://www.w3schools.com/>
- <https://developer.mozilla.org/es/>
- <https://www.quirksmode.org/>
- <https://alistapart.com/>
- <https://www.sitepoint.com/>

## DOM (_Document Object Model_)

Es esencialmente una interfaz de plataforma que proporciona un conjunto estándar de objetos para representar documentos HTML, XHTML y XML, un modelo estándar sobre cómo pueden combinarse dichos objetos, y una interfaz estándar para acceder a ellos y manipularlos.

A través del DOM, los programas pueden acceder y modificar el contenido, estructura y estilo de los documentos HTML y XML, que es para lo que se diseñó principalmente.

Permite el acceso dinámico a través de la programación para acceder, añadir y cambiar dinámicamente contenido estructurado en documentos con lenguajes como ECMAScript (JavaScript). El responsable del DOM es el World Wide Web Consortium (W3C).

## Interfaces web en dispositivos móviles

Hoy en día casi todo el mundo posee un dispositivo móvil pero no un pc de sobremesa o portátil. El número de accesos a internet mediante dispositivo móviles a aumentado llegando incluso a superar los accesos de equipos de sobremesa, por lo que es importante orientar el diseño de las interfaces a los primeros para evitar tener que rediseñarlas para adaptarlas.

### Diferencias notables entre dispositivos móviles y de sobremesa

|  Pantalla   |     Conexión     | Interacción | Hardware | Sensores |
| :---------: | :--------------: | :---------: | :------: | :------: |
|   Tamaño    |    Velocidad     |   Gestos    |   CPU    |  Cámara  |
| Orientación | Consumo de datos |   Teclado   | Memoria  |   GPS    |
|             |                  |             | Batería  |          |

### Herramientas de desarrollo y pruebas

- Simuladores y emuladores: <https://www.browserstack.com/>
- Remote Labs:
  - <https://firebase.google.com/docs/test-lab/>
  - <http://developer.samsung.com/rtlLanding.do>
- Extensiones para navegador en escritorio.
- Prototipado (skins o sw específico)
- IDEs
- W3C mobileOK checker

### Opciones de desarrollo

- **_Website_ dedicado**:
  - Sitio optimizado para móvil.
  - 2 URLs con el mismo contenido.
  - Configuración:
    - Cliente:
      - Cookies
    - Servidor:
      - Mime-types
      - Redirección
    - Detección móvil:
      - User-agent: Cadena de caracteres que identifica el navegador y su versión.
- **_Responsive Web Design_**:
  - Se adapta el _site_ al tamaño de pantalla.
  - 1 URL

## _Website_ dedicado

### HTML para móviles

Antes los dispositivos estaban muy limitados por las tecnologías de sus fabricantes, provocando que los navegadores de modelos diferentes utilizaran distintas versiones de lenguajes de marcado web. A día de hoy la mayoría de dispositivos móviles (comúnmente _smartphones_) son capaces de utilizar HTML5.

Engines:

- Webkit (Safari iOS, Android...).
- Gecko (Firefox mobile).
- Blink (Google Chrome (v28+), Edge, Brave, Opera v15+).
- Presto (Opera mobile).
- Trident (IExplorer mobile).
- EdgeHTML (Edge).

### CSS para móviles

```css
<link rel="stylesheet" type="text/css" href="file.css"
media="mediatype and|not|only (media feature)" />
```

**Media queries** (CSS3):

- Media type: screen
- Media feature:
  - `max-device-width` / `min-device-width`.
  - `max-width` / `min-width`.
  - `orientation`.
  - `aspect-ratio`.
  - `min-device-pixel-ratio` / `max-device-pixel ratio` (no estándar).
  - `resolution` / `min-resolution` / `max-resolution` (estándar).

### JavaScript para móviles

Es un leguaje que va a ser interpretado, se va a interactuar co él y va a generar eventos. Por tanto, consume:

- Batería.
- Ancho de banda.
- Cache.

Supone un coste computacional en dispositivos no muy modernos:

- Recuperando diálogos:
  - `alert`
  - `confirm`
  - `prompt`

Para reducirlo pueden utilizarse librerías _mobile_, aunque perjudicarían el tamaño, los tiempos de carga y la inicialización.

Puede utilizarse para realizar _Browser Detection_ y utilizar funciones de los navegadores.

#### Geolocalización

Obtención de la localización del usuario:

- Cliente:
  - GPS A-GPS.
  - Información de celda.
  - Posición WiFi.
- Servidor:
  - IP.
  - Operador.
  - Idioma.
  - WiFi AP.
- Preguntar al usuario.

En JavaScript: Objeto `navigator.geolocation` (estándar W3C). El usuario configura los permisos en el navegador. Asíncrono.

### Optimizaciones para móviles

#### Optimización de formularios

- Simplificar formularios incluyendo sólo detalles importantes.
- Usar una disposición vertical de los elementos.
- Usar menús o listas desplegables frente a radioButtons o checkBoxes.
- Utilizar el atributo `type` más adecuado en elementos `input`.

#### _CSS Sprites_

Abrir una conexión con el servidor para cargar imágenes (`<img src="">`) es un proceso costoso. Si existen una gran cantidad de imágenes pequeñas o iconos es recomendable crear una única imagen de mayor tamaño combinando las imágenes pequeñas y restringir la visualización a zonas concretas.

### Mejores prácticas

- Desarrollar código simple.
- Reducir el número de peticiones HTTP.
- Minimizar tamaño:
  - Eliminar espacios.
  - No cargar recursos no usados.
  - Máxima compresión de imágenes.
- Evitar usar sombras o gradientes.
- Usar peticiones AJAX si es posible (lazy loading).
- Evitar `try/catch`, `with`, `eval`, variables globales, _pop ups_...
- Concentrar cambios en DOM en una función.

## _Responsive Web Design_

Se diseña una página inicialmente para móvil y a media que aumenta el tamaño de la pantalla de los dispositivos se aumenta el tamaño de los elementos o se modifica su colocación.

El **diseño web adaptativo** sigue tres principios:

- _Fluid Layout_: Todos los elementos deben ser fluidos o flexibles y adaptarse al tamaño de la pantalla.
- _Media Queries_: Para adaptar y ejercer pequeños cambios al diseño de los elementos dependiendo del dispositivo.
- Imágenes flexibles: La imágenes también se adaptan al layout flexible.

### Contenidos flexibles

Eliminar unidades absolutas y utilizar unidades relativas usando la fórmula `target / context = result` siendo:

- _Target_: Tamaño deseado para el elemento.
- _Context_: Tamaño del elemento contenedor.
- _Result_: Tamaño relativo a usar.

#### Medidas flexibles

Se establece el tamaño de fuente al tamaño por defecto del navegador (normalmente 16px).

Se utiliza unidades relativas para escalar los tamaños fuente (em/rem):

- em: Escala respecto al contenedor padre.
- rem: Escala respecto al contenedor raíz.

```css
body { font-size: 100% ; }
h1 { font-size: 1.5em; /* 24 px / 16 px */ }
p { font-size: 0.875em; /* 14 px / 16 px */ }
```

#### Medidas _Responsive_

Se utilizan _viewport units_: Unidades relativas a la parte visible del navegador. 1 _viewport unit_ corresponde a un 1%.

- vw: _viewport height_.
- vh: _viempor width_.
- vmin: Menor tamaño (alto o ancho) del _view port_.
- vmax: Mayor tamaño (alto o ancho) del _view port_.

El navegador calcula el tamaño de fuente de forma dinámica:

```css
html { font-size: calc(1em + 1vw); }
/* Si vw = 0, font-size = 1em */
/* Cuanto más grande es la parte vw, el texto se hará más grande en pantallas grandes */
```

### _CSS Media Queries_

Se utiliza la regla `@media` para incluir un bloque de propiedades CSS solo si una determinada condición es verdadera.

```css
@media condition {
  /* CSS Blocks */
}
```

### Imágenes flexibles

Adaptar las imágenes (u otros elementos multimedia) al tamaño de los dispositivos. HTML 5.1 estandariza esta solución. Para lograrlo algunos navegadores soportan el uso de imágenes vectoriales (SVG...).

#### Antes de HTML 5.1

```css
img { /* Style */ }
```

- Funciona en la mayoría de los navegadores modernos.
  - No funciona en versiones antiguas de IE!
- Escala imágenes al tamaño del elemento contenedor.
- Aplicable a otros elementos (_video_, _object_, etc).

#### Imágenes flexibles en HTML 5.1

- Selección en base a densidad de píxeles:
  - Retina / 4K / Ultra HD.
  - x device pixel ratio
  - No soportado por IE, Opera Mini, Android Browser v4.4.

```css
<img src="im_300w.jpg" srcset ="im_300w.jpg 1x, im_600w.jpg 2x" width="300" height="300" alt="Description"/>
```

- Selección en base a _viewport_:
  - w tamaño de imagen.
  - vw tamaño relativo de _viewport_.

```css
<img src ="im_300w.jpg" srcset ="im_300w.jpg 300w, im_600w.jpg 600w" sizes="(max-width: 640px) 100vw, (max-width: 960px) 75vw, 300 px" alt="Description"/>
```

- Selección por _breakpoint_:
  
```html
<picture>
  <source media="(min-width=960px)" srcset ="im-large.jpg">
  <source media="(min-width=575px)" srcset ="im-medium.jpg">
  <img src="im-small.jpg" alt="Desc"/>
</picture>
```

### Workflow

- Opción 1: adaptar el diseño para _Desktop_:
  - No recomendada.
- Opción 2: _Mobile First_:
  - Comenzar con el diseño para móvil.
  - Optimizar para pantallas más grandes.

>_The absence of a media query is in fact, the first media query._ ~Bryan Rieger.

### Hojas de estilos

- Incluir varias hojas de estilos en el documento HTML:

```css
<link href="default.css" type="text/css" rel="stylesheet" media="screen "/>
<link href="desktop.css" type="text/css" rel="stylesheet" media="only screen and (min-device-width: 1024px) and (max-width: 989px)"/>
```

- Incluir una hoja de estilo que incluye _Media Queries_:

```css
@media screen and (min-width: 1024 px) {
/* Ajustes menores */
section ul li { width: 20%; }
}
```
