# 🧩 Kiro Specs Cheat Sheet PRO (SDD)

## 🎯 Objetivo

Definir cambios en el sistema de forma:

- clara
- estructurada
- verificable
- ejecutable por Kiro

👉 Specs = **unidad de trabajo controlada**

---

# 🧠 ¿Qué es un Spec?

Un **Spec** es un conjunto de documentos que separa:

```bash
requirements.md → qué se necesita
business-spec.md → comportamiento y criterios de negocio
architecture-spec.md o design.md → cómo se implementa
tasks.md → cómo se ejecuta
bugfix.md o bugfix-spec.md → cómo se corrige un fallo puntual
```

👉 No siempre vas a usar todos los nombres o todos los archivos.
Lo importante es separar **intención**, **diseño** y **ejecución**.

---

## 🧠 Mental model

Spec = mini proyecto aislado

👉 define:
- intención
- diseño
- ejecución
- supuestos y dudas si hace falta

---

# ⚙️ Flujo base

## 1. Requirements / Business Spec

- escrito en lenguaje claro
- idealmente usando EARS
- define comportamiento
- incluye criterios de aceptación

👉 fuente de verdad

---

## 2. Design / Architecture Spec

- arquitectura
- endpoints
- contratos
- decisiones técnicas
- restricciones

👉 blueprint

---

## 3. Tasks / Implementation Plan

- tareas pequeñas
- ejecutables
- ordenadas
- con dependencias visibles

👉 ejecución automática o semi-asistida

---

# 🧠 Insight CLAVE

Spec Mode separa:

- pensar
- diseñar
- ejecutar

👉 primero se aclara el problema
👉 después se diseña
👉 recién después se toca código

Esto baja muchísimo las alucinaciones y el retrabajo.

---

# 🧭 Dos formas válidas de arrancar

## 🟢 Behavior-first / Requirements-first

Primero definís:
- qué debe pasar
- qué criterios de aceptación existen
- qué reglas de negocio importan

Después diseñás la solución.

### Conviene cuando:
- el comportamiento está claro
- producto manda más que la técnica
- todavía no está fijada la solución

---

## 🔵 Design-first / Architecture-first

Primero definís:
- restricciones técnicas
- contratos externos
- arquitectura o integración obligatoria

Después aterrizás requisitos y tasks.

### Conviene cuando:
- la técnica ya viene condicionada
- hay APIs externas o contratos fijos
- el issue está dominado por limitaciones técnicas

---

## 🧠 Regla práctica

- si entendés mejor **qué debería hacer** → behavior-first
- si entendés mejor **cómo necesariamente debe integrarse** → design-first

---

# 🧩 Tipos de Specs

## 🟢 1. Feature Spec

### Cuándo usarlo
- nueva funcionalidad
- nuevos endpoints
- nuevos flujos o pantallas

### Foco
Construir algo nuevo

### Mapeo útil
- `requirements.md` o `business-spec.md`
- `design.md` o `architecture-spec.md`
- `tasks.md`

---

## 🔴 2. Bugfix Spec

### Cuándo usarlo
- bugs
- fallos en producción
- regresiones

### Foco
Corregir sin rediseñar lo que ya funciona

### Mapeo útil
- `bugfix.md` o `bugfix-spec.md`
- `design.md` si hace falta
- `tasks.md`

---

## 🔵 3. Correctness Spec

### Cuándo usarlo
- inconsistencia entre módulos
- validaciones duplicadas o divergentes
- refactor sin cambio funcional visible

### Foco
Alinear y estabilizar el sistema

### Mapeo útil
- `requirements.md` o `business-spec.md`
- `architecture-spec.md` si hay impacto técnico
- `tasks.md`

---

# 🧪 Ejemplos rápidos

## Feature

```md
## Feature: Crear orden

Cuando el usuario hace click en "Comprar", el sistema debe crear una orden

Si el carrito está vacío, el sistema debe mostrar error
```

---

## Bugfix

```md
## Bug: Login incorrecto

Cuando el usuario ingresa credenciales inválidas, el sistema debe rechazar el login
```

---

## Correctness

```md
## Correctness: Validación email

Cuando el usuario envía un email, el sistema debe validar formato RFC
```

---

# ⚠️ Conflictos cruzados y dependencias

Esto no siempre se menciona, pero en specs medianamente complejas es clave.

Hay que dejar visibles:
- dependencias entre tasks
- impactos en contratos compartidos
- decisiones globales que afectan a más de un cambio
- warnings de orden de despliegue o migración

👉 Si una decisión afecta varios tasks, no la entierres en uno solo.
Subila a una sección o archivo de advertencias común.

---

# 🧠 Orden recomendado de lectura

En specs complejas conviene este orden:

1. contexto / init
2. análisis inicial
3. spec principal (business o architecture)
4. rationale del enfoque
5. open questions / assumptions
6. implementation plan / tasks

👉 esto sirve tanto para humanos como para agentes.

---

# 🚨 Anti-patrones

## ❌ Saltarse requirements
👉 código sin intención clara

## ❌ Saltarse design
👉 arquitectura improvisada

## ❌ Tasks demasiado grandes
👉 ejecución caótica

## ❌ Mezclar negocio y técnica sin separar capas
👉 specs difíciles de leer y revisar

## ❌ No dejar visibles conflictos entre tareas
👉 cada task parece correcta sola, pero el conjunto falla

---

# 🧠 Relación con otras piezas

| Concepto | Rol |
|----------|-----|
| Steering | reglas globales |
| Specs | cambios |
| Skills | workflows |
| .kiroignore | límites de contexto |

👉 Specs = ejecución controlada sobre reglas conocidas

---

# 💡 Tip PRO

Un buen spec:

- empieza con comportamiento o restricciones claras
- separa negocio de arquitectura
- divide tareas pequeñas
- deja visibles dependencias y dudas

👉 eso hace que Kiro no tenga que “adivinar el proyecto” en cada paso.

---

# 🎯 Resumen final

- Spec = unidad de desarrollo completa
- separa pensar, diseñar y ejecutar
- puede arrancar behavior-first o design-first
- necesita visibilidad sobre conflictos y dependencias

👉 sin specs → caos
👉 con specs → ingeniería
