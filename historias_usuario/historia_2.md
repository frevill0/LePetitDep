# HU-02: Inicio de sesión

| Campo | Valor |
|-------|-------|
| **ID** | HU-02 |
| **Funcionalidad** | Inicio de sesión |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos |
| **Rol** | Cliente registrado |

## Historia

**Como** cliente registrado,
**quiero** iniciar sesión de forma segura con mi email y contraseña,
**para** acceder a mi cuenta, hacer pedidos y consultar mis órdenes.

## Flujo guiado

1. El usuario pulsa **"Iniciar sesión"**.
2. Ingresa su email y contraseña.
3. Pulsa **"Entrar"**.
4. El sistema valida las credenciales y lo lleva al menú con su nombre visible en el encabezado.

## Criterios de aceptación

### CA-02.1: Inicio de sesión exitoso
- **Dado** que tengo una cuenta registrada
- **Cuando** ingreso mi email y contraseña correctos y pulso "Entrar"
- **Entonces** el sistema inicia mi sesión, muestra "Hola, [nombre]" en el encabezado y me redirige al menú.

### CA-02.2: Credenciales incorrectas
- **Dado** que estoy en la pantalla de inicio de sesión
- **Cuando** ingreso un email o una contraseña incorrectos
- **Entonces** el sistema muestra "Email o contraseña incorrectos" sin indicar cuál de los dos falló.

### CA-02.3: Campos vacíos
- **Dado** que estoy en la pantalla de inicio de sesión
- **Cuando** dejo vacío el email o la contraseña
- **Entonces** el botón "Entrar" permanece deshabilitado.

### CA-02.4: Bloqueo por intentos fallidos
- **Dado** que he fallado el inicio de sesión 5 veces seguidas
- **Cuando** intento entrar por sexta vez
- **Entonces** el sistema bloquea temporalmente el acceso por 15 minutos y muestra un mensaje informándolo.

### CA-02.5: Ocultar y mostrar contraseña
- **Dado** que estoy escribiendo mi contraseña
- **Cuando** pulso el ícono del ojo
- **Entonces** la contraseña se muestra u oculta, y por defecto aparece oculta.

### CA-02.6: Cierre de sesión
- **Dado** que tengo la sesión iniciada
- **Cuando** pulso "Cerrar sesión"
- **Entonces** el sistema termina mi sesión y me lleva a la pantalla de inicio.

### CA-02.7: Expiración de sesión
- **Dado** que tengo la sesión iniciada
- **Cuando** pasan 30 minutos sin actividad
- **Entonces** la sesión expira y, al intentar una acción protegida, se me pide iniciar sesión de nuevo.

### CA-02.8: Acceso a páginas protegidas
- **Dado** que no he iniciado sesión
- **Cuando** intento entrar a "Realizar pedido" o "Historial de pedidos"
- **Entonces** el sistema me redirige a la pantalla de inicio de sesión y, tras entrar, me devuelve a la página que quería ver.
