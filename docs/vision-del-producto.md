# Visión del producto

---

**Autor: Ana Victoria Hernández Álvarez**

**Fecha de la última versión: 8 de septiembre de 2026**

**Repositorio: 
https://github.com/veca-boop/Project.Ingenier-a-de-Software-I**

---

## 1. Descripción del sistema

**Nombre del sistema: Agente de Atención Académica en Copilot**

**Descripción: Es un agente de Copilot integrado en el chat de Microsoft Teams de la directora de carrera que responde automáticamente a las preguntas frecuentes de los alumnos de la carrera de Ingeniería en Tecnologías de la Información sobre temas como trámites, materias, fechas y procesos académicos, utilizando información previamente proporcionada y aprobada por la Dirección de carrera. Cuando Dirección realice cambios en la información, se actualizará únicamente la información afectada antes de que vuelva a ser consultada por los alumnos. Como mínimo, la información será revisada al inicio de cada semestre.**

---

## 2. Problema y usuarios

**El problema: Los alumnos realizan constantemente preguntas similares al director de carrera, lo que genera tiempo de espera y trabajo repetitivo. Para lo cual no tiene tiempo suficiente y por lo tanto no puede dar un servicio personalizado en caso de ser necesario.**

**Cómo se resuelve hoy sin el sistema: Los alumnos tienen que enviar mensajes, correos o preguntar directamente su director/a para obtener respuestas, esperando a que esté disponible y el director/a debe contestar manualmente cada consulta**

**Usuarios del sistema:**

| Tipo de usuario | Qué necesita del sistema | Qué le preocupa |
|---|---|---|
| Alumno | Quieren obtener respuestas rápidas a sus dudas | Que la directora de carrera no esté disponible en ese momento |
| Dirección de carrera | Quiere tener acceso a modificar la información que el bot usa | Asegurar que los alumnos reciban información correcta y actualizada|

**Un conflicto entre usuarios: El alumno quiere que el agente responda la mayor cantidad de preguntas posibles y de manera inmediata, mientras que Dirección necesita limitar las respuestas del agente a información confiable, actualizada y aprobada.**

---

## 3. Alcance

### Dentro del alcance
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

### Explícitamente fuera del alcance

- El agente no te puede hacer el trámite.

- El agente no puede resolver dudas fuera de su menú de servicios.

- El agente no puede dar información detallada de los pasos para ningún trámite.


**Por qué queda fuera:**
El agente está diseñado como una herramienta de apoyo para reducir el tiempo que la directora de carrera dedica a responder preguntas frecuentes. Por lo que su función es proporcionar información académica previamente autorizada, no sustituir la atención directa de la directora ni funcionar como un asistente académico de propósito general.
---

## 4. Tipo de sistema y restricciones

**Tipo de sistema:**

 Web y SaaS  

**Por qué es de ese tipo: El agente funciona como un servicio integrado en el chat de  Microsoft Teams del director de carrera. Por lo cual Los usuarios no necesitan instalar una aplicación independiente. Además, el bot no manipula la información, no tiene grandes riesgos, ni usar un dispositivo físico, sino que el usuario interactúa con el bot directamente desde la plataforma de Teams.**

**Atributos de calidad que impone:**

| Atributo | Por qué importa en mi caso | Qué pasa si no se cumple |
|---|---|---|
|Disponibilidad | El bot debe estar disponible dentro de Teams cuando los usuarios necesiten consultar la información.|Los usuarios no podrán acceder a la información mediante el bot. |
|Usabilidad |Las respuestas deben ser claras y la interacción sencilla para que cualquier usuario pueda utilizarlo. | Los usuarios pueden confundirse o dejar de utilizar el bot.|
|Confiabilidad |El bot debe mostrar correctamente la información proporcionada por Dirección. |Puede generar confusión y hacer que los usuarios reciban información equivocada. |

**Reglas de negocio que ya identifiqué:**

1. El bot debe limitar sus respuestas a las categorías de información autorizadas por Dirección.

2. El bot debe proporcionar respuestas claras y relacionadas con la información solicitada por el usuario.

3. La información proporcionada por el bot debe corresponder a la información oficial proporcionada por Dirección.
   
5. Cuando Dirección modifique información, únicamente deberá actualizarse el contenido afectado antes de que vuelva a ser consultado por los alumnos.

---

## 5. Ciclo de vida elegido

**Modelo elegido: Metodología ágil – Desarrollo incremental (Software a la medida)**

**Por qué le conviene a este proyecto: El desarrollo incremental permite construir el agente de manera progresiva incorporando sus funcionalidades en diferentes etapas. En cada incremento se puede revisar el funcionamiento del agente y obtener retroalimentación de la directora para determinar qué elementos deben mantenerse, modificarse, agregarse o eliminarse. Esto permite que el sistema se adapte a las necesidades reales de los usuarios y que la información proporcionada por el agente sea validada antes de continuar con los siguientes incrementos.**

### Alternativas descartadas

**Alternativa 1: Prototipado rápido**

*Por qué la descarté: Se descartó porque, aunque permite obtener retroalimentación de los usuarios mediante una versión inicial del sistema, su enfoque está principalmente orientado a construir un prototipo para validar la propuesta y desecharla antes de desarrollar la versión definitiva. Para este proyecto resulta más conveniente utilizar un desarrollo incrementa*

**Alternativa 2: Modelo en espiral**

*Por qué la descarté: Se descartó porque está orientado principalmente a proyectos grandes con un nivel elevado de incertidumbre y riesgos técnicos o económicos. Para un agente de Copilot de alcance más limitado, su análisis constante de riesgos y sus iteraciones resultarían innecesariamente complejos.*
