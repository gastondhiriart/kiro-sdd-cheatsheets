# 🧩 Kiro MCP Cheat Sheet PRO (Model Context Protocol)

## 🎯 Objetivo

Permitir que Kiro:

- acceda a datos externos
- interactúe con servicios reales
- ejecute acciones fuera del código local

👉 MCP = **los ojos y manos de Kiro fuera del IDE**

---

# 🧠 ¿Qué es MCP?

El **Model Context Protocol (MCP)** es un estándar que permite conectar Kiro con:

- APIs externas
- bases de datos
- servicios cloud
- herramientas de búsqueda

👉 rompe la caja cerrada de la IA

---

## 🧠 Mental model

- Sin MCP → Kiro piensa pero está ciego
- Con MCP → Kiro ve, consulta y actúa

---

# ⚙️ Dónde se configura

```bash
.kiro/mcp-servers.json
```

---

# 🧩 Qué puede hacer con MCP

- consultar base de datos
- leer repos remotos
- buscar documentación actualizada
- ejecutar queries
- interactuar con APIs

👉 Ejemplos comunes:
- GitHub
- Jira
- PostgreSQL
- Search

---

# 🚨 Problema clave

MCP por sí solo:

👉 es poderoso… y peligroso

Puede:
- borrar datos
- ejecutar queries destructivas
- afectar sistemas reales

---

# 🧠 Powers (control sobre MCP)

👉 MCP = acceso 🔑
👉 Power = reglas de uso sobre ese acceso 🛡️

---

## 🧩 ¿Qué es un Power?

Un **Power** combina:

1. conexión MCP
2. instrucciones (Markdown)

👉 gobierna cómo el agente usa ese MCP:

- qué acciones puede ejecutar
- qué acciones están prohibidas
- cómo debe comportarse al interactuar con el sistema

---

## 🧠 Mental model

- MCP = llaves
- Power = reglas operativas sobre esas llaves

👉 un Power se parece a un contrato, pero no es solo un contrato pasivo.
Influye directamente en cómo actúa el agente.

---

## 🧪 Ejemplo de Power

```md
# PostgreSQL Power

- Prohibido ejecutar DELETE sin WHERE
- Limitar queries a 100 registros
- Usar paginación
- Nunca modificar tablas en producción
```

👉 esto controla cómo Kiro usa la DB

---

# 🔌 Install Powers vs Create Powers

## 🟢 Install Powers

Powers preconstruidos y auditados.

👉 incluyen:
- conexión MCP configurada
- reglas optimizadas
- comportamiento validado

Ejemplos:
- GitHub
- PostgreSQL
- Search

### Cuándo usarlos
- querés rapidez
- ya existe uno que te sirve
- no necesitás customizar mucho

---

## 🔵 Create Powers

Powers hechos a medida.

👉 definís:
- conexión MCP
- reglas específicas

Usar cuando:
- hay APIs internas
- hay reglas propias del equipo
- necesitás comportamiento muy específico

---

## 🧠 Regla práctica

- Install → rápido y seguro
- Create → flexible y controlado

---

# 🔥 Cuándo usar MCP

- necesitás datos reales
- debugging con DB
- integrar sistemas externos
- consultar APIs o repos remotos

---

# ⚠️ Cuándo NO usar MCP

- no necesitás datos reales
- podés resolverlo localmente
- hay riesgo innecesario

👉 MCP agrega complejidad y riesgo

---

# 🚨 Anti-patrones

## ❌ MCP sin Power
👉 acceso sin control

## ❌ Dar acceso total
👉 riesgo real en producción

## ❌ No limitar queries
👉 problemas de performance o costos

---

# 🧠 Relación con el sistema

| Pieza | Rol |
|------|-----|
| Steering | reglas globales |
| Specs | ejecución |
| Skills | comportamiento |
| Hooks | control |
| MCP | acceso externo |
| Power | control del acceso |

👉 MCP expande el mundo de Kiro

---

# 💡 Tip PRO

- empezá con Install Powers
- pasá a Create Powers cuando necesites precisión
- siempre limitá permisos
- si algo puede romper producción, combiná Power + Hooks

---

# 🎯 Resumen final

- MCP conecta Kiro con el mundo real
- permite leer, consultar y ejecutar
- Power define cómo se usa ese acceso
- es muy potente, pero requiere control

👉 sin MCP → limitado
👉 con MCP → poderoso
👉 con Power → usable en serio
