# Actividad: Diagramas con Mermaid

## 1. Diagrama de contexto

```mermaid
flowchart TD
    rec([Recepcionista])
    vet([Veterinario])
    sis[Sistema de la clínica]
    lab[Laboratorio externo]
    pago[Pasarela de pagos]
    dueno([Dueño de mascota])

    rec -->|agenda y cobra| sis
    vet -->|consulta expedientes| sis
    sis -->|envía estudios| lab
    sis -->|cobra consultas| pago
    dueno -->|solicita cita| sis

    style sis fill:#ff5d00,color:#fff
```

**Cambios realizados:**
1. Se agregó una caja: `Dueño de mascota`.
2. Se agregó la etiqueta `solicita cita` a la nueva relación.
3. Se eliminó la flecha `Veterinario --> Sistema de la clínica` para mostrar una versión alternativa en la que el veterinario no interactúa directamente con el sistema.

## 2. Diagrama de contenedores

```mermaid
flowchart TD
    rec([Recepcionista])

    subgraph sistema[Sistema de la clínica]
        web[App web<br/>React]
        api[API<br/>Node.js]
        db[(Base de datos<br/>PostgreSQL)]
        notif[Servicio de notificaciones]
    end

    lab[Laboratorio externo]

    rec -->|usa| web
    web -->|HTTPS/JSON| api
    api -->|lee y escribe| db
    api -->|SFTP| lab
    api -->|envía avisos| notif

    style api fill:#ff5d00,color:#fff
```

**Cambios realizados:**
1. Se agregó el contenedor `Servicio de notificaciones`.
2. Se agregó la etiqueta `envía avisos` a la relación entre la API y el nuevo contenedor.
3. Se eliminó la flecha `API --> Laboratorio externo` para mostrar una versión alternativa sin la comunicación directa con el laboratorio.

## 3. Diagrama de componentes

```mermaid
flowchart TD
    web[App web]

    subgraph api[API del sistema]
        agenda[Agenda<br/>citas y horarios]
        cobros[Cobros<br/>cuentas y pagos]
        exp[Expedientes<br/>historial clínico]
        notif[Notificador<br/>interfaz de envío]
        record[Recordatorios<br/>avisos de citas]
    end

    db[(Base de datos)]
    correo[Servicio de correo]

    web --> agenda
    web --> cobros
    web --> exp
    cobros -->|pregunta qué se atendió| agenda
    cobros -->|enviarRecibo| notif
    notif --> correo
    agenda --> db
    cobros --> db
    exp --> db
    agenda -->|programa avisos| record
    record --> correo

    style cobros fill:#ff5d00,color:#fff
```

**Cambios realizados:**
1. Se agregó el componente `Recordatorios`.
2. Se cambió la etiqueta `pregunta que se atendió` por `pregunta qué se atendió`.
3. Se eliminó la flecha `Expedientes --> Base de datos` para mostrar una versión alternativa sin esa conexión directa.

## 4. Diagrama de flujo con decisiones

```mermaid
flowchart TD
    ini([Inicio])
    val{¿Monto mayor a cero?}
    exc{¿Excede el saldo?}
    apl[Aplicar el abono]
    recibo[Generar recibo]
    err1[Monto inválido]
    err2[Excede el saldo]
    fin([Fin])

    ini --> val
    val -->|No| err1
    val -->|Sí| exc
    exc -->|Sí| err2
    exc -->|No| apl
    apl --> recibo
    recibo --> fin
    err1 --> fin
    err2 --> fin

    style apl fill:#ff5d00,color:#fff
```

**Cambios realizados:**
1. Se agregó la caja `Generar recibo`.
2. Se modificó la etiqueta de la decisión a `¿Monto mayor a cero?`.
3. Se eliminó la flecha directa de `apl` a `fin`.

## 5. Diagrama de secuencia

```mermaid
sequenceDiagram
    actor Rec as Recepcionista
    participant Web as App web
    participant Cob as Cobros
    participant Age as Agenda
    participant BD as Base de datos
    participant Not as Notificador

    Rec->>Web: Registra un abono de 500
    Web->>Cob: abonar(cuenta, 500)
    Cob->>Age: ¿Qué servicio se atendió?
    Age-->>Cob: Consulta general
    Cob->>BD: Guarda el pago
    Cob->>Not: Solicita enviar recibo
    Not-->>Cob: Recibo enviado
    Cob-->>Web: Pago registrado
    Web-->>Rec: Muestra el nuevo saldo
```

**Cambios realizados:**
1. Se agregó el participante `Notificador`.
2. Se cambió la etiqueta del mensaje a `¿Qué servicio se atendió?`.
3. Se eliminó la respuesta `BD-->>Cob: Listo`.

## 6. Diagrama de clases

```mermaid
classDiagram
    class CuentaDePaciente {
        -saldo: double
        -pagos: List~Pago~
        +abonar(monto) string
        +consultarSaldo() double
    }

    class Pago {
        -monto: double
        -fecha: Date
        +consultarComprobante() string
    }

    class Paciente {
        -nombre: string
        -especie: string
    }

    class Veterinario {
        -nombre: string
        +consultarPaciente() string
    }

    Paciente "1" --> "1" CuentaDePaciente : tiene
    Veterinario "1" --> "*" Paciente : atiende
```

**Cambios realizados:**
1. Se agregó la clase `Veterinario`.
2. Se agregó la relación entre `Veterinario` y `Paciente`, con la etiqueta `atiende`.
3. Se eliminó la relación entre `CuentaDePaciente` y `Pago`.

## 7. Diagrama de estados

```mermaid
stateDiagram-v2
    [*] --> Agendada
    Agendada --> Confirmada: el dueño confirma
    Agendada --> Cancelada: se cancela a tiempo
    Confirmada --> Atendida: el paciente llega a consulta
    Confirmada --> NoAsistio: no se presenta
    Atendida --> EnRevision: se revisa el expediente
    EnRevision --> [*]
    Cancelada --> [*]
    NoAsistio --> [*]
```

**Cambios realizados:**
1. Se agregó el estado `EnRevision`.
2. Se cambió la etiqueta a `el paciente llega a consulta`.
3. Se eliminó la transición directa `Atendida --> [*]` para que el proceso pase por `EnRevision`.

## 8. Diagrama entidad-relación

```mermaid
erDiagram
    PACIENTE ||--o{ CITA : tiene
    CITA ||--o| EXPEDIENTE : documenta
    CUENTA ||--o{ PAGO : registra
    VETERINARIO ||--o{ CITA : atiende

    PACIENTE {
        int id
        string nombre
        string especie
    }

    CITA {
        int id
        date fecha
        string motivo
    }

    PAGO {
        int id
        decimal monto
        date fecha
    }

    VETERINARIO {
        int id
        string nombre
        string especialidad
    }
```

**Cambios realizados:**
1. Se agregó la entidad `VETERINARIO`.
2. Se cambió la etiqueta de la relación entre `CITA` y `EXPEDIENTE` de `genera` a `documenta`.
3. Se eliminó la relación entre `PACIENTE` y `CUENTA`.
