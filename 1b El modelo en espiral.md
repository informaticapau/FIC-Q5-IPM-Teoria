# El modelo en espiral

## Etapas

- Análisis de usuarios/tareas:
  - Requiere la captura de información sobre el dominio, el entorno, los usuarios....
    - Técnicas para recopilar información:
      - Grupos focales de usuarios.
      - Entrevistas individuales.
      - Observación en el entorno de trabajo.
      - Revisión de los procesos de _workflow_, tareas...
      - Documentar cómo los usuarios solucionan problemas particulares.
    - Una vez capturada la información hay que definir el problema y todos sus factores (actores, roles,tareas, objetivos, actividades...).
- Diseño de la solución propuesta: Cada aspecto puede estar en iteraciones diferentes según el modelo en espiral.
  - Creación de la solución: Cómo debería de parecer el software para dar una solución al problema en cuestión.
  - Patrones de diseño a usar:
    - IU: Comando, Portal, Wizards...
    - No-IU: MVC, Singleton, Fachadas...
  - Elección de la plataforma adecuada.
  - Estructura y _layout_.
  - _Mockups_, prototipos...
  - Arquitectura:
    - Lógica de presentación: interacciones, tecnología, patrones de usabilidad...
    - Lógica de negocio: requisitos del dominio, casos de uso...
    - Lógica de servicio: gestión de datos, persistencia...
  - Técnicas:
    - Desarrollo conjunto o sesiones de diseño colaborativo (CDS): El equipo de trabajo colabora con los usuarios en diseñar bocetos.
    - Arquitectura de la información:
      - Taxonomía o jerarquía de los objetos.
      - Priorización de tareas y funcionalidades.
    - Bocetos y prototipos: A más fidelidad, más coste de desarrollo.
      - Baja fidelidad: papel.
      - Fidelidad media: Aplicación _wireframe_.
      - Alta fidelidad: Aplicación de ejemplo.
- Implementación de la solución:
  - Se construye un producto "entregable".
  - Se codifican funcionalidades (escribir el código, crear los gráficos, las diferentes pantallas, la navegación...).
- Testeo de la solución (verificación y validación):
  - Funcionalidad: ¿Hace lo que tiene que hacer?
  - Usabilidad: Extraer feedback de los usuarios.
  - Pruebas de _stress_: Simulaciones de carga.
  - Recuperación ante errores.
  - Seguridad.
  - Alpha testing: Etapas iniciales de desarrollo con la funcionalidad apenas realizada.
  - Beta testing: Etapas más avanzadas del desarrollo pero todavía no en producción. Paso previo a la _release_.

## Características

- La dimensión radial corresponde al coste de cada iteración.
- Iteraciones iniciales usan prototipos más baratos.
  - Habilita el diseño en paralelo de varios modelos para explorar diferentes vías.
- Iteraciones más avanzadas poseen mayor detalle y riqueza de implementación.
  - Los mayores riesgos ya han sido mitigados previamente.
- Cada prototipo es evaluado por el usuario.
- Solo iteraciones maduras son sacadas a la luz.

## Ventajas

- Hay un mayor control del proceso.
- Los errores serían más baratos de detectar en una etapa inicial (prototipado).
- Ahorro de costes de programación y tiempo de desarrollo.
- Mayor satisfacción del usuario.
