# Especificación de requisitos

---

**Sistema: Agente de atención académica en Copilot**

**Autor: Ana Victoria Hernández Álvarez**

**Versión: 2** 

**Fecha de la última actualización: 27/09/2026**

---

# 1. Propósito y alcance

**Propósito del documento: Documentar los requisitos funcionales y no funcionales del Agente de Atención Académica en Copilot, así como su origen, prioridad, criterios de aceptación y relación con los casos de uso y elementos del prototipo.
El documento está dirigido al equipo encargado del desarrollo del agente y a la Dirección de carrera, con el propósito de mantener una referencia clara de las funcionalidades y características de calidad que deberá cumplir el sistema.**

**Alcance del sistema:** 
El sistema será un agente de Copilot integrado en el chat personal de Microsoft Teams de la directora de carrera de TI, que permitirá a los alumnos consultar información académica previamente proporcionada y aprobada por Dirección de carrera.

- Desplegar un menú de servicios con las sigientes opciones: 

1. Materias.
2. Trámites y bajas.
3. Calendario y restricciones.

- Mostrar lista de materias disponibles de la carrera en el semestre con sus respectivos horarios y maestros.
- Desplegar lista de los siguientes trámites escolares disponibles:

1. BAJA de materias.

2. BAJA de carrera.

3. TRÁMITE de beca escolar. 

4. TRÁMITE para solicitar ser becado de tu director de carrera.

5. JUSTIFICANTE médico o de faltas.

6. INTERCAMBIO para materias de tu carrera.

- Mostrar información general del trámite (qué es, para qué es, qué información debes de tener a la mano y a quién debes contactar para verlo) con un mensaje adjunto que diga: "Si requieres información más específica contacta a tu director de carrera".

- Mostrar calendario escolar.

- Mostrar lista de restricciones escolares con explicación del motivo por el cual puede llegar a ocurrir: inglés o por mala conducta.

**Cuando la información oficial sea modificada, deberá actualizarse la información afectada para evitar que el agente proporcione información anterior.**

**Fuera del alcance:**
1. Realizar trámites en nombre del alumno.
2. Resolver dudas que no correspondan a la información autorizada por Dirección.
3. Proporcionar información detallada de los pasos para realizar un trámite.
4. Sustituir la atención directa de Dirección de carrera.
   
---

# 2. Usuarios y su contexto

| Usuario | Qué hace hoy sin el sistema | Qué espera del sistema |
|---|---|---|
| Alumno | Envía mensajes por Teams o consulta directamente a Dirección para resolver dudas sobre materias, trámites, fechas y restricciones | Obtener información académica de manera rápida sin depender de que Dirección esté disponible |
| Dirección de carrera | Atiende consultas mediante Teams y debe buscar información cuando no la tiene disponible | Reducir consultas repetitivas y proporcionar a los alumnos información previamente validada y actualizada |

**Conflictos identificados entre usuarios:**

1. El alumno busca obtener respuestas rápidas y la mayor cantidad posible de información, mientras que Dirección necesita que las respuestas del agente se limiten a información confiable, vigente y previamente autorizada.

2. La entrevista mostró que actualmente algunas consultas requieren que Dirección busque información antes de responder, pudiendo tardar entre uno y varios días.
   
---

# 3. Requisitos funcionales

### 3.1 Resumen

| ID | Nombre | Prioridad | Origen |
|---|---|---|---|
| RF-001 | Menú de servicios | Imprescindible | Visión del producto |
| RF-002 | Información de materias | Imprescindible | Visión del producto y entrevista |
| RF-003 | Lista de trámites | Imprescindible | Visión del producto |
| RF-004 | Información general de un trámite | Imprescindible | Visión del producto |
| RF-005 | Calendario y restricciones | Imprescindible | Visión del producto y entrevista |
| RF-006 | Actualizar información académica | Imprescindible | Visión del producto |

### 3.2 Fichas

### RF-001 · Menú de servicios

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar un menú con las opciones **Materias**, **Trámites y bajas** y **Calendario y restricciones**. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al iniciar el agente, el usuario podrá visualizar las tres opciones del menú y podrá seleccionar cualquiera de ellas. |
| Relacionado con | RF-002, RF-003, RF-005 |

