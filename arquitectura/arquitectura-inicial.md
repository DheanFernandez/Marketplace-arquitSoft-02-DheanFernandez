# Arquitectura inicial del sistema

## 1. Arquitectura en tres capas

El sistema se organiza inicialmente mediante una arquitectura de tres capas, separando las responsabilidades de presentación, lógica de negocio y acceso a datos.

### Capa de Presentación

Responsable de permitir la interacción de los usuarios con el sistema mediante la aplicación web y la API REST.

### Capa de Lógica de Negocio

Contiene las principales funcionalidades del marketplace:

- Usuarios
- Sellers
- Catálogo
- Carrito
- Pedidos

### Capa de Datos

Responsable de almacenar y consultar la información del sistema mediante una base de datos.

## Organización de las capas

| Capa | Pregunta que responde | Elementos |
|---|---|---|
| Presentación | ¿Cómo interactúa el usuario? | Aplicación Web / API REST |
| Lógica de negocio | ¿Qué hace el sistema? | Usuarios, Sellers, Catálogo, Carrito y Pedidos |
| Datos | ¿Dónde se almacena la información? | Base de datos |