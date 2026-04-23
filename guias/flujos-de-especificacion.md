# Flujos de especificación

No todos los cambios se entienden mejor desde el mismo ángulo. Esta guía ayuda a elegir por dónde arrancar un spec.

## Behavior-first (requirements primero)

Primero definís qué debería pasar, qué reglas de negocio aplican, qué criterios de aceptación existen. Después bajás a diseño y tasks.

Conviene cuando:
- Producto manda más que la técnica
- El comportamiento esperado está claro
- Hay libertad para diseñar la solución

Secuencia: requirements → design → tasks

## Design-first (arquitectura primero)

Primero definís contratos externos, restricciones técnicas, arquitectura obligatoria. Después aterrizás requisitos y tasks.

Conviene cuando:
- El trabajo está condicionado por una API externa
- Ya existe un diseño o contrato aprobado
- El problema está dominado por restricciones técnicas

Secuencia: design → requirements → tasks

## Bug-fix flow

Los bugs piden otro camino:
1. Análisis del fallo
2. Delimitación del impacto
3. Corrección acotada
4. Verificación de no regresión

No conviene tratarlos igual que una feature nueva.

## Cómo elegir

| Situación | Enfoque |
|-----------|--------|
| Feature con criterios claros y libertad técnica | Behavior-first |
| Integración con API externa o protocolo fijo | Design-first |
| Spike técnico | Design-first |
| Nueva funcionalidad de negocio | Behavior-first |
| Bug con superficie de regresión sensible | Bug-fix flow |

**Regla práctica:** "¿Entiendo mejor el comportamiento o las restricciones?" — esa respuesta te dice cuál flujo usar.

## Anti-patrones

- Arrancar siempre igual sin evaluar el tipo de problema
- Cambiar de enfoque a mitad de camino sin reordenar el spec
- Diseñar sin entender el comportamiento → solución técnicamente linda pero incorrecta
- Escribir requirements ignorando restricciones duras → spec idealista e irrealizable
