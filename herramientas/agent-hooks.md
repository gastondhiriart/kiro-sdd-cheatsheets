# Agent Hooks

Callbacks automáticos que se ejecutan cuando ocurren eventos en el IDE.

## Estructura

Los hooks viven en `.kiro/hooks/*.kiro.hook` como archivos JSON.

```json
{
  "name": "Lint on Save",
  "version": "1.0.0",
  "when": {
    "type": "fileEdited",
    "patterns": ["*.ts", "*.tsx"]
  },
  "then": {
    "type": "runCommand",
    "command": "npm run lint"
  }
}
```

## Eventos disponibles

| Evento | Cuándo se dispara |
|--------|------------------|
| `fileEdited` | Al guardar un archivo |
| `fileCreated` | Al crear un archivo nuevo |
| `fileDeleted` | Al borrar un archivo |
| `postToolUse` | Después de que el agente usa una herramienta |
| `preToolUse` | Antes de que el agente use una herramienta |
| `preTaskExecution` | Antes de ejecutar una task de spec |
| `postTaskExecution` | Después de ejecutar una task de spec |
| `promptSubmit` | Al enviar un mensaje en el chat |
| `agentStop` | Cuando el agente termina de ejecutar |
| `userTriggered` | Manual, con botón |

## Tipos de acción

| Tipo | Qué hace | Costo |
|------|----------|-------|
| `runCommand` | Ejecuta un comando en terminal | Gratis (local) |
| `askAgent` | Envía un prompt al agente | Consume créditos |

## Cuándo usar cada tipo

**runCommand (gratis):**
- Lint, type-check, tests
- Validaciones objetivas
- Cualquier cosa que se resuelve con un comando

**askAgent (caro):**
- Análisis que requiere razonamiento
- Sugerencias de mejora
- Revisiones de código

## Regla práctica

- Si corre muchas veces → `runCommand` (no usar IA)
- Si usa IA → que sea manual o en momentos puntuales
- Auto-save + hook con `askAgent` = créditos volando

## Anti-patrones

- No usar hooks → el agente puede ejecutar cosas sin validación
- Hooks demasiado restrictivos → bloquean productividad
- Scripts lentos en hooks → frenan todo el flujo
- `askAgent` en eventos frecuentes → gasto innecesario
