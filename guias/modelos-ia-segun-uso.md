# Modelos IA según uso

Cómo elegir el modelo correcto según la tarea.

## Modo Auto (recomendado)

Kiro elige el modelo automáticamente según la complejidad de la tarea. Usar como default para el 90% del trabajo.

No usar Auto cuando necesitás control fino del costo o estás en una tarea que requiere máxima precisión.

## Guía por tipo de tarea

| Tarea | Modelo sugerido |
|-------|----------------|
| Requirements complejos | Modelo potente (ej: Opus) |
| Diseño arquitectónico | Modelo potente |
| Debugging difícil | Modelo potente |
| Implementación general | Modelo balanceado (ej: Sonnet) |
| Refactors | Modelo balanceado |
| Tasks repetitivas | Modelo económico |
| Transformaciones simples | Modelo rápido |
| Ejecución masiva de código | Modelo económico |

## Regla mental

- **Pensar** (specs, arquitectura, debugging complejo) → modelo potente
- **Ejecutar** (código, refactors, tasks) → modelo balanceado
- **Rápido** (cosas simples, transformaciones) → modelo económico

## Anti-patrones

- Usar el modelo más potente para todo → caro y lento sin beneficio proporcional
- Usar el modelo más barato para cosas complejas → resultados pobres
- No usar Auto nunca → sobre-optimización innecesaria

## Flujo práctico

1. **Auto** → 90% del tiempo
2. **Modelo potente** → solo para decisiones críticas
3. **Modelo económico** → ejecución masiva
