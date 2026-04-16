# 🧩 Kiro Specs Cheat Sheet PRO (SDD)

## 🎯 Objetivo

Definir cambios en el sistema de forma:

* clara
* estructurada
* verificable
* ejecutable por Kiro

👉 Specs = **unidad de trabajo controlada**

---

# 🧠 ¿Qué es un Spec?

Un **Spec** es un conjunto de 3 documentos:

```bash id="p1c9xk"
requirements.md → qué se necesita
design.md       → cómo se implementa
tasks.md        → cómo se ejecuta
```

👉 Representa el ciclo completo de desarrollo



---

## 🧠 Mental model

Spec = mini proyecto aislado

👉 define:

* intención
* diseño
* ejecución

---

# ⚙️ Flujo de trabajo (clave)

## 1. requirements.md (Fase 1)

* escrito en EARS
* define comportamiento
* incluye criterios de aceptación

👉 fuente de verdad

---

## 2. design.md (Fase 2)

* arquitectura
* endpoints
* modelos
* decisiones técnicas

👉 blueprint

---

## 3. tasks.md (Fase 3)

* tareas pequeñas
* ejecutables
* checkboxes

👉 ejecución automática

---

## 🚀 Motor de ejecución

En `tasks.md`:

```md id="k2d9lw"
- [ ] Crear endpoint
- [ ] Implementar servicio
```

👉 Kiro:

* ejecuta tareas
* edita código real
* valida cambios
* marca como DONE



---

# 🧠 Insight CLAVE

Spec Mode:

👉 separa pensamiento de ejecución

* primero pensás (requirements + design)
* después ejecutás (tasks)

👉 elimina alucinaciones



---

# 🧩 Tipos de Specs

---

# 🟢 1. Feature Spec

## 📌 Cuándo usarlo

* nueva funcionalidad
* nuevos endpoints
* nuevas pantallas

## 🎯 Objetivo

Construir algo nuevo

---

## 📄 Ejemplo

### requirements.md

```md id="p0x3qe"
## Feature: Crear orden

Cuando el usuario hace click en "Comprar", el sistema debe crear una orden

Si el carrito está vacío, el sistema debe mostrar error
```

---

### design.md

```md id="s9f2ka"
## Enfoque

- Endpoint POST /orders
- Servicio OrderService
```

---

### tasks.md

```md id="u3l8qv"
- [ ] Crear endpoint
- [ ] Implementar servicio
- [ ] Tests
```

---

# 🔴 2. Bugfix Spec

## 📌 Cuándo usarlo

* bugs
* errores en producción
* comportamiento incorrecto

## 🎯 Objetivo

Corregir sin romper nada más

👉 Kiro entra en modo conservador

---

## 📄 Ejemplo

### requirements.md

```md id="b4k7nd"
## Bug: Login incorrecto

Cuando el usuario ingresa credenciales inválidas, el sistema debe rechazar el login
```

---

### design.md

```md id="c8v2qp"
## Problema

- comparación incorrecta de password

## Solución

- usar bcrypt.compare
```

---

### tasks.md

```md id="n2x9wm"
- [ ] Corregir validación
- [ ] Agregar tests
```

---

# 🔵 3. Correctness Spec

## 📌 Cuándo usarlo

* código inconsistente
* deuda técnica
* refactor sin cambiar comportamiento

## 🎯 Objetivo

Alinear y estabilizar el sistema

---

## 📄 Ejemplo

### requirements.md

```md id="e7r4za"
## Correctness: Validación email

Cuando el usuario envía un email, el sistema debe validar formato RFC
```

---

### design.md

```md id="h9m1st"
## Problema

- validaciones inconsistentes

## Solución

- centralizar validación
```

---

### tasks.md

```md id="j3k8qp"
- [ ] Crear util
- [ ] Reemplazar validaciones
```

---

# 🧠 Resumen rápido

| Tipo        | Cuándo usar         | Foco            |
| ----------- | ------------------- | --------------- |
| Feature     | nueva funcionalidad | construir       |
| Bugfix      | algo roto           | corregir        |
| Correctness | inconsistencia      | alinear/mejorar |

---

# 🎯 Regla de oro

* “agregar algo” → Feature
* “esto está mal” → Bugfix
* “esto no me gusta / inconsistente” → Correctness

---

# 🔥 Estrategias de entrada

## 🟢 Requirements-first (Top-down)

* empezás por negocio
* Kiro baja a código

👉 ideal cuando no sabés cómo implementarlo

---

## 🔵 Design-first (Bottom-up)

* empezás por arquitectura
* Kiro genera requirements y tasks

👉 ideal cuando ya sabés la solución técnica



---

# ⚠️ Anti-patrones

## ❌ Saltarse requirements

👉 código sin intención clara

---

## ❌ Saltarse design

👉 arquitectura improvisada

---

## ❌ Tasks demasiado grandes

👉 ejecución caótica

---

## ❌ Mezclar tipos de spec

👉 comportamiento impredecible

---

# 🧠 Relación con otras piezas

| Concepto        | Rol                 |
| --------------- | ------------------- |
| **Steering**    | reglas globales     |
| **Specs**       | cambios             |
| **Skills**      | workflows           |
| **.kiroignore** | límites de contexto |

👉 Specs = ejecución controlada sobre reglas

---

# 💡 Tip PRO

Un buen spec:

* empieza con EARS claro
* tiene diseño simple
* divide tareas pequeñas

👉 eso hace que Kiro “no piense de más”

---

# 🚀 Resumen final

* Spec = unidad de desarrollo completa
* separa pensar vs ejecutar
* reduce errores
* mejora consistencia

👉 sin specs → caos
👉 con specs → ingeniería

---
