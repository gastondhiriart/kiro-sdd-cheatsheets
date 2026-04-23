# Manejo de contexto

En chats largos el agente pierde foco, mezcla conceptos y alucina más. Esto se llama context drift.

## Estrategias

### Chats separados por tema

Si necesitás resolver una duda lateral (ej: entender cómo funciona una API), abrí un chat nuevo. Resolvé ahí y volvé al chat principal limpio.

No mezcles exploración con implementación en el mismo hilo.

### Subagentes

Kiro puede usar instancias paralelas con contexto aislado cuando ejecuta tasks complejas. Cada una trabaja sin contaminar a las otras.

Esto pasa internamente — no los invocás manualmente.

### Mantener el contexto enfocado

- Usá `#File` para inyectar archivos específicos en vez de que el agente busque
- Usá `#Terminal` para compartir errores sin copiar/pegar
- Usá `#Git Diff` para reviews
- Los steerings con `inclusion: always` se cargan automáticamente sin que tengas que repetir reglas

## Regla práctica

- Un chat = un tema o una task
- Si el chat se puso largo y confuso, empezá uno nuevo
- Los steerings mantienen el contexto estable entre chats
