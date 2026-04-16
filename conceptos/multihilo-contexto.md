# 🧵 Kiro Multithread Context Cheat Sheet PRO

(Subagentes, Tangents y Checkpoints)

## 🎯 Objetivo

Evitar que el contexto:

* se ensucie
* se vuelva inmanejable
* degrade la calidad de la IA

👉 Multihilo = **orden mental + aislamiento de contexto**

---

# 🧠 ¿Qué problema resuelve?

En un chat largo:

* Kiro olvida cosas
* mezcla conceptos
* empieza a alucinar
* consume muchos tokens

👉 esto se llama **context drift**

---

# 🧩 Solución de Kiro

Kiro usa 3 mecanismos:

* Tangents
* Checkpoints
* Subagentes



---

# 🟡 1. Tangents (Sub-chats aislados)

## 🧠 Qué son

Chats secundarios temporales

👉 para discutir algo sin ensuciar el flujo principal

---

## 🧪 Ejemplo

Estás diseñando arquitectura y pensás:

> “¿cómo funciona Promise.all?”

👉 abrís un tangent
👉 resolvés eso
👉 lo cerrás

👉 el chat principal queda limpio

---

## 🎯 Cuándo usarlos

* dudas teóricas
* exploraciones
* cosas no directamente relacionadas

---

## ⚠️ Error común

No usarlos y mezclar todo en el mismo chat

👉 termina en caos

---

# 🔵 2. Checkpoints (puntos de rollback)

## 🧠 Qué son

Snapshots del estado mental y del código

👉 permiten volver atrás

---

## 🧪 Ejemplo

Kiro rompe 5 archivos:

👉 vas al checkpoint anterior
👉 rewind
👉 todo vuelve atrás

---

## 🎯 Cuándo usarlos

* antes de cambios grandes
* refactors
* ejecuciones riesgosas

---

## 🧠 Insight

Es como:

👉 Git, pero del pensamiento + ejecución del agente

---

# 🟣 3. Subagentes (ejecución paralela)

## 🧠 Qué son

Instancias paralelas de Kiro que trabajan en background

👉 cada una con su propio contexto

---

## 🧪 Ejemplo

En `tasks.md`:

```md id="k2sub"
- [ ] Crear endpoint
- [ ] Implementar servicio
- [ ] Tests
```

👉 Kiro puede:

* ejecutar tareas en paralelo
* dividir trabajo
* no mezclar contextos

---

## 🎯 Cuándo se usan

* ejecución de tasks
* procesos complejos
* múltiples archivos

---

## 🧠 Insight clave

Cada subagente:

👉 tiene su propio “cerebro aislado”

👉 no contamina el resto

---

# 🧠 Insight CLAVE (el más importante)

Estos 3 mecanismos atacan el mismo problema:

👉 **la contaminación de contexto**

---

## 🎭 Comparación mental

| Herramienta | Qué hace             |
| ----------- | -------------------- |
| Tangent     | separa ideas         |
| Checkpoint  | permite volver atrás |
| Subagente   | ejecuta en paralelo  |

---

# 🔥 Cuándo usar cada uno

## Tangents

* dudas
* exploración
* teoría

---

## Checkpoints

* antes de cambios grandes
* cuando algo puede salir mal

---

## Subagentes

* ejecución de tareas
* procesamiento paralelo

---

# ⚠️ Anti-patrones

## ❌ Todo en un solo chat

👉 caos + alucinaciones

---

## ❌ No usar checkpoints

👉 no podés volver atrás

---

## ❌ Ejecutar todo secuencial

👉 perdés potencia

---

# 🧠 Relación con el sistema

| Pieza     | Rol                 |
| --------- | ------------------- |
| Steering  | reglas              |
| Specs     | ejecución           |
| Skills    | comportamiento      |
| Hooks     | control             |
| MCP       | mundo externo       |
| Multihilo | manejo del contexto |

👉 multihilo = salud mental del sistema

---

# 💡 Tip PRO

Pensalo así:

👉 Tangent = pensar
👉 Spec = decidir
👉 Subagente = ejecutar

---

# 🚀 Nivel avanzado

Podés:

* aislar discusiones complejas
* paralelizar desarrollo
* experimentar sin romper nada
* mantener contexto limpio en proyectos grandes

---

# 🎯 Resumen final

* Kiro separa contexto en múltiples hilos
* evita alucinaciones
* mejora performance
* permite rollback y paralelismo

👉 sin multihilo → caos
👉 con multihilo → control total

---
