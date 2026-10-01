# Especificación de requisitos

Sistema: Agente de Atención Académica en Copilot  
Autor: Ana Victoria Hernández Álvarez  
Versión: 4  
Fecha de última actualización: 30/09/2026

---

# 1. Propósito y alcance

## Propósito del documento

Este documento define los requisitos funcionales y no funcionales del Agente de Atención Académica en Copilot. También establece el origen, prioridad, criterios de aceptación, métricas y trazabilidad de los requisitos.

El documento está dirigido al equipo encargado del desarrollo del agente y a la Dirección de carrera, con el propósito de establecer las funcionalidades y características de calidad que deberá cumplir el sistema.

## Alcance del sistema

El sistema será un agente de Copilot integrado en el chat personal de Microsoft Teams de la directora de carrera de TI. El agente permitirá a los alumnos consultar información académica previamente proporcionada y aprobada por Dirección de carrera por medio de mensajes de texto.

El sistema deberá permitir:

- Consultar las materias disponibles.
- Consultar información de una materia.
- Consultar los prerrequisitos de una materia.
- Consultar los trámites escolares disponibles.
- Consultar información de un trámite.
- Consultar el calendario escolar.
- Consultar las restricciones escolares.
- Consultar las causas de las restricciones escolares.
- Mantener actualizada la información académica utilizada por el agente.

El sistema contará con un menú de servicios que permitirá al alumno acceder a las diferentes opciones de consulta.

## Fuera del alcance

El sistema no deberá:

1. Realizar trámites en nombre del alumno.
2. Modificar directamente la información oficial de la universidad.
3. Proporcionar información que no se encuentre dentro de las fuentes autorizadas.
4. Sustituir la atención directa de Dirección de carrera.
5. Proporcionar instrucciones detalladas para completar trámites que no hayan sido autorizadas.
6. Resolver consultas que no correspondan al ámbito académico definido para el agente.

---

# 2. Usuarios y su contexto

| Usuario | Qué hace actualmente sin el sistema | Qué espera del sistema |
|---|---|---|
| Alumno | Realiza consultas mediante Teams o directamente con Dirección de carrera para obtener información sobre materias, trámites, fechas y restricciones. | Obtener información académica de manera rápida sin depender de la disponibilidad inmediata de Dirección de carrera. |
| Dirección de carrera | Atiende consultas académicas y busca información cuando no se encuentra disponible de manera inmediata. | Reducir consultas repetitivas y proporcionar información previamente validada y autorizada. |

## Conflictos identificados entre usuarios

1. El alumno busca obtener información de manera rápida, mientras que Dirección de carrera necesita asegurar que las respuestas proporcionadas sean correctas, vigentes y autorizadas.

2. Algunas consultas requieren actualmente que Dirección de carrera busque información antes de responder, lo que puede retrasar la atención del alumno.

---

# 3. Requisitos funcionales

## 3.1 Resumen

| ID | Nombre del requisito | Prioridad | Origen |
|---|---|---|---|
| RF-001 | Mostrar menú de servicios | Imprescindible | Visión del producto |
| RF-002 | Mostrar materias disponibles | Imprescindible | Visión del producto + entrevista |
| RF-003 | Mostrar información de una materia | Imprescindible | Visión del producto + entrevista |
| RF-004 | Mostrar prerrequisitos de una materia | Imprescindible | Entrevista |
| RF-005 | Mostrar trámites disponibles | Imprescindible | Visión del producto |
| RF-006 | Mostrar información de un trámite | Imprescindible | Visión del producto |
| RF-007 | Mostrar calendario escolar | Imprescindible | Visión del producto + entrevista |
| RF-008 | Mostrar restricciones escolares | Imprescindible | Visión del producto + entrevista |
| RF-009 | Mostrar causas de restricción escolar | Imprescindible | Entrevista |
| RF-010 | Modificar información académica | Imprescindible | Visión del producto |

---

## 3.2 Fichas

### RF-001 · Mostrar menú de servicios

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar un menú con las opciones disponibles para realizar consultas académicas. |
| **Origen** | Visión del producto |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Al iniciar una interacción con el agente, deberá mostrarse el menú de servicios.<br>• El menú deberá mostrar la opción “Materias”.<br>• El menú deberá mostrar la opción “Trámites y bajas”.<br>• El menú deberá mostrar la opción “Calendario y restricciones”.<br>• El alumno deberá poder seleccionar cualquiera de las opciones disponibles. |
| **Relacionado con** | RF-002, RF-005, RF-007, RF-008 |

