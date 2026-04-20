# 🧩 Kiro Steering Cheat Sheet PRO

## 🎯 Objetivo

Definir el **contexto global, reglas y límites del proyecto** que Kiro debe respetar siempre.

👉 Steering = **la constitución del sistema**

---

# 🧠 ¿Qué es Steering?

Los **Steering Files** son archivos `.md` que viven en:

```bash
.kiro/steering/
```

👉 Contienen:
- reglas del proyecto
- decisiones técnicas
- contexto de negocio
- convenciones

👉 Su función principal:
**evitar que Kiro invente, improvise o rompa la arquitectura del proyecto**

---

## 🧠 Mental model

Si Kiro fuera un dev nuevo:

👉 Steering = onboarding + reglas + límites

No es documentación linda.
Es **input directo a cómo la IA toma decisiones**.

---

# 🔥 Principio clave

## 🧠 Pensar antes de codificar

Un buen steering no solo dice *qué stack usamos*.
También deja claro **cómo se decide**.

👉 Antes de escribir código, Kiro debería poder responder:
- qué problema está resolviendo
- qué restricciones no puede violar
- qué patrones del equipo debe seguir
- qué zonas del sistema son sensibles

Si eso no está claro en steering, el agente tiende a improvisar.

---

# 🧩 Los 3 pilares base

## ⚙️ `tech.md` — El QUÉ

Define:
- tecnologías
- herramientas
- restricciones técnicas
- estándares de testing, linting y calidad

### Ejemplo

```md
# Stack Tecnológico

- Frontend: React 18 con Next.js 14 App Router (nunca Pages Router)
- Estado global: Zustand (prohibido Redux o Context API)
- Estilos: Tailwind CSS v3 (no CSS Modules)
- Backend: FastAPI con Python 3.11
- ORM: Prisma (todas las queries pasan por /src/services)
- Testing: Jest + RTL (mínimo 80% cobertura)
```

---

## 🧭 `product.md` — El POR QUÉ

Define:
- qué hace el sistema
- quién lo usa
- qué reglas de negocio son intocables
- prioridades del dominio

### Ejemplo

```md
# Producto: Sistema de Turnos Médicos

- Tipo: B2B SaaS para clínicas
- Usuarios: médicos, secretarias, pacientes
- Prioridad: privacidad (HIPAA)
- Performance: < 2s en 3G

- Regla crítica:
  El sistema NO debe exponer datos de un paciente a otro usuario
```

---

## 🏗️ `structure.md` — El CÓMO

Define:
- organización del repo
- módulos y capas
- naming
- imports
- patrones de arquitectura

### Ejemplo

```md
# Estructura del Proyecto

- /src/app → rutas
- /src/components → UI
- /src/services → lógica de negocio
- /src/lib → utilidades
- /prisma → DB

## Naming
- camelCase → variables
- PascalCase → componentes

## Imports
- usar alias @/ en vez de ../
```

---

# 🧠 Qué más conviene meter en steering

Además de los 3 base, suele valer la pena tener:

- `testing.md`
- `api-design.md`
- `security-policy.md`
- `frontend-patterns.md`
- `modelos-segun-uso.md`

👉 Regla simple:
si algo se repite en varios tickets, probablemente ya no es contexto del ticket.
Es steering.

---

# ⚙️ Activación dinámica

Podés controlar cuándo se usan con frontmatter YAML:

```md
---
inclusion: fileMatch
fileMatchPattern: "src/api/**"
---

# API Design

- usar JSON:API
- versionado en headers
```

👉 Solo se activa cuando editás esa parte del código.

---

# ⚠️ Reglas para un buen steering

## ✔️ Hacer

- ser específico
- definir restricciones claras
- incluir qué **NO** hacer
- documentar decisiones reales
- reflejar cómo trabaja el equipo
- explicar tradeoffs cuando existan

## ❌ Evitar

- “usar buenas prácticas”
- “hacer código limpio”
- teoría sin aplicación
- definiciones vagas

---

# 🚨 Anti-patrones

## ❌ Steering genérico
👉 Kiro ignora o rellena huecos con su propio criterio

## ❌ Falta de restricciones
👉 Kiro se pone creativo en lugares donde no debería

## ❌ No incluir deuda técnica
👉 Kiro “mejora” zonas frágiles sin entender el riesgo

## ❌ No actualizarlo
👉 el agente toma decisiones alineadas a un proyecto que ya no existe

---

# 🧠 Relación con otras piezas

| Concepto | Rol |
|----------|-----|
| Steering | reglas globales |
| Specs | cambios puntuales |
| Skills | workflows |
| .kiroignore | qué no ver |

👉 Steering = cómo pensar
👉 Specs = qué hacer

---

# 💡 Tip PRO

Si querés que un agente trabaje bien en serio:

1. primero alineá steering
2. después hacé specs
3. recién ahí ejecutá tasks

👉 mucho caos con IA no viene de “mala IA”, sino de **mal contexto estable**.

---

# 🎯 Resumen final

- Steering = cerebro estable del proyecto
- define reglas, no features
- reduce improvisación y alucinaciones
- mejora consistencia entre tickets

👉 buen steering = IA alineada
👉 mal steering = caos elegante
