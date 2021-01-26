# Diseño de interfaces móviles

## Herramientas para desarrollar aplicaciones nativas

El mercado de las aplicaciones móviles está formado principalmente por dispositivos **Android** e **iOs**. Google está creando un toolkit para poder diseñar aplicaciones nativas compatibles en ambas plataformas.

| |Android|iOs|Google|
|--|--|--|--|
|Lenguaje|Kotlin|Swift|Dart|
|Otros lenguajes|Java|Objective-C||
|Librería gráfica|Android SDK|Cocoa Touch|Flutter|
|Entorno de desarrollo|Android Studio|Xcode (macOS)|
|Patrón de arquitectura|MVP|HMVC|Favorece composición sobre herencia|

## Prueba de aplicaciones móviles

Las aplicaciones móviles pueden probarse de distintas maneras, cada una con sus ventajas y desventajas:

|Dispositivo real|Emulador|Servicio online|
|--|--|--|
|Eficiencia|Comodidad|Rapidez|
|Más funcionalidades|Distintas instacias|

## _Boilerplate_ (Código repetitivo)

El **_boilerplate_** o simplemente código repetitivo son secciones de código que deben incluirse en muchos lugares con poca o ninguna alteración. Cuando se utilizan lenguajes que se consideran detallados , el programador debe escribir mucho código para lograr solo una funcionalidad menor.

En las aplicaciones móviles se produce mucho _boilerplate_, es necesario crear muchos ficheros antes de escribir la primera línea de código, y el proceso de compilación realiza muchos pasos (descargar librerías, compilar, enlazar, empaquetar, incluir ficheros adicionales, firmar...) lo que provaca que sea muy lento.
