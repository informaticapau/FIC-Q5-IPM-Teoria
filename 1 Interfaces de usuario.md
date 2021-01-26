# Interfaces de usuario

## Sobre las Interfaces Usables

Son los mecanismos mediante los cuales un usuario interactúa con un sistema. Dichos mecanismos deben permitir la entrada de información por parte del usuario y abastecerle con la salida pertinente. Cualquier dispositivo que requiere entrada y/o salida para el usuario necesita un interfaz.

### Importancia de las IU

La interfaz de usuario es muy importante ya que afecta de manera decisiva en la percepción de un _software_:

- Un _software_ usable se vende mejor.
- _Softwares_ y _Webs_ no usables se abandonan rápidamente.

A veces la percepción es bastante superficial y depende de preconcepiones. Un usuario puede echarse la culpa de errores debidos a un mal diseño si le parece suficientemente atractivo de inicio.

### Problemas de una mal IU

- Una IU mal diseñada hace perder el el tiempo a los usuarios.
- Los errores de diseño son costosos (mantenimiento, atención al cliente...).
- Afecta a sistemas críticos.

### Dificultades

Las IU son difíciles de diseñar debido a que quien las diseña no suele ser un usuario. De a misma manera los usuarios frecuentemente no saben exactamente lo que quieren o no son capaces de expresarlo. Si son frecuentes los errores en el uso de una IU probablemente se deba a un error de diseño.

Las IU son difíciles de crear ya que requieren una gran parte del esfuerzo de desarrollo de un proyecto _software_. Normalmente cerca del 50% en:

- Tiempo de diseño.
- Tiempo de implementación.
- Tiempo de mantenimiento.
- Tamaño del código.

## Desarrollo de las IU

### Modelo de desarrollo de las IU

El modelo en cascada limita la interacción del usuario durante el desarrollo a las fases de análisis de requisitos y las pruebas de aceptación. Es un proceso más arriesgado y menos predecible de lo normal por lo que no es apto para el desarrollo de IU.

La mejor opción es un desarrollo en espiral entre diseño, implementación y evaluación.

### Prototipado en papel

Representaciones muy sencillas y rápidas de corregir y modificar.

Diseño de la estructura:

- Diagramas de flujo:
  - Indican qué tiene que hacer el usuario para conseguir lo que quiere.
  - Es preferible diagramas de flujo sencillos que cubran las necesidades más relevantes.
- _Storyboards_:
  - Técnica originalmente desarrollada para planificar animaciones en películas.
  - Desenvuelven el camino de un usuario para una cierta acción en una serie de _snapshots_.
  - Se centran en los elementos de interacción.
  - Es una técnica más compleja: preferible en acciones donde el diseño no sea demasiado obvio.

Una vez se tiene la estructura general, se diseñan los bocetos de las pantallas individuales. El diseño de la estructura permite saber ya qué funcionalidades y elementos son necesarios en cada pantalla.

Diseño de las pantallas:

- _Wireframes_ prototipos de baja fidelidad, o vistas anatómicas:
  - Representaciones esquemática de los elementos de la interfaz y su organización.
  - Representan la estructura exacta de una pantalla sin detalles de decoración.
- _Mock-ups_ o prototipos de alta fidelidad.
  - Ayudan a los usuarios a tener una idea más clara de la apariencia de la interfaz que el _wireframe_.
  - Añaden detalles visuales: sombras, texturas, imágenes, transparencias, etc.
  - No son solo una cuestión de apariencia, también sirve para dar pistas o facilitar al usuario el acceso a funcionalidades.

_Testing_ de prototipado en papel: Muchas veces el simple hecho de realizar el prototipado hace que los problemas se hagan obvios. Cuando no es obvio:

