# Steering

Archivos markdown en `.kiro/steering/` que definen reglas, contexto y límites del proyecto. El agente los lee en cada interacción.

## Los 3 archivos base

### `tech.md` — Con qué se construye

- Stack tecnológico
- Herramientas de build, lint, formato
- Variables de entorno
- Comandos comunes

### `product.md` — Qué es el proyecto

- Qué hace el sistema
- Quién lo usa
- Reglas de negocio intocables
- Prioridades del dominio

### `structure.md` — Cómo está organizado

- Estructura de carpetas
- Convenciones de naming
- Patrones de imports
- Restricciones (qué NO hacer)

## Otros steerings útiles

- `workflow.md` — Cuándo planificar vs codear directo
- `ignore.md` — Archivos que el agente no debe tocar
- Steerings específicos por dominio (API design, testing, seguridad)

## Modos de inclusión

| Modo | Comportamiento |
|------|---------------|
| `always` (default) | Se carga en cada interacción |
| `manual` | Se activa con `#` en el chat |
| `fileMatch` | Se activa al editar archivos que matchean un patrón |

Ejemplo de fileMatch:

```md
---
inclusion: fileMatch
fileMatchPattern: "src/api/**"
---

# API Design
- usar JSON:API
- versionado en headers
```

## Reglas para un buen steering

- Ser específico, no genérico ("usar styled-components v6" > "usar buenas prácticas")
- Incluir qué NO hacer, no solo qué hacer
- Documentar decisiones reales del equipo
- Mantenerlo actualizado — un steering desactualizado es peor que no tener uno

## Anti-patrones

- Steering genérico que no dice nada concreto
- No incluir restricciones — el agente se pone creativo donde no debería
- No actualizarlo — el agente toma decisiones sobre un proyecto que ya cambió
