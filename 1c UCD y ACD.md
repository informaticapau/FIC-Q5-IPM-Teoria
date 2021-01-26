# Análisis de Usuario y Actividades

## UCD (_User Centered Design_)

Antes de empezar el desarrollo de una IU se realiza un enfoque hacia los usuarios para realizar un diseño de la manera más usable posible.

### Conocer al Usuario

Se extrae información de los distintos perfiles de los usuarios y se identifican características del conjunto objetivo de usuarios:

- Educación.
- Capacidades físicas.
- Experiencia en informática en general.
- Habilidades de tecleo, lectura...
- Experiencia en el dominio.
- Experiencia sobre la aplicación.
- Entorno de trabajo, contexto social.
- Patrones de comunicación

Muchas aplicaciones tienen distintos tipos de usuarios.

Obstáculos:

- Los desarrolladores y los usuarios están sistemáticamente separados con frecuencia:
  - El soporte técnico aísla a los desarrolladores de los usuarios.
  - Ventas y Marketing aíslan a los usuarios de los desarrolladores.
- Algunos usuarios son muy difíciles de llegar.
- A veces se conoce quiénes son los usuarios pero no se sabe qué necesitan.

| AVERIGUAR PROBLEMAS                       | AVERIGUAR SOLUCIONES                                                      |
| :---------------------------------------- | :------------------------------------------------------------------------ |
| ¿Qué es lo que hace la gente actualmente? | Encontrar una manera de hacerlo más fácil y eficiente.                    |
| ¿Qué tienen que hacer y no les gusta?     | Conseguir que no tengan que hacerlo o, al menos, hacerlo más entretenido. |
| ¿Qué les gustaría hacer?                  | Hacerlo posible.                                                          |

### Técnicas de investigación

Los usuarios pueden ser muy diferentes a los pensados inicialmente. Existen técnicas para averiguar lo que hacen los usuarios. Aunque es imprescindible tener una idea previa de qué usuarios son y que estos sea accesibles.

Incluso usando las técnicas no siempre puede predecirse un resultado correcto por lo que es importante saber cuando detenerse y cambiar de fase en el desarrollo.

#### _Job Shadowing_

La idea del _job shadowing_ es poder visitar a los usuarios en su entorno y poder extraer directamente información útil.

Se puede extraer mucha información útil de la que el usuario no es consciente o no valora:

- ¿Hay tareas específicas que requieren mucho tiempo?
- ¿Hace el usuario las mismas cosas repetidamente?
- ¿Ejecuta tareas con _workarounds_?
- ¿Requiere memorizar pasos o ciertos aspectos técnicos que se podrían gestionar automáticamente en un ordenador?
- ¿Usa herramientas externas tales como libreta, calculadora...?

_Job shadowing_ cumple la máxima: _Lo que ves es más relevante que lo que te cuentan_.

#### _Contextual Interviews_

Tras el proceso de observación, es conveniente pasar un tiempo con el usuario preguntándole sobre aspectos observados y otros aspectos que quizás no lo fueron para detectar problemáticas o aspectos mejorables.

Hay que evitar opiniones demasiado personales y subjetivas y no hay que forzar al usuario a realizar aspectos del diseño de la interfaz.

Preguntas tipo:

- ¿Hay tareas habituales que no haya visto?
- ¿Qué clase de problemas soluciona más a menudo?
- ¿Por qué has realizado la tarea observada de esa manera?
- ¿Cómo hacen si no hay suficiente información para completar una tarea?
- ¿Con quién interactúa habitualmente en las tareas?

#### _Remote Shadowing_

A veces no es posible visitar _in-situ_. La observación remota requiere colaboración (grabaciones de escritorio, grabación via cámara de vídeo...). No es necesario grabaciones de mucha calidad ni _framerate_. Una ventaja es que se pueden revisitar los vídeos cuando sea necesario durante el proceso.

## ACD (_Activity Centered Design_)

El diseño centrado en usuarios es muy útil y recomendable, pero no siempre es posible o conveniente. A veces es mejor centrarse en las actividades (o tareas) que se van a llevar a cabo en la aplicación.

- Es una aproximación intuitiva más clásica y la más habitual y abundante.
- Si el producto está orientado a una audiencia general, la investigación sobre el usuario es de poca ayuda en una etapa inicial.

### Analizar Tareas

Identificar tareas individuales que el programa debe hacer:

- Cada tarea es un objetivo.
- A menudo es conveniente empezar con unos objetivos globales y posteriormente refinarlos en subobjetivos.

Cuentiones esenciales:

- ¿Qué hay que hacer? -> Objetivos.
- ¿Qué es necesario previamente? -> Precondiciones.
  - Tareas que condicionan la actual.
  - Información que depende del usuario.
- ¿Qué pasos están involucrados? -> Subtareas/Proceso recursivo.

Otras preguntas:

- ¿Dónde se realiza esta tarea? -> Contexto y escenario.
- ¿Frecuencia de la tarea?
- ¿Restricciones?
- ¿Cómo se aprende la tarea?
- ¿Qué puede salir mal?
- ¿Quién más está involucrado en la tarea?

## UCD vs ACD

Es importante decidir utilizar UCD o ACD lo antes posible para enfocar las tareas de análisis y recolección de información de forma adecuada.

Es importante hacer que el producto se adapte a los usuarios de forma fácil. No siempre hay que adaptar el producto a una serie de usuarios.