- Se puede asumir que nuestros prototipos en papel son versiones primitivas del producto.
- Se pueden realizar algunos tests de usabilidad con ellos:
  - Una primera ronda de testeo: _Guerrilla testing_ (testing informal):
    - Se necesitan unos pocos voluntarios.
    - Se utilizan los bocetos de pantallas para mostrarle al usuario el acceso a la funcionalidad.
    - Se pueden empezar a detectar problemas con el diseño en determinadas partes.
  - _Testings_ más completos o formales basados en tareas.
    - Definir las tareas: Se observa al usuario realizar la tarea.
    - Preparar las pantallas:
      - Definir aquellas que previsiblemente puedan ser visitadas para la tarea.
      - Crear elementos de _pop-up_.
      - Preparar un mecanismo para escribir datos.
      - Escribir las tareas individualmente en papeles.
    - Preparar el test:
      - Reclutar gente. Mejor que no estén demasiado familiarizados con el entorno de desarrollo.
      - No ejecutar los tests de diferentes personas demasiado seguidos: Permite analizar los problemas o situaciones no previstas detectadas y corregirlas.
      - Involucrar si es posible una tercera persona que ayude a interaccionar con el probador.
    - Ejecutar el test:
      - No influenciar al usuario.
      - No resolver dudas tras haberse quedado atascado. Si es muy obvio que no se va a poder resolver la tarea se puede ayudar o directamente pasar a otra.
    - Analizar resultados:
      - Analizar la información cualitativa, no cuantitativa.
      - Identificar problemas, priorizarlos y resolverlos.

### Internacionalización y localización

En la informática, la **internacionalización** es el proceso de diseñar _software_ de manera tal que pueda adaptarse a diferentes idiomas y regiones sin la necesidad de realizar cambios de ingeniería ni en el código.

La **localización** es el proceso de adaptar el _software_ para una región específica mediante la adición de componentes específicos de un _locale_ y la traducción de los textos, por lo que también se le puede denominar regionalización (no obstante la traducción literal del inglés es la más extendida).

Es una práctica común en el idioma inglés (sobre todo en el ámbito de la computación), abreviar _internationalization_ con el numerónimo **"i18n"**. Ello se debe a que entre la primera i y la última ene de dicha palabra hay 18 letras. Lo mismo sucede con _localization_, que se abrevia **"L10n"**. La L mayúscula se utiliza para distinguirla de la i minúscula de i18n.

### Documentaciones para el desarrollo de interfaces

#### CUA (_Common User Agents_)

Documentación desarrollada por IBM a modo de catálogo de los _widgets_ disponibles y lo que significa cada uno. Un agente de usuario es una aplicación informática que funciona como cliente en un protocolo de red; el nombre se aplica generalmente para referirse a aquellas aplicaciones que acceden a la _World Wide Web_.

#### HIG (_Human Interface Guidelines_)

Son documentos que ofrecen a los desarrolladores de aplicaciones un conjunto de recomendaciones destinadas a mejorar la experiencia para los usuarios, haciendo interfaces de uso más intuitivos, aprendibles, y constantes.

Su objetivo principal es crear una experiencia sólida y consistente en el ambiente en que se desenvuelven las aplicaciones. La mayoría se limitan a definir una apariencia común para las aplicaciones, y se centran en los usos en un ambiente particular.

Indican un conjunto de reglas de utilidad general:

- Reglas visuales del diseño: diseño de iconos, estilo para las ventanas...
- Especifican cómo serán los mecanismos de entrada y la interacción de estos con el usuario.
- A veces define la terminología estándar y la semántica relacionadas con ciertos elementos o acciones.

Deben interpretarse como una importante recomendación a la hora de ayudar a los desarrolladores a crear usos mejores.

#### Sistemas de Diseño

Son conjuntos de patrones interconectados y prácticas compartidas organizadas coherentemente para ayudar en el diseño de productos digitales y el desarrollo de productos como aplicaciones o sitios web.

Puede contener:

- Bibliotecas de patrones.
- Lenguaje de diseño.
- Guías de estilo.
- Componentes codificados.
- Lenguaje de marca.
- Documentación para su uso.

Sirve como referencia que ayuda a los diferentes equipos involucrados (diseñadores, desarrolladores, redactores y gerentes de proyectos) a diseñar y construir productos digitales.

Algunas de las ventajas de un sistema de diseño son:

- Compilaciones más rápidas: a través de componentes reutilizables y fundamentos compartidos.
- Mejores productos: gracias a experiencias de usuario más coherentes y un lenguaje de diseño coherente.
- Mejora del mantenimiento y escalabilidad: mediante la reducción del diseño y la deuda técnica.
- Mayor enfoque para los equipos de productos: mediante la resolución de problemas comunes para que los equipos puedan concentrarse en resolver las necesidades de los usuarios.
