# Decisiones Arquitectónicas

Las decisiones arquitectónicas permiten responder a los drivers identificados previamente y establecer cómo se organizará técnicamente el sistema.

## ADR-001: Monolito Modular

**Drivers relacionados:** DA01 - Escalabilidad y DA06 - Mantenibilidad.

### Decisión
Se utilizará un monolito modular, organizando las funcionalidades del sistema en módulos independientes dentro de una misma aplicación desplegable.

### Justificación
Permite mantener una solución sencilla de desarrollar y desplegar, pero con una adecuada separación entre las responsabilidades del sistema.

### Resultado
El sistema estará organizado en módulos como:

- Usuarios
- Catálogo
- Carrito
- Pedidos
- Pagos
- Envíos

---

## ADR-002: Clean Architecture

**Driver relacionado:** DA06 - Mantenibilidad.

### Decisión
Se aplicará Clean Architecture para organizar internamente las responsabilidades y dependencias del sistema.

### Justificación
Permite separar las reglas de negocio de elementos tecnológicos como la interfaz de usuario, la base de datos, frameworks y servicios externos.

### Resultado
La aplicación se organizará en:

- Dominio
- Aplicación
- Infraestructura
- Presentación

Las dependencias deberán orientarse hacia el dominio.

---

## ADR-003: Estrategia de Caché

**Driver relacionado:** DA02 - Rendimiento.

### Decisión
Se incorporará una estrategia de caché para información consultada frecuentemente.

### Justificación
Permite reducir consultas repetitivas a la fuente de datos y mejorar el tiempo de respuesta del sistema.

### Resultado
La información de consulta frecuente podrá recuperarse desde caché antes de realizar una nueva consulta a la fuente de datos.

---

## ADR-004: Integración de Pagos mediante Interfaces y Adaptadores

**Driver relacionado:** DA04 - Integración con pagos.

### Decisión
La comunicación con la pasarela de pagos se realizará mediante interfaces y adaptadores.

### Justificación
Esto permite desacoplar los casos de uso del proveedor de pagos externo.

### Resultado
Se contará con un contrato de pagos y un adaptador encargado de comunicarse con la pasarela externa.