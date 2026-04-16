# 🧩 Kiro Steering Files Cheat Sheet PRO

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

* reglas del proyecto
* decisiones técnicas
* contexto de negocio
* convenciones

👉 Su función principal:
**evitar que Kiro “invente” o rompa tu arquitectura**



---

## 🧠 Mental model

Si Kiro fuera un dev nuevo:

👉 Steering = onboarding + reglas + límites

No es documentación linda.
Es **input directo a cómo la IA toma decisiones**.

---

# 🧩 Los 3 pilares base

---

## ⚙️ `tech.md` — El QUÉ (Stack)

Define:

* tecnologías
* herramientas
* restricciones técnicas

### Ejemplo

```md id="qz8f41"
# Stack Tecnológico

- Frontend: React 18 con Next.js 14 App Router (nunca Pages Router)
- Estado global: Zustand (prohibido Redux o Context API)
- Estilos: Tailwind CSS v3 (no CSS Modules)
- Backend: FastAPI con Python 3.11
- ORM: Prisma (todas las queries pasan por /src/services)
- Testing: Jest + RTL (mínimo 80% cobertura)
```

---

## 🧭 `product.md` — El POR QUÉ (Negocio)

Define:

* qué hace el sistema
* usuarios
* reglas críticas

### Ejemplo

```md id="o9w2lm"
# Producto: Sistema de Turnos Médicos

- Tipo: B2B SaaS para clínicas
- Usuarios: médicos, secretarias, pacientes
- Prioridad: privacidad (HIPAA)
- Performance: < 2s en 3G

- Regla crítica:
  El sistema NO debe exponer datos de un paciente a otro usuario
```

---

## 🏗️ `structure.md` — El CÓMO (Arquitectura)

Define:

* organización del repo
* convenciones
* patrones

### Ejemplo

```md id="v7t1pa"
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

# 🧠 Insight CLAVE (esto es lo más importante)

Steering no describe.

👉 **Condiciona el comportamiento de Kiro**

Ejemplo:

* “usamos React” → info
* “prohibido usar Redux” → decisión

👉 Lo segundo es lo que realmente cambia el output.

---

# 🔥 Qué hace Kiro con esto

Kiro usa steering para:

* generar código consistente
* respetar arquitectura
* evitar decisiones incorrectas
* reducir alucinaciones

👉 Es un filtro activo de decisiones

---

# 🧩 Steerings personalizados (avanzado)

Podés crear más archivos:

* `testing.md`
* `api-design.md`
* `security-policy.md`
* `frontend-patterns.md`

👉 No hay límite

---

## ⚙️ Activación dinámica (muy importante)

Podés controlar cuándo se usan con YAML:

```md id="p9k2sd"
---
inclusion: fileMatch
fileMatchPattern: "src/api/**"
---

# API Design

- usar JSON:API
- versionado en headers
```

👉 Solo se activa cuando editás esa parte del código



---

# ⚠️ Reglas para buen steering

## ✔️ Hacer

* ser específico
* definir restricciones claras
* incluir “qué NO hacer”
* documentar decisiones reales
* reflejar cómo trabaja el equipo

---

## ❌ Evitar

* “usar buenas prácticas”
* “hacer código limpio”
* definiciones vagas
* teoría sin aplicación

---

# 🚨 Anti-patrones

## ❌ Steering genérico

👉 Kiro ignora o inventa

---

## ❌ Falta de restricciones

👉 Kiro se pone creativo (y rompe cosas)

---

## ❌ No incluir deuda técnica

👉 Kiro “optimiza” donde no debe

---

## ❌ No actualizarlo

👉 decisiones desalineadas

---

# 🧠 Relación con otras piezas

| Concepto        | Rol               |
| --------------- | ----------------- |
| **Steering**    | reglas globales   |
| **Specs**       | cambios puntuales |
| **Skills**      | workflows         |
| **.kiroignore** | qué NO ver        |

👉 Steering = cómo pensar
👉 Specs = qué hacer

---

# 💡 Tip PRO

Si algo se repite en más de un ticket:

👉 va a steering

---

# 🚀 Auto-generación (clave en legacy)

Kiro puede:

* analizar tu repo
* detectar stack
* generar steering base automáticamente

👉 después vos lo ajustás



---

# 🎯 Resumen final

* Steering = cerebro del proyecto
* define reglas, no features
* guía todas las decisiones de Kiro
* reduce errores y alucinaciones

👉 buen steering = IA alineada
👉 mal steering = caos elegante

---