---

### RF-002 · Mostrar materias disponibles

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar las materias disponibles de la carrera correspondientes al semestre vigente. |
| **Origen** | Visión del producto + entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Al usuario escribir la opción “Materias”, deberá mostrarse la información correspondiente al semestre vigente.<br>• Deberá mostrarse la lista de materias disponibles.<br>• Deberá mostrarse el horario correspondiente a cada materia cuando dicha información se encuentre disponible.<br>• Deberá mostrarse el profesor correspondiente a cada materia cuando dicha información se encuentre disponible. |
| **Relacionado con** | RF-001, RF-003, RF-004, RNF-CON-001 |

---

### RF-003 · Mostrar información de una materia

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar información descriptiva sobre la materia seleccionada. |
| **Origen** | Visión del producto + entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • El alumno deberá poder escribir una materia disponible.<br>• El sistema deberá mostrar qué es la materia seleccionada.<br>• El sistema deberá mostrar para qué sirve la materia seleccionada.<br>• La información mostrada deberá corresponder con la información académica autorizada. |
| **Relacionado con** | RF-002, RNF-CON-001 |

---

### RF-004 ·Mostrar prerrequisitos de una materia

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar los prerrequisitos establecidos para la materia seleccionada. |
| **Origen** | Entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • El alumno deberá poder escribir una materia disponible.<br>• El sistema deberá identificar los prerrequisitos asociados a la materia seleccionada.<br>• El sistema deberá mostrar los prerrequisitos cuando la materia los tenga.<br>• El sistema deberá indicar cuando una materia no tenga prerrequisitos registrados. |
| **Relacionado con** | RF-002, RNF-CON-001 |

---

### RF-005 · Mostrar trámites disponibles

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar la lista de trámites escolares autorizados por Dirección de carrera. |
| **Origen** | Visión del producto |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Al escribir la opción “Trámites y bajas”, deberá mostrarse la lista de trámites disponibles.<br>• La lista deberá contener únicamente trámites autorizados por Dirección de carrera.<br>• Cada trámite deberá poder ser seleccionado por el alumno para consultar su información. |
| **Relacionado con** | RF-001, RF-006, RNF-CON-001 |

---

### RF-006 · Mostrar información de un trámite

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar la información general del trámite seleccionado. |
| **Origen** | Visión del producto |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • El alumno deberá poder escribir un trámite disponible.<br>• El sistema deberá mostrar qué es el trámite.<br>• El sistema deberá mostrar para qué sirve el trámite.<br>• El sistema deberá mostrar qué información debe tener disponible el alumno.<br>• El sistema deberá indicar a quién debe contactar el alumno para obtener información más específica.<br>• El sistema deberá mostrar el mensaje “Si requieres información más específica contacta a tu directora de carrera”. |
| **Relacionado con** | RF-005, RNF-CON-001 |

---

### RF-007 · Mostrar calendario escolar

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar el calendario escolar vigente utilizado por Dirección de carrera. |
| **Origen** | Visión del producto + entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Al escribir la opción correspondiente al calendario escolar, deberá mostrarse el calendario vigente.<br>• El calendario mostrado deberá corresponder con la información de la fuente oficial autorizada.<br>• El sistema no deberá mostrar como vigente un calendario que haya sido sustituido por una versión actualizada. |
| **Relacionado con** | RF-001, RF-010, RNF-CON-001 |

---

### RF-008 · Mostrar restricciones escolares

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar las restricciones escolares vigentes. |
| **Origen** | Visión del producto + entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Al escribir la opción correspondiente a las restricciones escolares, deberá mostrarse la lista de restricciones vigentes.<br>• El sistema deberá mostrar únicamente restricciones registradas como vigentes.<br>• La información mostrada deberá corresponder con la información autorizada por Dirección de carrera. |
| **Relacionado con** | RF-001, RF-009, RF-010, RNF-CON-001 |

---

