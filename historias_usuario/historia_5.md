# HU-05: Realizar pedido

| Campo | Valor |
|-------|-------|
| **ID** | HU-05 |
| **Funcionalidad** | Realizar pedido |
| **Prioridad** | Alta |
| **Estimación** | 8 puntos |
| **Rol** | Cliente registrado |

## Historia

**Como** cliente registrado,
**quiero** confirmar mi pedido, elegir un método de pago simulado y recibir un número de orden,
**para** recoger mis productos en el local sin hacer fila.

## Flujo guiado

1. Desde el carrito, el usuario pulsa **"Continuar con el pedido"**.
2. **Paso 1 – Resumen:** revisa los productos, cantidades y total.
3. **Paso 2 – Recogida:** elige la hora estimada de recogida en el local.
4. **Paso 3 – Pago simulado:** selecciona un método (tarjeta simulada o pago en el local).
5. **Paso 4 – Confirmación:** pulsa **"Confirmar pedido"**.
6. El sistema muestra el número de orden y el resumen del pedido.

## Criterios de aceptación

### CA-05.1: Requiere sesión iniciada
- **Dado** que no he iniciado sesión y tengo productos en el carrito
- **Cuando** pulso "Continuar con el pedido"
- **Entonces** el sistema me pide iniciar sesión o registrarme y, al hacerlo, conserva mi carrito y me devuelve al pedido.

### CA-05.2: Resumen del pedido
- **Dado** que estoy en el paso de resumen
- **Cuando** se carga la pantalla
- **Entonces** veo cada producto con cantidad y subtotal, el total a pagar y la dirección del local de recogida.

### CA-05.3: Hora de recogida
- **Dado** que estoy en el paso de recogida
- **Cuando** elijo la hora
- **Entonces** solo puedo seleccionar horarios dentro del horario de atención del local y con al menos 15 minutos de anticipación.

### CA-05.4: Selección de método de pago simulado
- **Dado** que estoy en el paso de pago
- **Cuando** veo las opciones
- **Entonces** puedo elegir entre "Tarjeta (simulada)" y "Pagar en el local", y no puedo avanzar sin elegir una.

### CA-05.5: Pago simulado aprobado
- **Dado** que elegí "Tarjeta (simulada)" e ingresé datos de prueba con formato válido
- **Cuando** pulso "Confirmar pedido"
- **Entonces** el sistema simula la aprobación del pago, sin realizar ningún cobro real.

### CA-05.6: Pago simulado rechazado
- **Dado** que elegí "Tarjeta (simulada)" e ingresé datos con formato inválido
- **Cuando** pulso "Confirmar pedido"
- **Entonces** el sistema muestra "Pago rechazado. Revisa los datos o elige otro método", no crea la orden y conserva mi carrito.

### CA-05.7: Número de orden
- **Dado** que el pedido se confirmó correctamente
- **Cuando** se muestra la pantalla de confirmación
- **Entonces** veo un número de orden único (por ejemplo, `LPD-000123`), la hora de recogida, el total y el estado "Recibido".

### CA-05.8: Vaciar el carrito tras confirmar
- **Dado** que el pedido se confirmó correctamente
- **Cuando** vuelvo al menú
- **Entonces** el carrito está vacío.

### CA-05.9: Evitar pedidos duplicados
- **Dado** que pulsé "Confirmar pedido"
- **Cuando** el sistema está procesando la orden
- **Entonces** el botón se deshabilita para que no se cree la misma orden dos veces.

### CA-05.10: Cancelar antes de confirmar
- **Dado** que estoy en cualquier paso antes de la confirmación
- **Cuando** pulso "Volver al carrito"
- **Entonces** regreso al carrito con mis productos intactos y no se crea ninguna orden.
