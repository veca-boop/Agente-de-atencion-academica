# ADR-001: Arquitectura de monolito modular

## 1. Contexto

El proyecto **Agente de Atención Académica en Copilot** busca facilitar la atención de consultas académicas de los estudiantes de Ingeniería en Tecnologías de la Información mediante un agente integrado en Microsoft Teams, utilizando Copilot Studio.

El agente proporcionará información sobre materias, horarios, profesores, calendario académico, trámites y bajas, a partir de información institucional autorizada por la dirección de carrera.

El sistema debe organizar las distintas funciones de atención académica y facilitar la incorporación de cambios conforme se avance en el desarrollo. También debe respetar los límites establecidos: proporcionar información y orientación sin ejecutar transacciones académicas ni ofrecer información no autorizada.

## 2. Decisión

Se decidió utilizar una **arquitectura de monolito modular**, en la que las funcionalidades del sistema se organizan en módulos con responsabilidades específicas, dentro de una misma aplicación.

La arquitectura se organizará en los siguientes módulos:

- **Atención y consultas:** recibe las consultas de los estudiantes y coordina la atención.
- **Información académica:** organiza las respuestas relacionadas con materias, horarios, profesores y calendario académico.
- **Trámites y bajas:** proporciona información sobre procedimientos académicos y bajas.
- **Validación y administración:** apoya la validación de consultas y la administración de la información autorizada.

Además, se utilizarán los patrones de diseño **Strategy** y **Factory**, definidos previamente en la Actividad 2, para apoyar la organización de los comportamientos y la creación de los objetos correspondientes.

## 3. Alternativas consideradas

Se consideraron las siguientes alternativas arquitectónicas:

- **Monolito tradicional:** concentra las funcionalidades sin establecer una separación modular clara. Se descartó porque la organización por responsabilidades es importante para mantener diferenciadas las funciones académicas del agente.
- **Monolito modular:** organiza las funcionalidades en módulos con responsabilidades específicas dentro de una misma aplicación. Se eligió porque permite estructurar el sistema de manera clara sin introducir la complejidad de distribuir sus funcionalidades.
- **Microservicios:** separa las funcionalidades en servicios independientes. No se eligió para esta etapa del proyecto, ya que la separación y operación de múltiples servicios añadiría complejidad que no se considera necesaria para el alcance actual.

## 4. Consecuencias

**Consecuencias positivas:**

- Las responsabilidades quedan organizadas en módulos identificables.
- Los cambios pueden concentrarse en el módulo correspondiente, procurando reducir el impacto sobre los demás.
- La estructura facilita el mantenimiento y la evolución incremental del prototipo.
- La arquitectura permite mantener una organización clara entre la atención, la información académica, los trámites y la validación.

**Consecuencias y limitaciones:**

- Los módulos forman parte de una misma aplicación, por lo que no cuentan con el aislamiento de despliegue propio de servicios independientes.
- Es necesario mantener claras las responsabilidades y las relaciones entre módulos para evitar dependencias innecesarias.
- La calidad de las respuestas depende de que la información académica utilizada esté autorizada y actualizada.
- La integración y puesta en funcionamiento del agente requieren la participación de la dirección de carrera y los permisos correspondientes.

## 5. Estado

**Aceptada.**

La arquitectura de monolito modular se estableció como decisión de diseño y sirve como base para continuar el desarrollo del Agente de Atención Académica en Copilot.

