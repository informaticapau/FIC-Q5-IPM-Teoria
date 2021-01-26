# Evaluación del producto

Evaluar un sistema involucra diferentes etapas en función del momento de desarrollo que en el que se encuentre. Las pruebas más típicas en desarrollo de software son:

- Pruebas de unidad.
- Pruebas de integración.
- Pruebas de usabilidad.
- Pruebas de aceptación.

## Evaluación de la usabilidad

Antes de realizar los tests de aceptación se quiere detectar posibles problemas en el interfaz evaluando su usabilidad.

- Inspección de usabilidad: heurísticas.
- Pruebas de usabilidad: usuarios.

### Heurísticas

Las heurísticas son guías de usabilidad:

- Ayudan a tomar decisiones al desarrollador.
- Ayudan a encontrar problemas con el diseño.

Los 10 principios de Nielsen:

1. Relacionarte al mundo real
2. Consistencia y standards
3. Ayuda y documentación
4. Control y libertad del usuario
5. Visibilidad del estado del sistema
6. Flexibilidad y eficiencia
7. Prevención de errores
8. Reconocimiento, no recuerdo
9. Informe de errores, diagnóstico y recuperación
10. Diseño estético y minimalista

La evaluación de heurísticas es realizado por un experto generalmente.

No es necesario ceñirse a un listado concreto de heurísticas, se pueden combinar diferentes guías. Las guías han de ser coherentes y apropiadas a la tecnología y modalidad de la interfaz a evaluar.

#### Etapas

- Inspeccionar el IU de forma minuciosa.
- Comparar el IU con las heurísticas.
- Listar los diferentes problemas de usabilidad. Es conveniente explicar y justificarlos.
- Justificar los problemas frente a las heurísticas evaluadas.
- Listar cada uno de los problemas. Incluso si un elemento tiene varios, es conveniente detallar todos.
- Revisitar la interfaz al menos una vez más.
  - La primera vez se necesitar aprender a usarlo.
  - La segunda vez se puede fijar más en detalle en sus aspectos particulares.

#### Aprovechamiento del potencial de la evaluación de heurísticas

- Usar múltiples evaluadores:
  - Mayor potencial de detección de problemas.
  - Cuantos más mejor, pero retornos decrecientes.
  - En general 3-5 evaluadores cuando sea posible.
- Alternar evaluación heurística con tests de usabilidad.
  - La evaluación de heurísticas es más asequible.
- Es correcto ayudar a progresar en una tarea.

#### Proceso formal de evaluación

- Entrenamiento:
  - Encuentro entre desarrolladores y evaluadores.
  - Presentación de la aplicación.
  - Descripción de usuarios tipo, dominios y escenarios.
- Evaluación:
  - Los evaluadores trabajan de forma separada.
  - Generan informes escritos o grabados.
  - Foco en detectar problemas, no catalogarlos.
  - No más de 1-2 horas por evaluador.
- Calificación de los problemas:
  - Los evaluadores priorizan los problemas encontrados (no solo los suyos).
  - Se centralizan las prioridades.
- Puesta en discusión:
  - Los evaluadores y el equipo de desarrollo se reúnen para discutir los problemas y las posibles soluciones.

La evaluación heurística es válida en cualquier etapa de prototipado. Problemas de falta de elementos (_missing elements_) son más difíciles de encontrar en prototipos de papel. Al no estar usando de verdad la interfaz, es necesario hacer un esfuerzo mayor para buscarlos.

#### Calificación de los problemas

- Factores que influyen:
  - Frecuencia de aparición.
  - Impacto: dificultad de evitación o superación.
  - Persistencia: cuántas veces hay que superarlo.
- Escalas de gravedad:
  - Cosmético: no es necesario de arreglar.
  - Menor: es necesario arreglar pero baja prioridad.
  - Mayor: es necesario arreglarlo con alta prioridad.
  - Catastrófico: imperativo arreglarse.

### Pruebas de Usabilidad

Pruebas donde se les pide a los usuarios que trabajen con la aplicación para llevar a cabo ciertas tareas.

El objetivo básico de las pruebas de usabilidad es observar a los usuarios mientras usan el producto para identificar posibles problemas de navegación o entendimiento.

Las pruebas pueden ser todo lo complejas que se quiera:

- En el lado bajo del espectro, análogamente a las pruebas con prototipos: _Guerrilla testing_.
- En un lado alto del espectro, puede suponer semanas de planificación de los ejercicios, contratar un experto en usabilidad, realizar pruebas controladas...
- En general, realizar pruebas con usuarios con metodologías poco planificadas o formales es siempre mejor que no realizar pruebas.

