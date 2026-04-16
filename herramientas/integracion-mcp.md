# 🌐 Kiro MCP Cheat Sheet PRO (Model Context Protocol)

## 🎯 Objetivo

Permitir que Kiro:

* acceda a datos externos
* interactúe con servicios reales
* ejecute acciones fuera del código local

👉 MCP = **los ojos y manos de Kiro fuera del IDE**

---

# 🧠 ¿Qué es MCP?

El **Model Context Protocol (MCP)** es un estándar que permite conectar Kiro con:

* APIs externas
* bases de datos
* servicios cloud
* herramientas de búsqueda

👉 rompe la “caja cerrada” de la IA



---

## 🧠 Mental model

* Sin MCP → Kiro piensa pero está ciego
* Con MCP → Kiro ve, consulta y actúa

---

# ⚙️ Dónde se configura

```bash id="mcp-path"
.kiro/mcp-servers.json
```

---

# 🧩 Qué puede hacer con MCP

* consultar base de datos
* leer repos remotos
* buscar documentación actualizada
* ejecutar queries
* interactuar con APIs

👉 Ejemplos reales:

* GitHub API → leer PRs
* PostgreSQL → consultar datos reales
* Brave Search → docs recientes

---

# 🧪 Ejemplo conceptual

```json id="mcp-example"
{
  "servers": [
    {
      "name": "postgres-db",
      "command": "npx",
      "args": ["mcp-postgres", "--connection", "postgres://..."]
    }
  ]
}
```

👉 habilita acceso a DB real

---

# 🚨 Problema clave

MCP por sí solo:

👉 es poderoso… y peligroso

Puede:

* borrar datos
* ejecutar queries destructivas
* afectar sistemas reales

---

# 🧠 Powers (control sobre MCP)

👉 MCP = acceso
👉 Power = reglas sobre ese acceso

---

## 🧩 ¿Qué es un Power?

Un **Power** combina:

1. conexión MCP
2. instrucciones (Markdown)

👉 define:

* qué puede hacer
* qué NO puede hacer
* cómo debe comportarse

---

## 🧠 Mental model

MCP = llaves 🔑
Power = contrato 📜

---

## 🧪 Ejemplo de Power

```md id="power-example"
# PostgreSQL Power

- Prohibido ejecutar DELETE sin WHERE  
- Limitar queries a 100 registros  
- Usar paginación  
- Nunca modificar tablas en producción  
```

---

# 🔌 Install Powers vs Create Powers

## 🟢 Install Powers

Powers **preconstruidos y auditados** que Kiro ya trae.

👉 Incluyen:

* conexión MCP configurada
* reglas optimizadas
* comportamiento validado

Ejemplos:

* GitHub Power
* PostgreSQL Power
* Brave Search Power

### Cuándo usarlos

* querés rapidez
* existe algo que ya te sirve
* no necesitás customizar mucho

👉 ventaja: rápido, seguro, plug & play

---

## 🔵 Create Powers

Powers **hechos a medida** por vos.

Definís:

1. MCP (conexión técnica)
2. reglas (archivo `.md`)

### Cuándo usarlos

* APIs internas
* microservicios propios
* reglas específicas del negocio

👉 ventaja: control total

---

## 🧠 Regla práctica

* Install → “usar algo ya armado”
* Create → “adaptar Kiro a mi sistema”

---

# 🔥 Cuándo usar MCP

* necesitás datos reales
* debugging con DB
* integrar sistemas externos
* consultar APIs o repos

---

# ⚠️ Cuándo NO usar MCP

* no necesitás datos reales
* podés resolverlo local
* hay riesgo innecesario

👉 MCP agrega complejidad y riesgo

---

# 🚨 Anti-patrones

## ❌ MCP sin Power

👉 acceso sin control

---

## ❌ Dar acceso total

👉 riesgo real en producción

---

## ❌ No limitar queries

👉 problemas de performance / costos

---

# 🧠 Relación con el sistema

| Pieza    | Rol                |
| -------- | ------------------ |
| Steering | reglas globales    |
| Specs    | ejecución          |
| Skills   | comportamiento     |
| Hooks    | control            |
| MCP      | acceso externo     |
| Power    | control del acceso |

👉 MCP expande el mundo de Kiro

---

# 💡 Tip PRO

* empezá con **Install Powers**
* pasá a **Create Powers** cuando necesites precisión
* siempre limitá permisos

---

# 🎯 Resumen final

* MCP conecta Kiro con el mundo real
* permite leer, consultar y ejecutar
* necesita control (Power)
* tiene impacto directo en riesgo

👉 sin MCP → limitado
👉 con MCP → poderoso
👉 con Power → usable en serio

---
