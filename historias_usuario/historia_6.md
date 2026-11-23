# HU-06: Historial de pedidos

| Campo | Valor |
|-------|-------|
| **ID** | HU-06 |
| **Funcionalidad** | Historial de pedidos |
| **Prioridad** | Media |
| **Estimación** | 3 puntos |
| **Rol** | Cliente registrado |

## Historia

**Como** cliente registrado,
**quiero** consultar mis órdenes anteriores,
**para** revisar lo que pedí, cuánto pagué y el estado de mis pedidos.

## Flujo guiado

1. El usuario entra a **"Mi cuenta" → "Historial de pedidos"**.
2. Ve la lista de sus órdenes, de la más reciente a la más antigua.
3. Pulsa una orden para ver su detalle.
4. Desde el detalle puede pulsar **"Volver a pedir"** para cargar los mismos productos en el carrito.

## Criterios de aceptación

### CA-06.1: Ver la lista de pedidos
- **Dado** que tengo la sesión iniciada y he realizado pedidos
- **Cuando** entro a "Historial de pedidos"
- **Entonces** veo mis órdenes ordenadas de la más reciente a la más antigua, cada una con número de orden, fecha, total y estado.

### CA-06.2: Solo mis pedidos
- **Dado** que tengo la sesión iniciada
- **Cuando** consulto el historial
- **Entonces** solo veo las órdenes de mi cuenta y nunca las de otros usuarios.

### CA-06.3: Detalle de una orden
- **Dado** que estoy en el historial
- **Cuando** pulso una orden
- **Entonces** veo los productos, cantidades, precios, total, método de pago, hora de recogida y estado.

### CA-06.4: Estados del pedido
- **Dado** que estoy viendo una orden
- **Cuando** se muestra su estado
- **Entonces** aparece uno de estos valores: "Recibido", "En preparación", "Listo para recoger", "Entregado" o "Cancelado".

### CA-06.5: Historial vacío
- **Dado** que aún no he hecho ningún pedido
- **Cuando** entro a "Historial de pedidos"
- **Entonces** veo el mensaje "Aún no tienes pedidos" y un botón "Ver menú".

### CA-06.6: Volver a pedir
- **Dado** que estoy en el detalle de una orden anterior
- **Cuando** pulso "Volver a pedir"
- **Entonces** los productos disponibles de esa orden se agregan al carrito y se me avisa si alguno está agotado.

### CA-06.7: Paginación
- **Dado** que tengo más de 10 órdenes
- **Cuando** entro al historial
- **Entonces** se muestran 10 órdenes por página con controles para ver las siguientes.