### RF-009 · Mostrar causas de restricción escolar

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mostrar la causa asociada a una restricción escolar cuando dicha información se encuentre disponible. |
| **Origen** | Entrevista |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • El alumno deberá poder escribr una restricción escolar.<br>• El sistema deberá mostrar la causa asociada cuando se encuentre registrada.<br>• El sistema deberá indicar cuando no exista una causa registrada para la restricción seleccionada.<br>• La causa mostrada deberá corresponder con la información autorizada por Dirección de carrera. |
| **Relacionado con** | RF-008, RF-010, RNF-CON-001 |

---

### RF-010 · Modificar información académica

| Campo | Contenido |
|---|---|
| **Descripción** | El sistema deberá mantener actualizada la información académica utilizada para responder las consultas cuando una fuente oficial autorizada modifique dicha información. |
| **Origen** | Visión del producto |
| **Prioridad** | Imprescindible |
| **Criterios de aceptación** | • Cuando una fuente oficial autorizada modifique información académica, deberá registrarse la modificación correspondiente.<br>• La información modificada deberá utilizarse en las consultas posteriores.<br>• La información que no haya sido modificada deberá conservarse sin cambios.<br>• El sistema no deberá utilizar información académica que haya sido sustituida por una versión vigente. |
| **Relacionado con** | RF-002, RF-003, RF-004, RF-005, RF-006, RF-007, RF-008, RF-009, RNF-CON-001 |

---

# 4. Requisitos no funcionales

## 4.1 Resumen

| ID | Atributo | Nombre | Prioridad | Origen |
|---|---|---|---|---|
| RNF-DIS-001 | Disponibilidad | Disponibilidad durante las 24 horas | Imprescindible | Entrevista |
| RNF-USA-001 | Usabilidad | Consulta sin capacitación previa | Importante | Supuesto del equipo + validación pendiente |
| RNF-CON-001 | Confiabilidad | Correspondencia con información oficial | Imprescindible | Visión del producto + entrevista |

---

## 4.2 Fichas

### RNF-DIS-001 · Disponibilidad durante las 24 horas

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Disponibilidad |
| **Descripción** | El agente deberá permanecer disponible para que los alumnos puedan realizar consultas académicas durante cualquier momento del día. |
| **Métrica** | • El agente deberá estar disponible las 24 horas del día, los 7 días de la semana.<br>• La disponibilidad estará sujeta al funcionamiento de Microsoft Teams y de los servicios de Copilot. |
| **Origen** | Entrevista de elicitación |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Los alumnos necesitan consultar información académica sin depender de la disponibilidad inmediata de Dirección de carrera. |
| **Afecta a** | Todo el sistema |

---

### RNF-USA-001 · Consulta sin capacitación previa

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Usabilidad |
| **Descripción** | Un alumno deberá poder consultar la información correspondiente a los servicios principales del agente sin recibir capacitación previa. |
| **Métrica** | • El alumno deberá poder acceder a la información solicitada en un máximo de 3 interacciones con el agente.<br>• El alumno deberá poder completar la consulta utilizando únicamente las opciones y respuestas proporcionadas por el agente. |
| **Origen** | Supuesto del equipo + validación pendiente |
| **Prioridad** | Importante |
| **Por qué importa** | La interacción debe ser sencilla para que los alumnos puedan utilizar el agente sin capacitación previa. El límite de 3 interacciones es un supuesto del equipo y deberá validarse mediante pruebas con usuarios. |
| **Afecta a** | RF-001, RF-002, RF-003, RF-004, RF-005, RF-006, RF-007, RF-008, RF-009 |

---

### RNF-CON-001 · Correspondencia con información oficial

| Campo | Contenido |
|---|---|
| **Atributo de calidad** | Confiabilidad |
| **Descripción** | El agente deberá proporcionar información que corresponda con la información oficial proporcionada y aprobada por Dirección de carrera. |
| **Métrica** | • El 100 % de las respuestas evaluadas deberá corresponder con la información oficial vigente utilizada como fuente.<br>• El agente no deberá presentar como vigente información que haya sido sustituida por una versión actualizada.<br>• El agente no deberá proporcionar información académica que no se encuentre dentro de las fuentes autorizadas. |
| **Origen** | Visión del producto + entrevista |
| **Prioridad** | Imprescindible |
| **Por qué importa** | Una respuesta incorrecta o desactualizada puede generar confusión en los alumnos y proporcionar información que no haya sido autorizada por Dirección de carrera. |
| **Afecta a** | RF-002, RF-003, RF-004, RF-005, RF-006, RF-007, RF-008, RF-009, RF-010 |

