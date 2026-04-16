# 🧩 Kiro Modelos IA según uso Cheat Sheet PRO

## 🎯 Objetivo

Elegir el modelo correcto según:

* complejidad
* costo (credits)
* velocidad
* tipo de tarea

👉 Modelo correcto = mejor resultado + menos costo

---

# ⚙️ Modo Auto (MUY IMPORTANTE)

## 🟢 Qué hace

👉 Kiro elige el modelo automáticamente según la tarea

* tareas simples → modelos baratos
* tareas complejas → modelos más potentes

---

## ✅ Cuándo usar Auto

* flujo normal de trabajo
* cuando no sabés qué elegir
* tasks.md
* uso diario

👉 **Default recomendado**

---

## ⚠️ Cuándo NO usar Auto

* querés control fino del costo
* estás debuggeando algo complejo
* estás definiendo arquitectura

👉 ahí conviene elegir manual

---

## 🧠 Regla

👉 Si dudás → Auto
👉 Si sabés lo que hacés → manual

---

# 🧩 Modelos disponibles (tu setup)

---

## 🟣 Claude Opus 4.6 (2.2x 💸)

👉 el más potente (y caro)

### Usar para:

* requirements complejos (EARS)
* diseño arquitectónico
* debugging difícil
* decisiones críticas

### ❌ NO usar para:

* tasks.md
* código repetitivo
* cosas simples

👉 **usar solo cuando realmente haga falta**

---

## 🔵 Claude Sonnet 4.6 / 4.5 (1.3x ⚖️)

👉 balance ideal

### Usar para:

* implementación
* refactors
* código general
* uso diario

👉 **mejor default manual**

---

## 🟢 Claude Sonnet 4 (1.3x)

👉 similar a 4.5 pero más orientado a coding

---

## ⚡ Claude Haiku 4.5 (0.4x 💨)

👉 rápido y barato

### Usar para:

* tareas simples
* transformaciones
* respuestas rápidas

---

## 🧠 DeepSeek v3.2 (0.25x 💸)

👉 excelente costo/beneficio

### Usar para:

* generación de código
* iteraciones rápidas
* tasks repetitivas

---

## 🚀 MiniMax M2.5 (0.25x)

👉 rápido y barato

### Usar para:

* tareas livianas
* contenido simple
* soporte general

---

## 🧪 GLM 5 (0.5x)

👉 modelo intermedio

### Usar para:

* tareas mixtas
* código + texto

---

## 💻 Qwen3 Coder Next (0.05x 🧨)

👉 ultra barato y especializado en código

### Usar para:

* escribir código
* completar funciones
* tasks grandes de código

👉 **ideal para ejecución masiva**

---

# 🔥 Guía práctica (la posta)

## 🧩 Spec Mode

### requirements.md

👉 Opus 4.6 (solo si es complejo)
👉 sino Auto / Sonnet

---

### design.md

👉 Opus o Sonnet

---

### tasks.md

👉 Sonnet / Qwen / DeepSeek
👉 ❌ nunca Opus

---

## 🧪 Vibe Mode

* dudas complejas → Opus
* código → Sonnet / Qwen
* cosas simples → Haiku

---

# ⚠️ Regla importante sobre Opus

👉 **NO usar Opus por defecto**

Problemas:

* caro (2.2x)
* lento
* no mejora tareas simples

---

## ✅ Usar Opus solo si:

* estás definiendo lógica compleja
* el problema es difícil
* necesitás máxima precisión

---

## 🧠 Regla mental

* pensar → Opus
* ejecutar → Sonnet / Qwen
* rápido → Haiku

---

# 🚨 Anti-patrones

## ❌ Usar Opus para todo

👉 quemás credits al pedo

---

## ❌ Usar Haiku para cosas complejas

👉 resultados pobres

---

## ❌ No usar Auto nunca

👉 sobre-optimización innecesaria

---

# 💡 Tip PRO

Flujo ideal:

1. Auto / Sonnet → 90% del tiempo
2. Opus → casos complejos
3. Qwen / DeepSeek → ejecución masiva

---

# 🎯 Resumen final

* Auto = mejor default
* Sonnet = caballo de batalla
* Opus = bisturí
* Qwen / DeepSeek = ejecución

👉 elegir bien el modelo = mitad del resultado

---
