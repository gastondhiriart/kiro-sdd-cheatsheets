# 🧩 Kiro Skills Cheat Sheet PRO (SDD)

## 🎯 Objetivo

Definir **workflows reutilizables** que Kiro puede:

* entender
* aplicar automáticamente
* ejecutar (incluso con scripts)

👉 Skills = **cómo trabaja el agente**

---

# 🧠 ¿Qué es una Skill?

Una Skill es un módulo que encapsula:

* instrucciones (Markdown)
* ejemplos
* lógica ejecutable (scripts)

👉 No es un prompt
👉 Es un **comportamiento reusable y automático**



---

## 🧠 Mental model

Skill = mini especialista

👉 Ejemplos:

* auditor de código
* experto en docker
* guardián de commits

---

# ⚙️ Para qué sirven

* estandarizar prácticas
* evitar repetir prompts
* automatizar tareas complejas
* ejecutar validaciones reales

👉 Son ideales para:

* linting avanzado
* validaciones de seguridad
* CI local
* convenciones de equipo
* auditorías

---

# 🧩 Anatomía de una Skill

```bash id="q8w2ld"
.kiro/skills/<skill-name>/
├── SKILL.md
├── examples/
└── scripts/
```



---

## 📄 SKILL.md (el cerebro)

```md id="n2k9pm"
---
name: qa-auditor
description: Validaciones TypeScript estrictas
---

- Prohibido usar any
- Usar tipos genéricos
- Ejecutar script de validación
```

👉 Define:

* cuándo se activa
* qué reglas aplica
* qué acciones ejecuta

---

# 🤖 Auto-invocación (la magia real)

Kiro usa NLP para decidir:

👉 “esto que pediste → coincide con esta skill”

Ejemplo:

* vos: “lintéame este código”
* Kiro: activa `qa-auditor`

👉 sin que la llames



---

## 🎮 Invocación manual

```bash id="c1z7mp"
/qa-auditor
```

👉 fuerza ejecución

---

# 🧪 Ejemplos de Skills

---

## 🧪 1. QA Auditor

```md id="t9x3pw"
---
name: qa-auditor
description: Validaciones estrictas
---

- Prohibido usar any
- Validar tipos
- Ejecutar script
```

👉 uso:

* PRs
* APIs
* código crítico

---

## 🐳 2. Docker Deploy

```md id="f4v8bn"
---
name: docker-deploy
description: Reglas Docker
---

- Multi-stage builds
- No copiar node_modules
- HEALTHCHECK obligatorio
```

👉 uso:

* deploy
* infraestructura

---

## 🧾 3. Commit Messages

```md id="y6k2rs"
---
name: commit-messages
description: Conventional commits obligatorio
---

- feat(scope)
- fix(scope)
- refactor(scope)
```

👉 uso:

* commits consistentes

---

# 🧠 Insight CLAVE (esto es lo importante)

Skills ≠ conocimiento

👉 Skills = comportamiento

| Concepto | Rol               |
| -------- | ----------------- |
| Steering | qué reglas seguir |
| Specs    | qué construir     |
| Skills   | cómo actuar       |

---

## 🔥 Regla de oro

Si algo:

* se repite
* tiene reglas claras
* tiene pasos definidos

👉 debería ser una Skill

---

# ⚠️ Cuándo NO usar Skills

No usar para:

* lógica de negocio
* features específicas
* arquitectura

👉 eso es steering o specs

---

# 🚨 Anti-patrones

## ❌ Skills genéricas

👉 no aportan nada

---

## ❌ Sin ejemplos

👉 Kiro interpreta mal

---

## ❌ Sin scripts cuando hacen falta

👉 pierde potencia real

---

## ❌ Skills demasiado grandes

👉 difíciles de mantener

---

# 💡 Tip PRO

Las mejores skills tienen:

* reglas claras
* ejemplos buenos/malos
* scripts ejecutables

👉 ahí Kiro pasa de “sugerir” a “hacer”

---

# 🚀 Nivel avanzado

## Importar skills

```bash id="u7m1sk"
kiro skill import https://github.com/org/skills
```



---

## Usarlas como “cerebro compartido”

👉 equipo entero comparte mismas reglas

---

# 🎯 Relación con el sistema

| Pieza    | Rol                |
| -------- | ------------------ |
| Steering | define reglas      |
| Specs    | definen cambios    |
| Skills   | ejecutan workflows |
| Hooks    | controlan acciones |

👉 Skills = músculo operativo

---

# 🚀 Resumen final

* Skill = workflow reusable
* se activa automáticamente
* puede ejecutar código real
* reduce errores y repetición

👉 sin skills → repetís prompts
👉 con skills → sistema consistente

---
