# HU-03: Exploración del menú

| Campo | Valor |
|-------|-------|
| **ID** | HU-03 |
| **Funcionalidad** | Exploración del menú |
| **Prioridad** | Alta |
| **Estimación** | 5 puntos |
| **Rol** | Cliente visitante / Cliente registrado |

## Historia

**Como** cliente,
**quiero** ver la lista de cafés y productos de panadería con sus precios y descripciones,
**para** elegir qué pedir antes de ir al local.

## Flujo guiado

1. El usuario entra a la sección **"Menú"**.
2. Ve los productos organizados por categoría (Cafés, Panadería, Bebidas frías, etc.).
3. Puede filtrar por categoría o buscar por nombre.
4. Pulsa un producto para ver su detalle.
5. Desde el detalle puede pasar a **"Agregar al carrito"**.

## Criterios de aceptación

### CA-03.1: Visualizar el menú
- **Dado** que entro a la sección "Menú"
- **Cuando** la página termina de cargar
- **Entonces** veo los productos agrupados por categoría, cada uno con imagen, nombre, precio y una descripción breve.

### CA-03.2: Formato de precio
- **Dado** que estoy viendo el menú
- **Cuando** se muestra el precio de un producto
- **Entonces** aparece con símbolo de moneda y dos decimales (por ejemplo, `$2.50`).

### CA-03.3: Filtrar por categoría
- **Dado** que estoy en el menú
- **Cuando** selecciono la categoría "Panadería"
- **Entonces** solo se muestran los productos de esa categoría.

### CA-03.4: Buscar un producto
- **Dado** que estoy en el menú
- **Cuando** escribo "capuchino" en el buscador
- **Entonces** se muestran solo los productos cuyo nombre o descripción contienen ese texto.

### CA-03.5: Búsqueda sin resultados
- **Dado** que estoy en el menú
- **Cuando** busco un producto que no existe
- **Entonces** el sistema muestra "No encontramos productos con ese nombre" y una opción para ver todo el menú.

### CA-03.6: Detalle del producto
- **Dado** que estoy en el menú
- **Cuando** pulso un producto
- **Entonces** veo su detalle con nombre, imagen ampliada, descripción completa, precio y el botón "Agregar al carrito".

### CA-03.7: Producto agotado
- **Dado** que un producto no está disponible
- **Cuando** aparece en el menú
- **Entonces** se muestra con la etiqueta "Agotado" y el botón "Agregar al carrito" está deshabilitado.

### CA-03.8: Menú visible sin iniciar sesión
- **Dado** que no he iniciado sesión
- **Cuando** entro a la sección "Menú"
- **Entonces** puedo ver todos los productos, pero al intentar realizar el pedido se me pide iniciar sesión o registrarme.
