# Aspectos del diseño de interfaces

## Realismo

En general, los interfaces se diseñan para tener una apariencia realista.

- Ayuda a que el usuario reconozca ciertas funciones.
- Ayuda a saber qué esperar de forma intuitva de ciertos controles.

En general es buena idea usar símbolos para representar elementos funcionales del interfaz. Sin embargo, demasiado realismo puede crear confusión.

**Interacción realista**: Simular un interfaz gráfico como un elemento del mundo real con el que comparte funcionalidad. Pueden limitar la funcionalidad innecesariamente.

**Skeuomorfismo**: Versiones nuevas de objetos que retienen elementos de versiones antiguas que ya no aportan funcionalidad.

## Interacción Natural

Distintos paradigmas:

- _Command Line Interface_.
- _Graphical User Interface_.
- _Natural User Interface_.

El paradigma NUI puede resultar muy cómodo para el usuario pero es el más complicado de perfeccionar.

Aspectos a considerar en un NUI:

- Dar _feedback_ de la manera más inmediata posible respecto a las acciones del usuario.
- Cuando tenga sentido, usar gestos que activen comandos, no que manipulen objetos en la pantalla.
- Evitar el aprendizaje de gestos demasiado complejos.
- Controlar entradas accidentales.

## Ley de Fitts

Afirma que el tiempo requerido `T` para alcanzar un elemento es dependiente de la distancia al elemento `D` y al ancho `W` en la dirección del movimiento.

        T = a + b*log2( 1 + D/W )

`a` y `b` son constantes que dependen del dispositivo: tiempo de arranque/parada y factor inverso a la velocidad de movimiento.

Un elemento en el extremo de la pantalla (no táctil) virtualmente tiene tamaño infinito.

Menús radiales de contexto reducen la distancia media.

- Típica en menús de videojuegos.
- No es muy cómodo si las opciones crecen demasiado.
- Son más intuitivas disposiciones en horizontal o vertical.

Conviene separar elementos pequeños y dejar márgenes entre ellos.

Elementos más grandes son más fáciles de clickar.

Es recomendable dejar elemento sensibles o destructivos en un tamaño razonablemente pequeño y/o alejado para evitar problemas.

## Interrupciones

En general, las interrupciones deben ser evitadas ya que lastran la productividad a la hora de realizar una tarea. No solo la pérdida de atención de la tarea principal durante el período de la interrupción, sino también el coste posterior de recuperar el ritmo en función del tipo de tarea.

Pueden evitarse tomando decisiones por el usuario ya que generalmente la frecuencia relativa de las posibles opciones no justifica la consulta cada vez.

A veces es necesario consultar al usuario.

- Si son previsibles varias consultas es mejor agruparlas todas de antemano.
- Interrumpir solo para decisiones urgentes, no para informar.
  - Si no es importante no mostrar.
  - Si es importante pero no requiere atención inmediara notificar sin interrumpir.

Si se abusa de las interrupciones, el usuario no va a leerlas demasiado y se va a equivocar.

Es importante dejar al usuario deshacer sus acciones:

- Da confianza al usuario.
- Menos alertas provocan una mayor concentración cuando aparecen.

## Funcionalidades

El crecimiento de funcionalidades sin medida puede desbaratar unos productos originales bien definidos. Demasiadas funcionalidades puede evitar el acceso de nuevos usuarios aunque los usuarios experimentados demandarán más funcionalidades acelerando el proceso.

Conviene recordar lo que los usuario pretenden realizar con la herramienta. A veces un usuario va a demandar nueva funcionalidad como solución a problemas que no es necesaria. Hay que indagar en los motivos por los que el usuario percibe esa funcionalidad como necesaria.

En vez de añadir nuevas funcionalidades es mejor hacer las antiguas más usables:

- Tratar de agrupar varios problemas en una solución.
- Mantener un equilibrio escuchando a los usuarios:
  - Darán muchas claves fuera de las preconcepciones.
  - Por otro lado, van a tender a una versión a medida para ellos.

Para eliminar funcionalidades:

- Investigar datos de uso sobre el programa.
- Informar a los usuarios sin dejarles.
- Facilitar alternativas si es posible.

Una característica importante es la facilidad con la que los usuarios son capaces de encontrar y usar una funcionalidad. Para evitar la masificación en pantalla, generalmente hay un compromiso:

- Hacer una funcionalidad más encontrable hace que otras partes lo sea menos.
- A veces es correcto esconderlas y hacer que las active un usuario.

Es importante decidir dónde encontrar las funcionalidades:

