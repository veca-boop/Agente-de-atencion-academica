# SC-001: Identificación de la fuente y fecha de actualización de información académica

> Solicitud de cambio · Ingeniería de Software I · SIS3407

---

## Estado

Propuesta · 12 de noviembre de 2026

## Quién la pide

**Solicitante:** Julián Guerrero Martínez
**Papel:** Dupla de revisión del sistema Agente de Atención Académica en Copilot.

## Qué se pide

Quiero que los alumnos puedan identificar de dónde proviene la información que proporciona el agente y cuándo fue actualizada por última vez. También quiero que, cuando no se disponga de una fecha de actualización, el agente lo indique para que los alumnos sepan que no es posible confirmar la vigencia de esa información.

## Por qué

Actualmente, el agente proporciona información académica utilizando fuentes autorizadas por la directora de carrera, pero no contempla mostrar al alumno la procedencia ni la fecha de actualización de los datos.

Esto puede generar incertidumbre al consultar información que cambia con el tiempo, como fechas del calendario escolar, horarios, requisitos de trámites y restricciones académicas. Mostrar estos datos permitiría mejorar la transparencia y confiabilidad de las respuestas.

## Qué pasa si no se hace

Los alumnos podrían utilizar información desactualizada sin darse cuenta, especialmente cuando existan modificaciones en fechas, procedimientos o requisitos académicos. Además, no tendrían una referencia clara para comprobar el origen de la información proporcionada por el agente, lo que podría generar confusiones y disminuir la confianza en el sistema.

## Tipo de mantenimiento

- [ ] **Correctivo** · algo está mal y hay que repararlo.
- [ ] **Adaptativo** · el entorno cambió y hay que ajustarse.
- [x] **Perfectivo** · funciona, pero puede ser mejor.
- [ ] **Preventivo** · todavía no falla, pero va a fallar.

**Justificación:** El sistema ya proporciona información académica, pero esta funcionalidad puede mejorarse al permitir que los alumnos conozcan la procedencia y fecha de actualización de las respuestas.

## Criterio de aceptación

1. El agente muestra la fuente institucional de la información proporcionada, cuando esta se encuentra identificada.
2. Cuando la fuente dispone de una fecha de actualización, el agente muestra dicha fecha junto con la respuesta.
3. Cuando no existe una fecha de actualización disponible, el agente informa que no puede confirmar cuándo fue actualizada la información.
4. La información proporcionada continúa utilizando exclusivamente fuentes académicas autorizadas.
5. La consulta de la fuente y su fecha de actualización no modifica la información académica original.
6. La fuente y fecha mostradas corresponden a los datos utilizados para generar la respuesta.

## Prioridad que sugiere el solicitante

**Media.**

El cambio mejoraría la transparencia y confiabilidad de las respuestas, especialmente en consultas sobre información que puede modificarse durante el ciclo escolar. Sin embargo, su ausencia no impide que el agente continúe proporcionando información académica.

---

*La solicitud describe qué se quiere, nunca cómo hacerlo. El cómo se decide en el análisis de impacto, y lo decide quien conoce el diseño.*
