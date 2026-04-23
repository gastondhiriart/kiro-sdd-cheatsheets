# Specs

Un spec es un conjunto de documentos que separa intención, diseño y ejecución.

## Estructura

```
.kiro/specs/<feature>/
├── requirements.md    — Qué se necesita
├── design.md          — Cómo se implementa
└── tasks.md           — Pasos de ejecución
```

No siempre se usan todos. Lo importante es separar pensar, diseñar y ejecutar.

## Flujo base

1. **Requirements** — Lenguaje claro, idealmente con notación EARS. Define comportamiento y criterios de aceptación.
2. **Design** — Arquitectura, endpoints, contratos, decisiones técnicas.
3. **Tasks** — Tareas pequeñas, ordenadas, con dependencias visibles.

## Dos formas de arrancar

### Behavior-first

Primero definís qué debería pasar, después diseñás la solución.

Conviene cuando:
- El comportamiento está claro
- Producto manda más que la técnica
- La solución técnica es flexible

Secuencia: requirements → design → tasks

### Design-first

Primero definís restricciones técnicas y contratos, después aterrizás requisitos.

Conviene cuando:
- Hay APIs externas o contratos fijos
- El problema está dominado por restricciones técnicas
- Es un spike o integración

Secuencia: design → requirements → tasks

**Regla práctica:** si entendés mejor el comportamiento → behavior-first. Si entendés mejor las restricciones → design-first.

## Tipos de specs

| Tipo | Cuándo | Foco |
|------|--------|------|
| Feature | Nueva funcionalidad | Construir algo nuevo |
| Bugfix | Bugs, regresiones | Corregir sin rediseñar |
| Correctness | Inconsistencias entre módulos | Alinear y estabilizar |

## Dependencias entre tasks

En specs complejos, dejar visibles:
- Dependencias entre tasks
- Impactos en contratos compartidos
- Decisiones que afectan a más de un task

Si una decisión afecta varios tasks, no la entierres en uno solo.

## Anti-patrones

- Saltarse requirements → código sin intención clara
- Saltarse design → arquitectura improvisada
- Tasks demasiado grandes → ejecución caótica
- No dejar visibles conflictos entre tasks → cada task parece correcta sola, pero el conjunto falla