- Para una funcionalidad más fácil de encontrar se puede tratar con propiedades como tamaño, forma, color, posición...
- Las cosas que deben ser más encontrables deberían estar en situaciones/arreglos similares en todas las pantallas.

## Animaciones

Animar un cambio de estado ayuda al usuario a seguir el proceso, aunque a veces pueden desorientarlo:

- Evitar animaciones innecesarias.
- No ignorar la visión periférica.
- Ayudar a los usuarios a formar modelos mentales adecuados.

## Consistencia

Representa la armonía o lógica entre las diferentes partes del producto. Esa armonía se contrapone a las diferencias que se puedan encontrar. También hay que tener en cuenta la consistencia respecto a productos que ya se conocen o usos previos de ciertos elementos.

Muchas veces la consistencia se usa referida a la apariencia. Los errores de este tipo de consistencia son fácilmente identificables y corregibles.

Cuanto más se parezca algo a lo que el usuario previamente conoce más fácil es de despertar un sentimiento de inconsistencia:

- El usuario espera que se comporte de la misma manera.
- Si se va a dar un uso algo diferente a algún elemento, hay que hacerlo lo suficientemente diferente/diferenciable.

## Modos

Un modo es una parte de la aplicación de la que hay que entrar/salir y que restringe o acota las operaciones que se pueden llevar a cabo mientras esté activo.

Mientras una aplicación  esté en un cierto modo, su comportamiento frente a las entradas del usuario varían.

Afectan a la usabilidad:

- No es algo natural para la gente en el mundo real.
- Si el usuario no conoce o entiende el modo actual, se producen respuestas del sistema inesperadas.

Dado que los modos son fuente de errores comunes, es importante darle la información de forma clara al usuario. Los modos no obvios han de ser evitados. Para hacer que un modo sea obvio:

- _Feedback_ visual al usuario para reducir errores y confusión.
- Si no funcionan imágenes estáticas pueden valer animaciones sencillas.
- _Feedback_ sonoro (es más difícilmente ignorable que el visual en muchos casos).

Incluso haciendo que el modo sea obvio para los usuarios, la forma de presentarlo puede llevar a confusión.

En general los modos no son muy bien valorados pero no siempre son inadecuados y hay veces que son necesarios: Para mostrar funcionalidades sólo cuando son aplicables.

Mientras se entre intencionadamente, se vea de forma obvia su presencia y se conozca la manera de abandonarlo no hay problema.

### Modos inesperados

Los diálogos son un tipo específico de modo. Son generalmente obvios por la forma en que aparecen pero también inesperados generalmente además de interrupciones.

### Quasimodos

Modos temporales solo activos mientras el usuario explícitamente los mantenga así:

- Mayúsculas manteniendo pulsado la tecla `Shift`.
- Mantener pulsado el botón del ratón.

Siempre son obvios, esperados y fáciles de abandonar. Conviene considerar si un modo temporal resuelve la necesidad del modo o es necesario algo más persistente.

## Velocidad

Un aspecto difícilmente medible en tests con usuarios es la velocidad y respuesta de la aplicación. Es fácil saber cuándo no entienden algo pero normalmente no se mostrará si la velocidad de respuesta es adecuada.

La velocidad es la característica más importante. A diferencia de otros problemas, en caso de aplicaciones lentas los usuarios pueden abandonarlas rápidamente.

La capacidad de respuesta (_responsiveness_) de un sistema es crucial. Las investigaciones en este asunto son bastante concluyentes:

- Acciones que duran < 0.1 s se consideran instantáneas.
- Acciones < 1 s, aunque no instantáneas, no permiten perder el foco con facilidad al usuario.
- Por encima de 1s se corre ese riesgo.

Si una operación va a durar más de lo esperado es bueno dar _feedback_ al usuario. El tipo de _feedback_ depende de varios aspectos_

- Cuánto dura la acción.
- Qué tipo de acción es.

En operaciones cortas, el objetivo simplemente es hacerle obvio al usuario que se ha recibido la petición y se está trabajando.

Si la acción va a durar más de unos segundos, es cuando tiene sentido indicar algún tipo de progreso. En algunos casos es recomendable también indicarle al usuario en qué tarea se está si la acción incluye unas pocas tareas fácilmente identificables, ya que ayuda a que el usuario entienda la duración del proceso.

Si la tarea dura bastante el usuario se centrará en otro asunto: No interrumpir (audio, aviso en la barra de tareas, etc.).

### Velocidad percibida

Más importante que la velocidad real es la velocidad percibida: Cómo perciben los usuarios la velocidad del producto.

Maneras de mejorar la velocidad percibida:

- Mostrar resultados parciales cuando sea posible.
- No bloquear la interfaz con operaciones lentas.
- Decoraciones.
