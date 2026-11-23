# HU-01: Registro de usuario

| Campo | Valor |
|-------|-------|
| **ID** | HU-01 |
| **Funcionalidad** | Registro de usuario |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos |
| **Rol** | Cliente visitante |

## Historia

**Como** cliente visitante,
**quiero** crear una cuenta con mi email y una contraseña,
**para** poder hacer pedidos de café y panadería y recogerlos en el local.

## Flujo guiado

1. El usuario pulsa **"Crear cuenta"** en la pantalla de inicio.
2. Ingresa su nombre, email, contraseña y confirmación de contraseña.
3. Acepta los términos y condiciones.
4. Pulsa **"Registrarme"**.
5. El sistema crea la cuenta, muestra un mensaje de bienvenida y lo lleva al menú.

## Criterios de aceptación

### CA-01.1: Registro exitoso
- **Dado** que estoy en el formulario de registro
- **Cuando** ingreso un nombre, un email válido no registrado y una contraseña que cumple los requisitos, y pulso "Registrarme"
- **Entonces** el sistema crea mi cuenta, muestra el mensaje "¡Bienvenido a LePetitDep!" y me redirige al menú con la sesión iniciada.

### CA-01.2: Email con formato inválido
- **Dado** que estoy en el formulario de registro
- **Cuando** ingreso un email sin formato válido (por ejemplo, `cliente@correo`)
- **Entonces** el sistema muestra "Ingresa un email válido" junto al campo y no permite enviar el formulario.

### CA-01.3: Email ya registrado
- **Dado** que ya existe una cuenta con el email `ana@correo.com`
- **Cuando** intento registrarme con ese mismo email
- **Entonces** el sistema muestra "Este email ya está registrado" y ofrece un enlace a "Iniciar sesión".

### CA-01.4: Contraseña que no cumple los requisitos
- **Dado** que estoy en el formulario de registro
- **Cuando** ingreso una contraseña de menos de 8 caracteres o sin al menos una letra y un número
- **Entonces** el sistema indica qué requisito falta y no crea la cuenta.

### CA-01.5: Las contraseñas no coinciden
- **Dado** que estoy en el formulario de registro
- **Cuando** la contraseña y su confirmación son diferentes
- **Entonces** el sistema muestra "Las contraseñas no coinciden" y no crea la cuenta.

### CA-01.6: Campos obligatorios
- **Dado** que estoy en el formulario de registro
- **Cuando** dejo vacío algún campo obligatorio o no acepto los términos
- **Entonces** el botón "Registrarme" permanece deshabilitado y el campo faltante se marca en rojo.

### CA-01.7: Seguridad de la contraseña
- **Dado** que me registré correctamente
- **Cuando** el sistema guarda mi cuenta
- **Entonces** la contraseña se almacena cifrada (hash) y nunca se muestra en texto plano.
