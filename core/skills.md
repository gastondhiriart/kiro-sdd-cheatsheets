# 🧩 Kiro Skills Cheat Sheet PRO (SDD)

## 🎯 Objetivo

Definir **workflows reutilizables** que Kiro puede:

- entender
- aplicar automáticamente
- ejecutar (incluso con scripts)

👉 Skills = **cómo trabaja el agente**

---

# 🧠 ¿Qué es una Skill?

Una Skill es un módulo que encapsula:

- instrucciones (Markdown)
- ejemplos
- lógica ejecutable (scripts)

👉 No es un prompt
👉 Es un **comportamiento reusable y automático**

---

## 🧠 Mental model

Skill = mini especialista

👉 Ejemplos:
- auditor de código
- experto en docker
- guardián de commits
- revisor de specs

---

# ⚙️ Para qué sirven

- estandarizar prácticas
- evitar repetir prompts
- automatizar tareas complejas
- ejecutar validaciones reales

👉 Son ideales para:
- linting avanzado
- validaciones de seguridad
- chequeo de specs
- convenciones de commits
- revisión de documentación

---

# 🧩 Anatomía de una Skill

```bash
.kiro/skills/<skill-name>/
├── SKILL.md
├── examples/
└── scripts/
```

---

## 📄 SKILL.md (el cerebro)

```md
---
name: qa-auditor
description: Validaciones TypeScript estrictas
---

- Prohibido usar any
- Usar tipos genéricos
- Ejecutar script de validación
```

👉 Define:
- cuándo se activa
- qué reglas aplica
- qué acciones ejecuta

---

# 🤖 Auto-invocación

Kiro usa NLP para decidir:

👉 “esto que pediste coincide con esta skill”

Ejemplo:
- vos: “revisame este código de API”
- Kiro: activa la skill correspondiente

👉 sin que la llames explícitamente

---

## 🎮 Invocación manual

```bash
/qa-auditor
```

👉 fuerza ejecución

---

# 🧪 Ejemplos de skills útiles

## 🧪 1. QA Auditor

```md
---
name: qa-auditor
description: Validaciones estrictas
---

- Prohibido usar any
- Validar tipos
- Ejecutar script
```

---

## 🐳 2. Docker Deploy

```md
---
name: docker-deploy
description: Reglas Docker
---

- Multi-stage builds
- No copiar node_modules
- HEALTHCHECK obligatorio
```

---

## 🧾 3. Commit Messages

```md
---
name: commit-messages
description: Conventional commits obligatorio
---

- feat(scope)
- fix(scope)
- refactor(scope)
```

---

## 🧠 4. Spec Review

```md
---
name: spec-review
description: Revisión de consistencia entre requirements, design y tasks
---

- Detectar contradicciones entre documentos
- Marcar supuestos no explicitados
- Señalar tasks demasiado grandes o ambiguas
```

👉 Esta skill es especialmente útil en SDD porque evita specs lindas pero inconsistentes.

---

# 🧠 Insight CLAVE

Skills ≠ conocimiento

👉 Skills = comportamiento operativo

| Concepto | Rol |
|----------|-----|
| Steering | qué reglas seguir |
| Specs | qué construir |
| Skills | cómo actuar |

---

# 🔥 Regla de oro

Si algo:
- se repite
- tiene reglas claras
- tiene pasos definidos
- puede validarse o automatizarse

👉 probablemente debería ser una Skill

---

# ⚠️ Cuándo NO usar Skills

No usar para:
- lógica de negocio
- features específicas
- arquitectura del proyecto

👉 eso va en steering o specs

---

# 🚨 Anti-patrones

## ❌ Skills genéricas
👉 no aportan nada concreto

## ❌ Sin ejemplos
👉 Kiro interpreta mal

## ❌ Sin scripts cuando hacen falta
👉 pierde potencia real

## ❌ Skills demasiado grandes
👉 difíciles de mantener

---

# 💡 Tip PRO

Las mejores skills tienen:

- reglas claras
- ejemplos buenos/malos
- scripts ejecutables
- un scope acotado

👉 ahí Kiro pasa de “sugerir” a “hacer con criterio”.

---

# 🚀 Nivel avanzado

## Importar skills

```bash
kiro skill import https://github.com/org/skills
```

## Usarlas como cerebro compartido

👉 todo el equipo comparte las mismas reglas operativas

---

# 🎯 Resumen final

- Skill = workflow reusable
- se activa automáticamente o por slash
- puede ejecutar lógica real
- sirve muchísimo para SDD cuando querés consistencia operativa

👉 sin skills → repetís prompts
👉 con skills → sistema consistente