---

# 5. Casos de uso

## 5.1 Resumen

| ID | Nombre | Actor principal | Requisitos relacionados |
|---|---|---|---|
| CU-01 | Consultar materias disponibles | Alumno | RF-001, RF-002 |
| CU-02 | Consultar información de una materia | Alumno | RF-002, RF-003 |
| CU-03 | Consultar prerrequisitos de una materia | Alumno | RF-002, RF-004 |
| CU-04 | Consultar trámites disponibles | Alumno | RF-001, RF-005 |
| CU-05 | Consultar información de un trámite | Alumno | RF-005, RF-006 |
| CU-06 | Consultar calendario escolar | Alumno | RF-001, RF-007 |
| CU-07 | Consultar restricciones escolares | Alumno | RF-001, RF-008 |
| CU-08 | Consultar causas de restricción escolar | Alumno | RF-008, RF-009 |
| CU-09 | Modificar información académica | Dirección de carrera | RF-010 |

---

## 5.2 Diagrama de casos de uso

### Actor Alumno

- CU-01 · Consultar materias disponibles
- CU-02 · Consultar información de una materia
- CU-03 · Consultar prerrequisitos de una materia
- CU-04 · Consultar trámites disponibles
- CU-05 · Consultar información de un trámite
- CU-06 · Consultar calendario escolar
- CU-07 · Consultar restricciones escolares
- CU-08 · Consultar causas de restricción escolar

### Actor Dirección de carrera

- CU-09 · Modificar información académica

---

## 5.3 Prototipo navegable

El prototipo corresponde al **CU-05 · Consultar información de un trámite** e incluye el escenario principal y los flujos alternos correspondientes a la consulta de información general de un trámite.

---

## CU-05 · Consultar información de un trámite

### Actor principal

Alumno

### Objetivo

Obtener información general sobre un trámite escolar disponible.

### Precondición

- El agente se encuentra disponible.
- El trámite se encuentra registrado como disponible.
- Existe información autorizada sobre el trámite.

### Escenario principal

1. El alumno escribe la opción “Trámites y bajas”.
2. El sistema muestra la lista de trámites disponibles.
3. El alumno escribe el trámite que desea consultar.
4. El sistema identifica el trámite seleccionado.
5. El sistema muestra qué es el trámite.
6. El sistema muestra para qué sirve el trámite.
7. El sistema muestra qué información debe tener disponible el alumno.
8. El sistema muestra a quién debe contactar el alumno para obtener información más específica.
9. El sistema muestra el mensaje: “Si requieres información más específica contacta a tu directora de carrera”.
10. El alumno obtiene la información general disponible sobre el trámite.

### Flujos alternos

**FA-01 · El alumno requiere información más específica**

1. El alumno solicita información que no se encuentra dentro de la información autorizada.
2. El sistema informa al alumno que debe contactar directamente a Dirección de carrera.
3. El sistema no proporciona información adicional que no se encuentre autorizada.

**FA-02 · No existe información suficiente sobre el trámite**

1. El sistema identifica que no existe información autorizada suficiente para responder la consulta.
2. El sistema informa al alumno que debe contactar a Dirección de carrera.
3. El sistema no genera información que no se encuentre registrada en las fuentes autorizadas.

### Postcondición

- El alumno obtiene la información general disponible sobre el trámite.
- Si la información solicitada se encuentra fuera del alcance autorizado, el alumno es dirigido a Dirección de carrera.

### Requisitos que realiza

RF-005, RF-006

## Figma:https://www.figma.com/proto/SCYiz3nCxSqjktAWXtbIhz/Prototipo-Agente-de-atenci%C3%B3n-acad%C3%A9mica?node-id=1-5145&t=RD9Xxfk5GiKQwI9E-0&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=1%3A5145
---

# 6. Trazabilidad