---

### RF-002 · Información de materias

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar las materias disponibles de la carrera correspondientes al semestre, junto con sus horarios y maestros. |
| Origen | Visión del producto + entrevista |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar la opción **Materias**, el sistema deberá mostrar la información correspondiente a las materias disponibles del semestre, incluyendo horario y profesor. |
| Relacionado con | RNF-CON-001 |

---

### RF-003 · Lista de trámites

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la lista de trámites escolares disponibles definida por Dirección. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar **Trámites y bajas**, el sistema deberá mostrar la lista de trámites autorizados por Dirección. |
| Relacionado con | RF-004, RNF-CON-001 |

---

### RF-004 · Información general de un trámite

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la información general del trámite seleccionado, incluyendo qué es, para qué sirve, qué información debe tener disponible el alumno y a quién debe contactar. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar un trámite, el sistema deberá mostrar los cuatro elementos de información definidos para dicho trámite y el mensaje de contacto con Dirección cuando se requiera información más específica. |
| Relacionado con | RF-003, RNF-CON-001 |

---

### RF-005 · Calendario y restricciones

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la información correspondiente a la opción **Calendario y restricciones** seleccionada por el alumno. |
| Origen | Visión del producto + entrevista |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar la opción, el sistema deberá mostrar la información vigente definida para el servicio seleccionado. El calendario utilizado deberá corresponder a la fuente oficial definida por Dirección. |
| Relacionado con | RNF-CON-001 |

---

### RF-006 · Actualizar información académica

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá permitir actualizar únicamente la información académica que haya sido modificada por Dirección antes de que vuelva a ser consultada por los alumnos. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Cuando Dirección proporcione una modificación de información, el contenido afectado deberá quedar actualizado para las consultas posteriores sin modificar la información que no haya cambiado. |
| Relacionado con | RF-002, RF-003, RF-004, RF-005, RNF-CON-001 |

---
  
# 4. Requisitos no funcionales

### 4.1 Resumen

| ID | Atributo | Nombre | Prioridad | Origen |
|---|---|---|---|---|
| RNF-DIS-001 | Disponibilidad | Disponibilidad 24 horas | Imprescindible | Entrevista |
| RNF-USA-001 | Usabilidad | Consulta sin capacitación previa | Importante | Supuesto + validación |
| RNF-CON-001 | Confiabilidad | Información oficial | Imprescindible | Visión del producto + entrevista |

### 4.2 Fichas

### RNF-DIS-001 · Disponibilidad 24 horas

| Campo | Contenido |
|---|---|
| Atributo de calidad | Disponibilidad |
| Descripción | El agente deberá estar disponible para que los alumnos puedan realizar consultas en cualquier momento. |
| Métrica | Disponibilidad durante las 24 horas del día. |
| Origen | Entrevista de elicitación |
| Prioridad | Imprescindible |
| Por qué importa | Los alumnos necesitan poder consultar información sin depender de la disponibilidad inmediata de Dirección. |
| Afecta a | Todo el sistema |

---

### RNF-USA-001 · Consulta sin capacitación previa

| Campo | Contenido |
|---|---|
| Atributo de calidad | Usabilidad |
| Descripción | Un alumno deberá poder consultar la información de un servicio del menú en un máximo de tres interacciones con el agente, sin recibir instrucciones externas. |
| Métrica | Máximo 3 interacciones. |
| Origen | Supuesto del equipo; pendiente de validación específica |
| Prioridad | Importante |
| Por qué importa | La interacción debe ser sencilla para que los alumnos puedan utilizar el agente sin capacitación previa. |
| Afecta a | RF-001, RF-002, RF-003, RF-005 |

---

### RNF-CON-001 · Información oficial

| Campo | Contenido |
|---|---|
| Atributo de calidad | Confiabilidad |
| Descripción | El agente deberá proporcionar información que corresponda con la información oficial proporcionada y aprobada por Dirección. |
| Métrica | En las pruebas realizadas con información previamente aprobada por Dirección, el agente deberá mostrar la misma información oficial en el 100 % de las consultas correspondientes. |
| Origen | Visión del producto + entrevista |
| Prioridad | Imprescindible |
| Por qué importa | Una respuesta incorrecta o desactualizada puede generar confusión en los alumnos. |
| Afecta a | RF-002, RF-003, RF-004, RF-005 |

