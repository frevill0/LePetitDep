# HU-04: Agregar productos al carrito

| Campo | Valor |
|-------|-------|
| **ID** | HU-04 |
| **Funcionalidad** | Agregar productos al carrito |
| **Prioridad** | Alta |
| **Estimación** | 5 puntos |
| **Rol** | Cliente visitante / Cliente registrado |

## Historia

**Como** cliente,
**quiero** seleccionar productos y la cantidad de cada uno y agregarlos a un carrito,
**para** armar mi pedido antes de confirmarlo.

## Flujo guiado

1. Desde el menú o el detalle de un producto, el usuario elige la cantidad con los botones **"−"** y **"+"**.
2. Pulsa **"Agregar al carrito"**.
3. El ícono del carrito se actualiza con el número de productos.
4. El usuario abre el carrito, revisa los productos, ajusta cantidades o elimina productos.
5. Pulsa **"Continuar con el pedido"**.

## Criterios de aceptación

### CA-04.1: Agregar un producto
- **Dado** que estoy viendo un producto disponible
- **Cuando** elijo una cantidad y pulso "Agregar al carrito"
- **Entonces** el producto se añade al carrito, aparece el mensaje "Producto agregado" y el contador del ícono del carrito aumenta.

### CA-04.2: Límites de cantidad
- **Dado** que estoy eligiendo la cantidad de un producto
- **Cuando** uso los botones "−" y "+"
- **Entonces** la cantidad mínima es 1 y la máxima es 10 por producto.

### CA-04.3: Agregar un producto que ya está en el carrito
- **Dado** que ya tengo 2 capuchinos en el carrito
- **Cuando** agrego 1 capuchino más
- **Entonces** el carrito muestra una sola línea de capuchino con cantidad 3, no dos líneas separadas.

### CA-04.4: Ver el contenido del carrito
- **Dado** que tengo productos en el carrito
- **Cuando** abro el carrito
- **Entonces** veo cada producto con su nombre, cantidad, precio unitario y subtotal, además del total del pedido.

### CA-04.5: Modificar la cantidad en el carrito
- **Dado** que estoy en el carrito
- **Cuando** cambio la cantidad de un producto
- **Entonces** el subtotal de ese producto y el total del pedido se recalculan al instante.

### CA-04.6: Eliminar un producto
- **Dado** que estoy en el carrito
- **Cuando** pulso "Eliminar" en un producto
- **Entonces** el producto desaparece del carrito y el total se actualiza.

### CA-04.7: Carrito vacío
- **Dado** que no tengo productos en el carrito
- **Cuando** abro el carrito
- **Entonces** veo el mensaje "Tu carrito está vacío", un botón "Ver menú" y el botón "Continuar con el pedido" está deshabilitado.

### CA-04.8: Conservar el carrito
- **Dado** que agregué productos al carrito
- **Cuando** navego a otra sección o recargo la página
- **Entonces** los productos siguen en el carrito.