| Requisito | Caso de uso | Actor | Prototipo |
|---|---|---|---|
| RF-001 | CU-01, CU-04, CU-06, CU-07 | Alumno | Menú principal |
| RF-002 | CU-01, CU-02, CU-03 | Alumno | No hay |
| RF-003 | CU-02 | Alumno | No hay |
| RF-004 | CU-03 | Alumno | No hay |
| RF-005 | CU-04, CU-05 | Alumno | Menú principal / Lista de trámites |
| RF-006 | CU-05 | Alumno | Información del trámite |
| RF-007 | CU-06 | Alumno | No hay |
| RF-008 | CU-07, CU-08 | Alumno | No hay |
| RF-009 | CU-08 | Alumno | No hay |
| RF-010 | CU-09 | Dirección de carrera | No hay |
| RNF-DIS-001 | CU-01 a CU-09 | Alumno / Dirección de carrera | No aplica |
| RNF-USA-001 | CU-01 a CU-08 | Alumno | No aplica |
| RNF-CON-001 | CU-01 a CU-09 | Alumno / Dirección de carrera | No aplica |

---

# 7. Registro de cambios

| Fecha | Requisito / Documento | Qué cambió | Por qué |
|---|---|---|---|
| 08/09/2026 | Descripción del sistema | Se cambió la denominación de “bot” a “agente de Copilot”. | Se ajustó la descripción del sistema a la solución solicitada por Dirección. |
| 08/09/2026 | Tipo de sistema / metodología | Se cambió la metodología de prototipado rápido a metodología ágil – desarrollo incremental. | Se determinó que el proyecto se desarrollará progresivamente, permitiendo validar y modificar cada incremento. |
| 22/09/2026 | Requisitos | Se estableció la nomenclatura RF-### para requisitos funcionales y RNF-###-### para requisitos no funcionales. | Se adoptó una identificación única y estable para facilitar la trazabilidad. |
| 22/09/2026 | Requisitos | Se estableció que cada requisito debe expresar una sola idea y contar con un criterio de aceptación comprobable. | Se ajustó la redacción de requisitos a los criterios establecidos para el proyecto. |
| 22/09/2026 | Requisitos | Se estableció que el campo Origen debe distinguir entre información confirmada y supuestos del equipo. | Se busca diferenciar la información obtenida durante la elicitación de las decisiones pendientes de validación. |
| 24/09/2026 | Información académica | Se identificó que para orientar a un alumno sobre las materias que puede cursar se consideran promedio, acreditación de español e inglés, créditos, semestre, materias específicas y prerrequisitos. | La entrevista permitió identificar información académica adicional relevante para las consultas. |
| 24/09/2026 | RF-007 | Se identificó que el calendario utilizado por Dirección proviene de la fuente oficial correspondiente. | La entrevista permitió identificar la fuente utilizada para determinar la información vigente. |
| 24/09/2026 | RF-010 | Se identificó que las modificaciones de información pueden producirse por cambios de normatividad y por Administración Escolar. | La entrevista permitió identificar situaciones que pueden provocar modificaciones en la información académica. |
| 24/09/2026 | Casos de uso | Se definieron los objetivos principales de los actores y su relación con los requisitos funcionales. | Se estableció la trazabilidad entre requisitos y casos de uso. |
| 28/09/2026 | Prototipo navegable | Se desarrolló un prototipo navegable para la consulta de información de un trámite. | Se construyó el prototipo solicitado para validar la interacción principal del agente. |
| 30/09/2026 | Requisitos funcionales | Se aumentó el número de requisitos funcionales a diez y se descompusieron las funcionalidades en objetivos independientes. | La rúbrica establece un mínimo de diez requisitos funcionales y cada requisito debe expresar una sola idea. |
| 30/09/2026 | RF-003 | Se incorporó el requisito Consultar información de una materia. | Se identificó como una consulta independiente relacionada con conocer qué es y para qué sirve una materia. |
| 30/09/2026 | RF-004 | Se incorporó el requisito Consultar prerrequisitos de una materia. | Se identificó como una consulta independiente a partir de la información obtenida durante la entrevista. |
| 30/09/2026 | RF-009 | Se incorporó el requisito Consultar causas de restricciones escolares. | Se identificó como un objetivo de consulta independiente respecto a la consulta de las restricciones. |
| 30/09/2026 | Requisitos no funcionales | Se separaron las métricas en puntos individuales. | Se buscó facilitar la comprobación de cada métrica y mantener consistencia con la estructura de los criterios de aceptación. |
| 30/09/2026 | Casos de uso | Se establecieron nueve casos de uso correspondientes a los objetivos concretos de los actores. | Se estableció una relación directa entre los objetivos de los actores y los requisitos funcionales. |
