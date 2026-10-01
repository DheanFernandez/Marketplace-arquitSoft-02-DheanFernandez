# Estilo Arquitectónico

## Estilo seleccionado

Se selecciona un estilo arquitectónico basado en **monolito modular con arquitectura en capas**.

## Descripción

El sistema se implementará inicialmente como una única aplicación desplegable, pero organizada internamente en módulos funcionales independientes.

La solución se estructura en capas para separar las responsabilidades principales del sistema y facilitar su mantenimiento y evolución.

## Capas principales

### Presentación
Contiene las interfaces utilizadas por los usuarios del sistema.

### Aplicación
Coordina los casos de uso y las operaciones del sistema.

### Dominio
Contiene las reglas de negocio, entidades y lógica principal.

### Infraestructura
Gestiona la comunicación con base de datos, servicios externos, APIs y demás tecnologías.

## Justificación

Este estilo permite mantener una solución simple de desplegar, pero con una estructura organizada y modular.

Además, facilita el mantenimiento, las pruebas y la futura evolución de determinados módulos.

## Relación con los drivers arquitectónicos

- DA01 - Escalabilidad.
- DA02 - Rendimiento.
- DA03 - Seguridad.
- DA04 - Integración con pagos.
- DA05 - API REST.
- DA06 - Mantenibilidad.

## Diagrama general

```mermaid
flowchart TD

    U[Usuarios] --> P[Presentación]

    P --> A[Aplicación]

    A --> D[Dominio]

    A --> I[Infraestructura]

    I --> DB[(Base de Datos)]
    I --> PAY[Pasarela de Pago]
    I --> EXT[Servicios Externos]