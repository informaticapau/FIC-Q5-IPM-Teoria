# Sección 508

Estándares de accesibilidad requeridos para el software público en USA.

Requisitos:

- Técnicos: La codificación de un website es compatible con tecnologías asistivas.
- Funcionales: El sistema puede ser usable por personas con discapacidades.
- Soporte: La documentación de soporte e información alternativa es accesible.

## Imágenes y tablas

Proporcionar texto alternativo:

- HTML: `title`/`alt` y `caption`:

```html
<img src="logo.png" alt="Logo empresa"/>
<table>
  <caption>Título de la tabla</caption>
  <!--...-->
</table>
```

- WAI-ARIA: Para descripciones más largas y para marcar imágenes decorativas.

## Contenidos repetitivos

Proporcionar un mecanismo para saltar bloques de contenido que se repitan en múltiples páginas.

```html
<a href="#main">Saltar a noticias</a>
<nav>
  <ul>
    <li><a href="nac.html">Nacional</a></li>
    <li><a href="int.html">Internacional</a></li>
    <li><a href="eco.html">Economia</a></li>
  </ul>
</nav>
<h1><a id="#main">Noticias</a></h1>
```

Cualquier mecanismo de navegación que se repita entre páginas debe ser consistente (seguir el mismo orden).

## Color

La información no puede depender del color:

- Utilizar colores que contrasten en el fondo y el primer plano.
- No utilizar únicamente color para marcar acciones.
- No marcar campos obligatorios en un formulario sólo con color.
- No indicar errores marcando el borde de un campo en rojo.

## Formularios

- Agrupar elementos relacionados en un formulario:
  - HTML: `fieldset`/`legend` y `label`/`input`.
  - WAI-ARIA si las instrucciones no están cerca de los campos o si no son visibles en la página.

```html
<fieldset>
  <legend>Your Name</legend>
  <label for="title">Title (optional)</label>
  <input id="title" type="text">

  <label for="first-name">First name*</label>
  <input id="first-name" name="first-name" type="text">

  <label for="last-name">Last name*</label>
  <input id="last-name" name="last-name" type="text">
</fieldset>
```

- No producir un cambio de contexto (abrir una ventana, navegar a una nueva página, cambiar el foco a otro componente...) cuando el usuario selecciona o introduce información, sólo con botones/enlaces.
- Proporcionar etiquetas o instrucciones cuando se requiera la introducción de datos.
- Si se produce un error, indicar la localización del error en la descripción y, si es posible, proporcionar sugerencias para solucionarlo.

## Enlaces y botones

- Proporcionar una descripción clara del objetivo de cada enlace/botón.
- Evitar etiquetar enlaces/botones con "pulsa aquí" o "leer más".
- No usar el mismo texto para varios enlaces/botones en la misma página.
- El destino o función de cada enlace/botón debe estar claramente explicado.

## Teclado

Todas las funcionalidades deben ser operables mediante un teclado:

- No eliminar la accesibilidad de los elementos nativos HTML.
- Usar WAI-ARIA y Javascript para hacer accesibles elementos customizados.

## Foco

El indicador de foco debe ser visible. Si existe un orden en la navegación, los elementos que reciben foco deben mantener dicho orden:

- Codificar contenidos de forma que coincida su posición con el orden deseado.
- Usar `tabindex="0"` para incluir un elemento en la lista de elementos accesibles con el tabulador.

## Hojas de estilos

- Todo el contenido no textual debe tener una alternativa.
- No incluir imágenes con contenido como `background-image`.
- La información, estructura y relaciones entre los elementos de la página debe ser determinada programáticamente.
  - No incluir contenido con significado en CSS (`::before`, `::after`).
- Cuando la secuencia en la que se presentan los contenidos afecta a su significado, la secuencia de lectura debe ser determinada programáticamente.
- Evitar posicionamientos absolutos.

## Títulos y cabeceras

- Cada página web debe proporcionar un título que describa su propósito.
- Utilizar cabeceras descriptivas para structurar los contenidos.
- Usar las etiquetas `<h1>` - `<h6>` y no saltar niveles.
- Si el tamaño por defecto no es adecuado, modificar vía CSS.
- No usar las etiquetas de cabecera para otras finalidades.

## Elementos multimedia

- Audio: proporcionar una transcripcion textual.
- Vídeo:
  - Sin sonido: proporcionar una transcripción textual o una pista de sonido.
  - Con sonido: proporcionar subtítulos.
  
- Proporcionar un mecanismo para parar contenidos que se inician de forma automática.
- Proporcionar mecanismos para controlar los subtítulos y/o descripción de audio.

## Otros

- Evitar contenidos que se muevan, haga scroll, parpadeen o produzcan destellos.
- Utilizar un CAPTCHA que no se base sólo en imágenes.
- Incluir el idioma general de la página y de secciones concretas en las que cambie el idioma.

```html
<!DOCTYPE html>
<html lang="en">
  <!--...-->
  <body>
    <section lang="es">
      <!--...-->
    </section>
  </body>
</html>
```

- Validar el código HTML.

## Pruebas

- Web accessibility toolbars.
- Navegador con CSS/JS/imágenes deshabilitadas.
- Navegadores solo texto.
- Navegar sin raton.
- Usar tecnologías asistivas.