---

# 5. Casos de uso

| ID | Nombre | Actor principal | Requisitos relacionados |
|---|---|---|---|
| CU-01 | Consultar materias | Alumno | RF-001, RF-002 |
| CU-02 | Consultar trámites disponibles | Alumno | RF-001, RF-003 |
| CU-03 | Consultar información de un trámite | Alumno | RF-003, RF-004 |
| CU-04 | Consultar calendario escolar | Alumno | RF-001, RF-005 |
| CU-05 | Consultar restricciones | Alumno | RF-001, RF-005 |
| CU-06 | Actualizar información académica | Dirección de carrera | RF-006 |

### Prototipo navegable

[Enlace](https://www.figma.com/proto/SCYiz3nCxSqjktAWXtbIhz/Prototipo-Agente-de-atenci%C3%B3n-acad%C3%A9mica?node-id=1-5145&t=RD9Xxfk5GiKQwI9E-0&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=1%3A5145)

El prototipo corresponde al CU-03 · Consultar información de un trámite e incluye el escenario principal y un flujo alterno para solicitudes de información más específica.

## CU-03 · Consultar información de un trámite

### Actor principal

Alumno

### Objetivo

Obtener información general sobre un trámite escolar disponible.

### Precondición

El agente está disponible y el trámite que desea consultar se encuentra dentro de la información autorizada por Dirección de carrera.

### Escenario principal

1. El alumno selecciona la opción **“Trámites disponibles”**.
2. El sistema muestra la lista de trámites autorizados.
3. El alumno selecciona el trámite que desea consultar.
4. El sistema muestra qué es el trámite, para qué sirve, qué información debe tener disponible y a quién debe contactar.
5. El sistema muestra el mensaje: **“Si requieres información más específica contacta a tu director de carrera”.**
6. El alumno obtiene la información general disponible sobre el trámite.

### Flujos alternos

**1a. El trámite que busca el alumno no está disponible:**  
El sistema informa que el trámite no se encuentra entre los servicios disponibles y mantiene al alumno dentro de la opción de trámites.

**2a. El alumno requiere información más específica:**  
El sistema indica que debe contactar directamente a Dirección de carrera.

### Postcondición

El alumno obtiene la información general disponible sobre el trámite o es dirigido a Dirección de carrera cuando necesita información específica.

### Requisitos que realiza

RF-003, RF-004

---

# 6. Trazabilidad

| Requisito | Origen | Caso de uso | Elemento del prototipo |
|---|---|---|---|
| RF-001 | Visión del producto | CU-01, CU-02, CU-04, CU-05 | Prototipo Figma: Menú principal |
| RF-002 | Visión del producto + entrevista | CU-01 | No hay |
| RF-003 | Visión del producto | CU-02, CU-03 | Prototipo Figma: Menú principal y Lista de trámites |
| RF-004 | Visión del producto | CU-03 | Prototipo Figma: Información del trámite y Flujo alterno |
| RF-005 | Visión del producto + entrevista | CU-04, CU-05 | No hay |
| RF-006 | Visión del producto | CU-06 | No hay |
| RNF-DIS-001 | Entrevista | CU-01, CU-02, CU-03, CU-04, CU-05, CU-06 | No hay |
| RNF-USA-001 | Supuesto + validación pendiente | CU-01, CU-02, CU-03, CU-04, CU-05 | No hay |
| RNF-CON-001 | Visión del producto + entrevista | CU-01, CU-02, CU-03, CU-04, CU-05, CU-06 | No hay |

---

# 7. Registro de cambios

| Fecha | Requisito / Documento | Qué cambió | Por qué |
|---|---|---|---|
| 08/09/2026 | Descripción del sistema | Se cambió la denominación de **“bot”** a **“agente de Copilot”**. | Se ajustó la descripción del sistema a la solución solicitada por Dirección. |
| 08/09/2026 | Tipo de sistema / metodología | Se cambió la metodología de **prototipado rápido** a **metodología ágil – desarrollo incremental (software a la medida)**. | Se determinó que el proyecto se desarrollará progresivamente, permitiendo validar y modificar cada incremento. |
| 22/09/2026 | Requisitos | Se estableció la nomenclatura para los requisitos funcionales y no funcionales: **RF-###** y **RNF-###-###**. | Se adoptó una identificación única y estable para facilitar la trazabilidad. |
| 22/09/2026 | Requisitos | Se estableció que cada requisito debe expresar una sola idea, ser verificable y permanecer dentro del alcance del sistema. | Se ajustó la redacción de requisitos a los criterios establecidos para el proyecto. |
| 22/09/2026 | Requisitos | Se estableció que el campo **Origen** debe distinguir entre información confirmada y deducida. | Se busca diferenciar lo que fue confirmado por Dirección de lo que todavía se está suponiendo. |
| 24/09/2026 | RF-001 | Se definió el requisito **Menú de servicios** con las opciones Materias, Trámites y bajas, y Calendario y restricciones. | Se derivó directamente del alcance establecido en la Visión del producto. |
| 24/09/2026 | RF-002 | Se definió el requisito **Información de materias**, incluyendo materias disponibles, horarios y maestros. | Se retomó la funcionalidad establecida en la Visión y se complementó con la información obtenida en la entrevista. |
| 24/09/2026 | RF-003 | Se definió el requisito **Lista de trámites**. | Se formalizó la lista de trámites escolares que deberá mostrar el agente. |
| 24/09/2026 | RF-004 | Se definió el requisito **Información general de un trámite**, incluyendo qué es, para qué sirve, información necesaria y a quién contactar. | Se formalizó la información que deberá proporcionar el agente sobre cada trámite. |
| 24/09/2026 | RF-005 | Se definió el requisito **Calendario y restricciones**. | Se formalizó el servicio correspondiente al calendario escolar y las restricciones. |
| 24/09/2026 | RNF-DIS-001 | Se confirmó que el agente deberá estar disponible **las 24 horas**. | Dirección confirmó durante la entrevista que los alumnos necesitan consultar la información en todo momento. |
| 24/09/2026 | RNF-USA-001 | Se identificó como supuesto que un alumno debería obtener la información en un máximo de **tres interacciones**. | Se necesitaba convertir la usabilidad en una métrica comprobable; el número de tres interacciones quedó pendiente de validación. |
| 24/09/2026 | RNF-CON-001 | Se definió el requisito de **Confiabilidad**, estableciendo que la información deberá coincidir con la información oficial aprobada por Dirección. | Se confirmó la importancia de utilizar información oficial y previamente aprobada. |
| 24/09/2026 | RF-002 | Se identificó que para orientar actualmente a un alumno sobre las materias que puede cursar se consideran promedio, acreditación de español e inglés, créditos, semestre, materias específicas y prerrequisitos. | La entrevista permitió descubrir información adicional que no estaba contemplada originalmente. |
| 24/09/2026 | RF-005 | Se identificó que el calendario utilizado actualmente por Dirección proviene de la página oficial de Anáhuac Querétaro. | Se confirmó la fuente utilizada para determinar la información vigente del calendario. |
| 24/09/2026 | Actualización de información | Se identificó que los cambios en información de trámites se producen por normatividad y Administración Escolar. | La entrevista permitió conocer el origen de las modificaciones a la información. |
| 27/09/2026 | Casos de uso | Se definieron seis casos de uso: consultar materias, consultar trámites disponibles, consultar información de un trámite, consultar calendario escolar, consultar restricciones y actualizar información académica. | Se tradujeron los requisitos y situaciones identificadas en la entrevista a objetivos completos de los actores. |
| 27/09/2026 | RF-005 | Se separaron los casos de uso de consultar calendario escolar y consultar restricciones, aunque ambos pertenecen al servicio **Calendario y restricciones**. | Se identificaron como dos objetivos distintos que el alumno puede alcanzar mediante el sistema. |
| 27/09/2026 | RF-006 | Se identificó el requisito **Actualizar información académica** como requisito funcional relacionado con el caso de uso CU-06. | El análisis de los casos de uso permitió formalizar como requisito una funcionalidad que ya estaba contemplada en la Visión, pero que no había sido documentada como RF. |
