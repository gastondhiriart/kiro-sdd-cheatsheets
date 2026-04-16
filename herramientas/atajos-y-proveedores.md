# ⚡ Kiro Dynamic Providers & Shortcuts Cheat Sheet PRO

## 🎯 Objetivo

Inyectar contexto en Kiro de forma:

* rápida
* precisa
* sin copiar/pegar
* sin ensuciar el chat

👉 Providers = **formas inteligentes de darle contexto a Kiro**

---

# 🧠 ¿Qué son los Providers?

Son “atajos semánticos” que le dicen a Kiro:

👉 “mirá esto del proyecto sin que te lo copie”

---

## 🧠 Mental model

En vez de:

❌ copiar código
❌ pegar logs
❌ explicar contexto

👉 usás providers

---

# 🧩 Providers principales

---

## 🧠 #codebase

👉 el más potente

**Qué hace:**

* analiza TODO el repo
* usa embeddings (RAG)
* encuentra relaciones

### 🧪 Ejemplo

```text
#codebase
¿dónde se maneja el login?
```

### 📌 Cuándo usar

* explorar código
* entender arquitectura
* buscar lógica existente

---

## 📄 #file o @

👉 foco puntual

**Qué hace:**

* inyecta un archivo específico

### 🧪 Ejemplo

```text
@src/auth/login.ts
explicame este archivo
```

### 📌 Cuándo usar

* debugging
* refactors
* entender código específico

---

## 💻 #terminal

👉 logs sin copiar

**Qué hace:**

* inyecta el último output de la terminal

### 🧪 Ejemplo

```text
#terminal
qué error hay?
```

### 📌 Cuándo usar

* errores de build
* fallos de npm
* logs grandes

---

## 🔗 [[file:...]]

👉 referencias vivas

**Qué hace:**

* linkea archivos dentro de docs
* siempre usa versión actual

### 🧪 Ejemplo

```md
Ver lógica en:
[[file:src/services/auth.ts]]
```

### 📌 Cuándo usar

* steering files
* documentación
* evitar desactualización

---

## 🧩 /mi-skill

👉 ejecutar skills

### 🧪 Ejemplo

```text
/qa-auditor
```

### 📌 Cuándo usar

* aplicar workflows
* validaciones
* automatizaciones

---

# ⚡ Atajos importantes

---

## ⚙️ Cmd + Shift + P

👉 abre la paleta de comandos de Kiro

📌 Usar para:

* hooks
* configuración
* acciones rápidas

---

## 🚀 kiro task run

👉 ejecuta pipeline de specs desde CLI

📌 Usar para:

* automatización
* ejecución completa

---

# 🔥 Guía práctica (la posta)

## 🧪 Debugging

```text
@archivo.ts
#terminal
qué está mal?
```

---

## 🧠 Explorar código

```text
#codebase
dónde se valida el login?
```

---

## ⚙️ Refactor puntual

```text
@archivo.ts
refactorizá esto
```

---

## 🧪 Error complejo

```text
#terminal
#codebase
explicame qué rompí
```

---

# 🧠 Insight CLAVE

Providers = control del contexto

👉 más contexto correcto = mejores respuestas
👉 menos ruido = menos alucinaciones

---

# ⚠️ Anti-patrones

## ❌ Copiar código manualmente

👉 innecesario

## ❌ Meter todo el repo en el prompt

👉 quemás tokens

## ❌ No usar #codebase

👉 perdés el poder de Kiro

---

# 💡 Tip PRO

Combiná providers:

👉 ahí está la magia

```text
#codebase
@src/auth/login.ts
#terminal
qué falla en el login?
```

---

# 🧠 Relación con el sistema

| Pieza     | Rol               |
| --------- | ----------------- |
| Providers | contexto dinámico |
| Steering  | contexto fijo     |
| Specs     | ejecución         |
| Skills    | comportamiento    |

👉 Providers = input inteligente

---

# ⚡ Resumen rápido — Providers y Atajos

| Sintaxis                | Qué hace                   | Cuándo usar                             |
| ----------------------- | -------------------------- | --------------------------------------- |
| 🧠 `#codebase`          | Analiza todo el repo (RAG) | Explorar arquitectura, buscar lógica    |
| 📄 `@archivo` o `#file` | Inyecta un archivo puntual | Debug, refactor, foco específico        |
| 💻 `#terminal`          | Inyecta logs de consola    | Errores de build, fallos                |
| 🔗 `[[file:...]]`       | Referencia viva a código   | Docs, steering, evitar desactualización |
| 🧩 `/mi-skill`          | Ejecuta una skill          | Validaciones, workflows                 |
| ⚙️ `Cmd + Shift + P`    | Abre comandos de Kiro      | Configuración, hooks                    |
| 🚀 `kiro task run`      | Ejecuta specs desde CLI    | Automatización, pipeline                |

---

## 🧠 Regla rápida

* 🧠 Mucho contexto → `#codebase`
* 🎯 Foco puntual → `@archivo`
* 💥 Error → `#terminal`
* ⚙️ Automatizar → `/skill`

👉 combinarlos = máximo poder

---
