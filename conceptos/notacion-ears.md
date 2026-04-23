# Notación EARS

EARS (Easy Approach to Requirements Syntax) estructura requirements para que sean claros, testeables y sin ambigüedad.

## Patrones

### Ubiquitous — siempre verdadero
`El sistema debe <comportamiento>`
> El sistema debe cifrar todas las contraseñas usando bcrypt.

Usar para: reglas globales, invariantes, seguridad.

### Event-driven — disparado por acción
`Cuando <evento>, el sistema debe <respuesta>`
> Cuando el usuario envía el formulario, el sistema debe validar el email.

Usar para: acciones de usuario, llamadas API, eventos del sistema.

### State-driven — mientras una condición se mantiene
`Mientras <estado>, el sistema debe <respuesta>`
> Mientras el carrito esté vacío, el sistema debe desactivar el botón de checkout.

Usar para: UI dinámica, restricciones de flujo, estados de negocio.

### Unwanted behavior — manejo de fallos
`Si <condición no deseada>, el sistema debe <respuesta>`
> Si el pago falla, el sistema debe rechazar la transacción y registrar el error.

Usar para: edge cases, fallos externos, resiliencia.

### Optional — condicional por configuración
`Donde <condición>, el sistema debe <respuesta>`
> Donde el usuario tenga 2FA habilitado, el sistema debe solicitar un código adicional.

Usar para: feature flags, planes premium, configuraciones opcionales.

## Reglas

- Un requisito = una idea
- Ser específico: qué pasa, cuándo pasa, qué hace el sistema
- Evitar: "manejar correctamente", "validar bien", "optimizar"
- Términos consistentes en todo el spec

## Criterios de aceptación

Cada requisito EARS debería mapearse a:

```
Dado <contexto>
Cuando <acción>
Entonces <resultado esperado>
```

## Dónde encaja en SDD

EARS vive en `requirements.md`. Es especialmente útil en flujos behavior-first. No reemplaza el diseño, pero evita que el diseño arranque sobre ambigüedad.
