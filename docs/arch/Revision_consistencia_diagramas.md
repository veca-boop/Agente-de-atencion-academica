# Revisión de consistencia de diagramas

**Proyecto:** Agente de Atención Académica en Copilot  
**Materia:** SIS3407 – Ingeniería de Software I

## 1. Consistencia entre el diagrama de clases y el diagrama de secuencia

Se revisa que los mensajes enviados a las clases durante la interacción correspondan con las operaciones definidas en el diagrama de clases.

**Hallazgo:**

En el diagrama de secuencia, el agente solicita información a la clase `Materia` mediante la operación `consultarInformacion(codigo)`.

Al revisar el diagrama de clases, se identificó que la operación originalmente estaba definida sin parámetros:

`consultarInformacion(): String`

**Corrección realizada:**

Se actualizó la operación para incluir el parámetro necesario:

`consultarInformacion(codigo: String): String`

De esta manera, el mensaje del diagrama de secuencia coincide con la operación definida en la clase `Materia`.

Los mensajes relacionados con la recepción de consultas y la presentación de respuestas corresponden a las interacciones entre Microsoft Teams y el agente, por lo que no representan operaciones de las clases del dominio.

**Resultado:** Consistente después de la corrección.

## 2. Consistencia entre el diagrama de clases y el diagrama de estados

Se revisa si alguna de las clases del modelo tiene atributos que representen estados o etapas de un ciclo de vida que requieran una máquina de estados.

**Revisión realizada:**

Se analizaron las seis clases del modelo:

- `Materia`
- `Docente`
- `Horario`
- `Tramite`
- `CalendarioEscolar`
- `RestriccionEscolar`

Ninguna contiene un atributo que represente un estado ni se ha definido un ciclo de vida con transiciones entre estados.

**Decisión:**

No se elaborará un diagrama de estados, ya que no existe una clase que requiera representar este comportamiento en el modelo actual.

**Resultado:** No aplica.

## 3. Consistencia entre los diagramas y los casos de uso

Se verifica que los diagramas elaborados representen funcionalidades identificadas previamente en el diagrama de casos de uso de la Unidad 2.

**Caso de uso seleccionado:**

`Consultar información de una materia`.

**Revisión realizada:**

- **Diagrama de secuencia:** representa la interacción entre el alumno, Microsoft Teams, el Agente de Atención Académica y la clase `Materia` para consultar información.
- **Diagrama de actividad:** representa el flujo de la consulta, desde que el alumno escribe su solicitud hasta que recibe una respuesta o un mensaje de información no disponible.
- **Diagrama de clases:** contiene la clase `Materia` y la operación `consultarInformacion(codigo: String)`, necesarias para representar la consulta.

**Resultado:** Consistente. Los diagramas representan el mismo caso de uso definido previamente.

## 4. Resumen de resultados

| Regla de consistencia | Resultado | Acción realizada |
|---|---|---|
| Clases vs. secuencia | Consistente | Se agregó el parámetro `codigo: String` a la operación de `Materia`. |
| Clases vs. estados | No aplica | Ninguna clase tiene atributos de estado ni un ciclo de vida definido. |
| Diagramas vs. casos de uso | Consistente | Se verificó la correspondencia con el caso de uso «Consultar información de una materia». |

## Conclusión

La revisión permitió identificar y corregir una diferencia entre el diagrama de clases y el diagrama de secuencia, relacionada con el parámetro de la operación `consultarInformacion`.

También se comprobó que no es necesario elaborar un diagrama de estados para el modelo actual y que los diagramas de secuencia y actividad corresponden con un caso de uso definido en la Unidad 2.

Con estas revisiones, los diagramas mantienen coherencia entre sus elementos y representan de manera consistente el funcionamiento propuesto para el Agente de Atención Académica en Copilot.
