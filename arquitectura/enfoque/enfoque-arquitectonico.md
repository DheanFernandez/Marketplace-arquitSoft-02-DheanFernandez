# Enfoque Arquitectónico

## Enfoque seleccionado

El sistema utilizará **Clean Architecture** como enfoque para organizar las responsabilidades y dependencias internas.

## Objetivo

Separar las reglas de negocio de los detalles tecnológicos y controlar la dirección de las dependencias del sistema.

## Problema que resuelve

Clean Architecture evita el acoplamiento directo entre:

- Interfaz de usuario.
- Reglas de negocio.
- Base de datos.
- Frameworks.
- APIs.
- Servicios externos.

## Capas definidas

### 1. Dominio

Contiene:

- Entidades.
- Objetos de valor.
- Reglas de negocio.

Ejemplos:

- Usuario.
- Producto.
- Carrito.
- Pedido.
- Pago.

### 2. Aplicación

Contiene los casos de uso del sistema.

Ejemplos:

- Registrar usuario.
- Listar productos.
- Agregar producto al carrito.
- Registrar pedido.
- Procesar pago.

### 3. Presentación

Contiene las interfaces mediante las cuales interactúan los usuarios.

Ejemplos:

- Catálogo.
- Carrito.
- Pantalla de pago.
- Panel de usuario.

### 4. Infraestructura

Contiene las implementaciones concretas relacionadas con tecnologías externas.

Ejemplos:

- Base de datos.
- Cliente HTTP.
- Pasarela de pago.
- Servicios externos.

## Regla de dependencias

Las dependencias deben apuntar hacia el núcleo del sistema.

La capa de dominio no debe depender de infraestructura, frameworks ni interfaces externas.

## Beneficios

- Mejora la mantenibilidad.
- Reduce el acoplamiento.
- Facilita las pruebas unitarias.
- Permite cambiar tecnologías externas con menor impacto.
- Mejora la separación de responsabilidades.

## Diagrama del enfoque

```mermaid
flowchart TD

    P[Presentación] --> A[Aplicación]

    A --> D[Dominio]

    I[Infraestructura] --> A
    I --> D

    DB[(Base de Datos)] --> I
    API[Servicios Externos] --> I
    PAY[Pasarela de Pago] --> I