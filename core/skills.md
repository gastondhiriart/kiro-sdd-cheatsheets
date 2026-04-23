# Skills

Workflows reutilizables que Kiro puede activar automáticamente o por comando.

## Estructura

```
.kiro/skills/<skill-name>/
├── SKILL.md           # Instrucciones (requerido)
├── references/        # Documentación de apoyo
├── scripts/           # Lógica ejecutable
└── assets/            # Templates
```

## SKILL.md

```md
---
name: pr-review
description: Review pull requests for code quality and security.
---

## Proceso
1. Verificar seguridad
2. Revisar manejo de errores
3. Confirmar cobertura de tests
4. Revisar naming y estructura
```

Campos del frontmatter:
- `name` (requerido) — Debe coincidir con el nombre de la carpeta. Minúsculas, números, guiones.
- `description` (requerido) — Cuándo usar esta skill. Kiro matchea esto contra tus requests.

## Activación

- **Automática** — Kiro detecta que tu request coincide con la descripción de una skill
- **Manual** — Escribís `/nombre-skill` en el chat

## Cuándo crear una skill

Si algo:
- Se repite
- Tiene reglas claras
- Tiene pasos definidos
- Puede validarse o automatizarse

→ Probablemente debería ser una skill.

## Cuándo NO usar skills

- Lógica de negocio → va en specs
- Reglas del proyecto → va en steering
- Features específicas → va en specs

## Relación con otras piezas

| Concepto | Rol |
|----------|-----|
| Steering | Qué reglas seguir |
| Specs | Qué construir |
| Skills | Cómo actuar |

## Tips

- Scope acotado — una skill hace una cosa bien
- Incluir ejemplos buenos y malos en references/
- Usar scripts/ para validaciones que no dependen del modelo
- Compartir skills entre el equipo via el repo
