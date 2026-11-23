# LePetitDep ☕🥐

## Descripción

**LePetitDep** es una aplicación web ficticia que permite a los usuarios pedir café y productos de panadería en línea para **recogerlos en el local**. El usuario crea una cuenta, explora el menú, arma su carrito, confirma el pedido con un método de pago simulado y recibe un número de orden para retirar sus productos. Cada funcionalidad inicia con un flujo guiado que acompaña al usuario paso a paso.

Este repositorio contiene las **historias de usuario** y sus **criterios de aceptación** para las funcionalidades principales del sistema.

## Funcionalidades

| # | Funcionalidad | Descripción | Historia |
|---|---------------|-------------|----------|
| 1 | Registro de usuario | Crear una cuenta con email y contraseña. | [HU-01](historias_usuario/historia_1.md) |
| 2 | Inicio de sesión | Acceso seguro con validación de credenciales. | [HU-02](historias_usuario/historia_2.md) |
| 3 | Exploración del menú | Ver la lista de cafés y panadería con precios y descripciones. | [HU-03](historias_usuario/historia_3.md) |
| 4 | Agregar productos al carrito | Seleccionar productos y cantidades. | [HU-04](historias_usuario/historia_4.md) |
| 5 | Realizar pedido | Confirmación, método de pago simulado y número de orden. | [HU-05](historias_usuario/historia_5.md) |
| 6 | Historial de pedidos | Consultar las órdenes anteriores. | [HU-06](historias_usuario/historia_6.md) |

## Estructura del repositorio

```
LePetitDep/
├── historias_usuario/
│   ├── historia_1.md   # Registro de usuario
│   ├── historia_2.md   # Inicio de sesión
│   ├── historia_3.md   # Exploración del menú
│   ├── historia_4.md   # Agregar productos al carrito
│   ├── historia_5.md   # Realizar pedido
│   └── historia_6.md   # Historial de pedidos
└── README.md
```

## Formato de las historias

Cada historia sigue la plantilla:

> **Como** [tipo de usuario], **quiero** [acción], **para** [beneficio].

Los criterios de aceptación están escritos en formato **Dado / Cuando / Entonces** (Gherkin), de modo que puedan verificarse como casos de prueba.

## Roles

- **Cliente visitante:** usuario que aún no tiene cuenta o no ha iniciado sesión.
- **Cliente registrado:** usuario con cuenta activa y sesión iniciada.
