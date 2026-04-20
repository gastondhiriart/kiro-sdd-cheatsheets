# 🧩 Kiro Multihilo de Contexto Cheat Sheet PRO

## 🎯 Objetivo

Evitar que el contexto:

- se ensucie
- se vuelva inmanejable
- degrade la calidad de la IA

👉 Multihilo = **orden mental + aislamiento de contexto**

---

# 🧠 Qué problema resuelve

En un chat largo:

- Kiro olvida cosas
- mezcla conceptos
- alucina más
- consume más contexto del necesario

👉 esto es **context drift**

---

# 🧩 Solución de Kiro

Kiro usa 3 mecanismos:

- Tangents
- Checkpoints
- Subagentes

---

# 🟡 1. Tangents

## Qué son

Chats secundarios temporales.

👉 sirven para discutir algo sin ensuciar el flujo principal

## Cuándo usarlos

- dudas teóricas
- exploraciones rápidas
- temas laterales

## Ejemplo

Estás diseñando una arquitectura y necesitás entender Promise.all.
Abrís un tangent, resolvés eso, y volvés al hilo principal limpio.

---

# 🔵 2. Checkpoints

## Qué son

Snapshots del estado mental y de la ejecución.

👉 permiten volver atrás si una rama salió mal

## Cuándo usarlos

- antes de cambios grandes
- refactors delicados
- tareas riesgosas

## Insight

Es como un rewind del pensamiento + ejecución del agente.

---

# 🟣 3. Subagentes

## Qué son

Instancias paralelas de Kiro que trabajan en background.

👉 cada una con su propio contexto
👉 no las invocás manualmente como una acción explícita
👉 suelen aparecer sobre todo al ejecutar tasks complejas

## Cuándo aparecen normalmente

- al correr `tasks.md`
- cuando Kiro divide trabajo en varias unidades
- cuando necesita paralelizar sin mezclar contexto

## Qué ganás

- paralelismo
- menos contaminación entre tareas
- mejor consistencia

---

# 🧠 Insight CLAVE

Los 3 mecanismos atacan el mismo problema:

👉 **la contaminación de contexto**

---

## Comparación mental

| Herramienta | Qué hace |
|------------|---------|
| Tangent | separa ideas |
| Checkpoint | permite volver atrás |
| Subagente | ejecuta en paralelo |

---

# 🔥 Cuándo usar cada uno

## Tangents
- dudas
- exploración
- teoría

## Checkpoints
- antes de cambios grandes
- cuando algo puede salir mal

## Subagentes
- ejecución de tareas
- trabajo en paralelo
- contexts aislados por task

---

# ⚠️ Anti-patrones

## ❌ Todo en un solo chat
👉 caos + alucinaciones

## ❌ No usar checkpoints
👉 no podés volver atrás fácilmente

## ❌ Pensar que los subagentes se invocan manualmente
👉 normalmente son una mecánica interna del sistema

---

# 🧠 Relación con el sistema

| Pieza | Rol |
|------|-----|
| Steering | reglas |
| Specs | ejecución |
| Skills | comportamiento |
| Hooks | control |
| MCP | acceso externo |
| Multihilo | manejo del contexto |

👉 multihilo = salud mental del sistema

---

# 💡 Tip PRO

Pensalo así:

- Tangent = pensar en una burbuja
- Spec = decidir formalmente
- Subagente = ejecutar en paralelo sin mezclar temas

---

# 🎯 Resumen final

- Kiro separa contexto en múltiples hilos
- evita alucinaciones por contaminación de conversación
- mejora rollback y paralelismo

👉 sin multihilo → caos
👉 con multihilo → control
