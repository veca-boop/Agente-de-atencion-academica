# Especificación de requisitos

---

**Sistema: Agente de atención académica en Copilot**

**Autor: Ana Victoria Hernández Álvarez**

**Versión:** 

**Fecha de la última actualización:**

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

| Usuario	| Qué hace hoy sin el sistema	| Qué espera del sistema |
|---|---|---|
| Alumno | Envía mensajes por Teams o consulta directamente a Dirección para resolver dudas sobre materias, trámites, fechas y restricciones | Obtener información académica de manera rápida sin depender de que Dirección esté disponible |
| Dirección de carrera | Atiende consultas mediante Teams y debe buscar información cuando no la tiene disponible | Reducir consultas repetitivas y proporcionar a los alumnos información previamente validada y actualizada |

**Conflictos identificados entre usuarios:**
1. El alumno busca obtener respuestas rápidas y la mayor cantidad posible de información, mientras que Dirección necesita que las respuestas del agente se limiten a información confiable, vigente y previamente autorizada.

2. La entrevista mostró que actualmente algunas consultas requieren que Dirección busque información antes de responder, pudiendo tardar entre uno y varios días.
   
---

# 3. Requisitos funcionales

### 3.1 Resumen
| ID | Nombre |	Prioridad |	Origen |
|---|---|---|---|
| RF-001 | Menú de servicios | Alta | Visión del producto |			
| RF-002 | Información de materias | Alta | Visión del producto y entrevista |			
| RF-003 | Lista de trámites | Alta | Visión del producto |
| RF-004 | Información general de un trámite | Alta | Visión del producto |
| RF-005 | Calendario y restricciones | Alta | Visión del producto y entrevista |

### 3.2 Fichas

### RF-001 · Menú de servicios

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar un menú con las opciones **Materias**, **Trámites y bajas** y **Calendario y restricciones**. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al iniciar el agente, el usuario podrá visualizar las tres opciones del menú y podrá seleccionar cualquiera de ellas. |
| Relacionado con | RF-002, RF-003, RF-005 |

### RF-002 · Información de materias

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar las materias disponibles de la carrera correspondientes al semestre, junto con sus horarios y maestros. |
| Origen | Visión del producto + entrevista |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar la opción **Materias**, el sistema deberá mostrar la información correspondiente a las materias disponibles del semestre, incluyendo horario y profesor. |
| Relacionado con | RNF-003 |

### RF-003 · Lista de trámites

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la lista de trámites escolares disponibles definida por Dirección. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar **Trámites y bajas**, el sistema deberá mostrar la lista de trámites autorizados por Dirección. |
| Relacionado con | RF-004, RNF-003 |

### RF-004 · Información general de un trámite

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la información general del trámite seleccionado, incluyendo qué es, para qué sirve, qué información debe tener disponible el alumno y a quién debe contactar. |
| Origen | Visión del producto |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar un trámite, el sistema deberá mostrar los cuatro elementos de información definidos para dicho trámite y el mensaje de contacto con Dirección cuando se requiera información más específica. |
| Relacionado con | RF-003, RNF-003 |

### RF-005 · Calendario y restricciones

| Campo | Contenido |
|---|---|
| Descripción | El sistema deberá mostrar la información correspondiente a la opción **Calendario y restricciones** seleccionada por el alumno. |
| Origen | Visión del producto + entrevista |
| Prioridad | Imprescindible |
| Criterio de aceptación | Al seleccionar la opción, el sistema deberá mostrar la información vigente definida para el servicio seleccionado. El calendario utilizado deberá corresponder a la fuente oficial definida por Dirección. |
| Relacionado con | RNF-003 |

---
  
# 4. Requisitos no funcionales

### 4.1 Resumen

| ID | Atributo | Nombre | Prioridad | Origen |
|---|---|---|---|---|
| RNF-DIS-001 | Disponibilidad | Disponibilidad 24 horas | Imprescindible | Entrevista |
| RNF-USA-001 | Usabilidad | Consulta sin capacitación previa | Importante | Supuesto + validación |
| RNF-CON-001 | Confiabilidad | Información oficial | Imprescindible | Visión del producto + entrevista |			
		
### 4.2 Fichas
-Agrupadas por atributo de calidad. Abajo va un ejemplo completo; bórralo cuando escribas los tuyos.

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
-Se trabajan en la semana 7, después de la entrevista. Cada caso de uso se relaciona con los requisitos funcionales que realiza.

---

# 6. Trazabilidad
-Esta tabla es la que hace posible el análisis de impacto de la semana 15. Mantenla actualizada conforme cambien los requisitos.

| Requisito |	Origen |	Caso de uso |	Elemento del prototipo |
|---|---|---|---|
| RF-001 |	Entrevista 15 sep	CU-01 | Registrar consulta |	Pantalla de consulta |

---

# 7. Registro de cambios
-Cada modificación posterior a la primera versión se anota aquí. Un requisito eliminado se marca como tal, pero su identificador no se reutiliza.

| Fecha |	Requisito |	Qué cambió |	Por qué |
|---|---|---|---|

---

Antes de entregar
[ ] Todos los requisitos tienen identificador único y ninguno está repetido
[ ] Cada requisito expresa una sola idea
[ ] Cada requisito funcional tiene criterio de aceptación comprobable
[ ] Cada requisito no funcional tiene una métrica, no solo un adjetivo
[ ] El campo Origen distingue lo confirmado por el cliente de lo que sigo suponiendo
[ ] Hay al menos un requisito no funcional por cada atributo de calidad que impone mi tipo de sistema
[ ] Ningún requisito impone una solución técnica
[ ] Todos los requisitos caben dentro del alcance declarado
[ ] La tabla de trazabilidad está completa
[ ] Mi dupla revisó el documento y su revisión está registrada
[ ] Borré los ejemplos y las instrucciones en cursiva
