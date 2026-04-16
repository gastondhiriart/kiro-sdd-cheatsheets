# 🛡️ Kiro Agent Hooks Cheat Sheet PRO

## 🎯 Objetivo

Controlar y proteger lo que Kiro puede hacer en tu máquina.

👉 Hooks = **capa de seguridad activa en tiempo real**

---

# 🧠 ¿Qué son los Hooks?

Los **Agent Hooks** son callbacks automáticos que:

* interceptan acciones del agente
* ejecutan validaciones
* pueden bloquear ejecuciones

👉 Actúan como guardias de seguridad invisibles



---

## 🧠 Mental model

Hook = firewall del agente

👉 No evita que piense
👉 Evita que haga cosas peligrosas

---

# ⚙️ Dónde viven

```bash id="m1k9zp"
.kiro/hooks.json
```

---

# 🧩 Estructura básica

```json id="q7x2vn"
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "action": {
          "type": "command",
          "command": "scripts/security_check.sh",
          "timeout": 5
        }
      }
    ]
  }
}
```

---

# 🧩 Conceptos clave

## 🔹 Trigger (cuándo se ejecuta)

Ejemplos:

* `PreToolUse` → antes de ejecutar herramientas (bash, etc)
* `FileSave` → al guardar archivos

👉 define el momento de control

---

## 🔹 Matcher (qué intercepta)

```json id="y2r8mk"
"matcher": "Bash"
```

👉 define el tipo de acción

---

## 🔹 Action (qué hace)

Puede:

* ejecutar script
* validar
* bloquear

---

# 🚨 Flujo real

1. Kiro intenta ejecutar algo
2. Hook intercepta
3. Se ejecuta el script
4. Resultado:

* `0` → ✅ permitido
* `!= 0` → ❌ bloqueado

👉 si falla → Kiro NO ejecuta



---

# 🧪 Ejemplos prácticos

---

## ☠️ Bloquear comandos peligrosos

```bash id="k9t3xp"
#!/bin/bash

if [[ "$KIRO_COMMAND" == *"rm -rf"* ]]; then
  echo "Bloqueado"
  exit 2
fi

exit 0
```

👉 evita desastres

---

## 🧪 Validar tests antes de ejecutar

```json id="r4v1ls"
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "action": {
          "type": "command",
          "command": "npm run test"
        }
      }
    ]
  }
}
```

👉 no ejecuta nada si falla

---

## 🧹 Lint automático

```json id="x8p2zn"
{
  "hooks": {
    "FileSave": [
      {
        "matcher": "*.ts",
        "action": {
          "type": "command",
          "command": "npm run lint"
        }
      }
    ]
  }
}
```

---

# 🧠 Insight CLAVE

Hooks ≠ Skills

| Concepto | Rol            |
| -------- | -------------- |
| Skills   | comportamiento |
| Hooks    | control        |

👉 Skills = “hacé esto”
👉 Hooks = “esto no lo hacés ni en pedo”

---

# 🔥 Cuándo usar Hooks

Usalos cuando haya riesgo real:

* comandos destructivos
* scripts bash
* deploys
* acceso a DB
* cambios sensibles

👉 todo lo que pueda romper algo

---

# ⚠️ Cuándo NO usarlos

No usar para:

* lógica de negocio
* features
* validaciones simples

👉 eso va en specs o skills

---

# 🚨 Anti-patrones

## ❌ No usar hooks

👉 Kiro puede hacer cosas peligrosas

---

## ❌ Hooks demasiado restrictivos

👉 bloqueás productividad

---

## ❌ Scripts lentos

👉 frena todo el flujo

---

# 💡 Tip PRO

Pensalos como:

👉 CI/CD local en tiempo real

Antes de que algo pase… ya lo frenaste

---

# 🚀 Nivel avanzado

Podés:

* encadenar múltiples hooks
* validar distintos tipos de acciones
* integrar scripts complejos
* aplicar políticas de seguridad tipo empresa

---

# 🧠 Relación con el sistema

| Pieza    | Rol            |
| -------- | -------------- |
| Steering | reglas         |
| Specs    | ejecución      |
| Skills   | comportamiento |
| Hooks    | control        |

👉 Hooks = guardia final

---

# 🎯 Resumen final

* Hook = interceptor automático
* ejecuta validaciones
* puede bloquear acciones
* protege tu entorno

👉 sin hooks → potencia sin control
👉 con hooks → potencia segura

---
