# 🧩 Kiro Agent Hooks Cheat Sheet PRO

## 🎯 Objetivo

Controlar y proteger lo que Kiro puede hacer en tu máquina.

👉 Hooks = **capa de seguridad activa en tiempo real**

---

# 🧠 ¿Qué son los Hooks?

Los **Agent Hooks** son callbacks automáticos que:

- interceptan acciones del agente
- ejecutan validaciones
- pueden bloquear ejecuciones

👉 actúan como guardias de seguridad invisibles

---

## 🧠 Mental model

Hook = firewall del agente

👉 no evita que piense
👉 evita que haga cosas peligrosas

---

# ⚙️ Dónde viven

```bash
.kiro/hooks.json
```

---

# 🧩 Estructura básica

```json
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

## 🔹 Trigger

Cuándo se ejecuta.

Ejemplos:
- `PreToolUse`
- `FileSave`

---

## 🔹 Matcher

Qué intercepta.

Ejemplo:

```json
"matcher": "Bash"
```

---

## 🔹 Action

Qué hace el hook:
- ejecutar script
- validar
- bloquear

---

# 🚨 Flujo real

1. Kiro intenta ejecutar algo
2. Hook intercepta
3. Se corre el script
4. Resultado:

- `0` → permitido
- `!= 0` → bloqueado

👉 si falla, Kiro NO ejecuta la acción

---

# 🧪 Ejemplos prácticos

## ☠️ Bloquear comandos peligrosos

```bash
#!/bin/bash

if [[ "$KIRO_COMMAND" == *"rm -rf"* ]]; then
  echo "Bloqueado"
  exit 2
fi

exit 0
```

---

## 🧪 Validar tests antes de ejecutar

```json
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

---

## 🧹 Lint automático al guardar

```json
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

| Concepto | Rol |
|----------|-----|
| Skills | comportamiento |
| Hooks | control |

👉 Skills = “hacé esto”
👉 Hooks = “esto no lo hacés ni loco”

---

# 🔥 Cuándo usar Hooks

Usalos cuando haya riesgo real:

- comandos destructivos
- scripts bash delicados
- deploys
- acceso a DB
- cambios sensibles

---

# ⚠️ Cuándo NO usarlos

No usar para:
- lógica de negocio
- features
- validaciones demasiado livianas

👉 eso va en specs o skills

---

# 🚨 Anti-patrones

## ❌ No usar hooks
👉 Kiro puede ejecutar cosas peligrosas sin fricción

## ❌ Hooks demasiado restrictivos
👉 bloqueás productividad por paranoia

## ❌ Scripts lentos
👉 frena todo el flujo

---

# 💡 Tip PRO

Pensalos como:

👉 CI/CD local en tiempo real

Antes de que algo pase, ya lo frenaste.

---

# 🧠 Relación con el sistema

| Pieza | Rol |
|------|-----|
| Steering | reglas |
| Specs | ejecución |
| Skills | comportamiento |
| Hooks | control |

👉 Hooks = guardia final

---

# 🎯 Resumen final

- Hook = interceptor automático
- ejecuta validaciones
- puede bloquear acciones
- protege tu entorno

👉 sin hooks → potencia sin control
👉 con hooks → potencia segura