#### Modalidades

- Evaluación formativa:
  - Pruebas de prototipos.
  - Entorno controlado.
  - Observaciones cualitativas.
- Estudios de campo:
  - Encontrar problemas en entornos reales.
  - Evaluar implementaciones funcionales.
  - Principalmente observaciones cualitativas.
- Experimento controlado:
  - Probar hipótesis.
  - Implementaciones funcionales.
  - Observaciones cuantitativas.

#### Roles para las pruebas

Usuarios:

- Los usuarios probadores van a tener una presión importante durante la prueba:
  - Ansiedad por el rendimiento.
  - Sensación de test de inteligencia.
  - Comparación con otros sujetos.
  - Miedo a hacer el ridículo.
- Hay que tratar al usuario con respeto.
  - Cinco aspectos básicos para generar respeto y confianza:
    - Tiempo: No lo malgastarlo. Evitar tener que realizar procesos o actuaciones que puedan ser realizadas de antemano.
    - Comodidad: El usuario debe sentirse cómodo.
    - Información: Informar al usuario lo máximo posible. Consentimientos informados.
    - Privacidad: Respetar y guardar la privacidad del usuario.
    - Control: El usuario puede parar en cualquier momento o tomar decisiones sobre el proceso.
  - En un clima ideal el usuario debería de pensar en alto:
    - Lo que piensan que está pasando.
    - Lo que están tratando de hacer.
    - Lo que esperan que ocurra ante cierta acción.

Facilitador:

- Realiza el papel de informador y conductor de la prueba.
- Provee las tareas a realizar.
- Trata de incitar al usuario a pensar en alto.
- Evita que el observador interrumpa o intervenga.

Observador:

- Están callados, sin gesticular y sin expresar frustración o decepción.
- Toman notas.
- Observan incidentes críticos.
  - Negativos: errores, atascos, frustraciones...
  - También aspectos positivos remarcados por el usuario.

#### Modelo Landauer-Nielsen

Cada usuario encuentra una fracción `L` de los problemas de usabilidad. Si los tests son independientes, demuestran que `n` usuarios encontrarán `1-(1-L)^n`.

Típicamente `L = 31%`: 5 usuarios encontrarán el 85% de los problemas. Normalmente se recomienda en torno a 5 usuarios en cada iteración de diseño (pruebas más pequeñas pero más frecuentes).

Problemas con el modelo:

- La probabilidad `L` de encontrar un problema de usabilidad podría ser mucho más pequeña
que 31% en casos particulares.
- Podría no ser constante: diferentes problemas lógicamente podrían tener probabilidades diferentes.

Es una aproximación formal y razonable al proceso pero no es posible establecer con seguridad el número de usuarios a priori para un interfaz dado.

## Pruebas de aceptación

En general se busca establecer que el producto cumple con las especificaciones y requisitos.

Normalmente se distinguen:

- Pruebas realizadas por el equipo de desarrollo (herramientas automáticas).
- Pruebas realizadas con usuarios (clientes).

Existen metodologías de desarrollo guiadas por pruebas (_Test Driven Development_):

- Primero se especifican los tests.
- _Behaviour Driven Development_ (BDD) es una especialización donde los tests a especificar se definen en términos del comportamiento de la unidad a probar.

_User Acceptance Test_ (UAT): Se realiza con un usuario con conocimiento del dominio (cliente, usuario final).

- Es una de las etapas finales antes de la puesta en funcionamiento del producto.
- El objetivo no es detectar problemas funcionales, de usabilidad o estructurales sino verificar que el usuario aprueba (acepta) la aplicación en su estado actual.
- Es una verificación formal que puede acarrear normalmente la comprobación de ciertos requisitos previamente establecidos.

## Evaluación del uso

Una vez la aplicación pasa a usarse en el mundo real es conveniente medir lo bien que funciona, particularmente frente a las expectativas.

- La velocidad es un apartado de particular interés por la dificultad de evaluarlo con pruebas de usabilidad.
- Comprobar los puntos de salida habituales de la aplicación: ¿Se completan las tareas o se dejan a medias?
- Medir errores:
  - Enlaces rotos.
  - Resultados de búsqueda vacíos.
  - _Crashes_.
- Medir el comportamiento del usuario para entender mejor el uso que le da (Funcionalidades populares, no usadas...).
- Tratar de encontrar puntos de mejora
