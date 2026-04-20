# 🧩 `.kiroignore` Cheat Sheet PRO

## 🎯 Objetivo

Controlar **qué puede leer Kiro y qué no** dentro del repo.

👉 No es optimización
👉 Es **seguridad + calidad de contexto**

---

# 🧠 Qué es `.kiroignore`

`.kiroignore` es un archivo que:

👉 **bloquea el acceso de lectura del agente**

Si Kiro intenta leer algo ignorado:

👉 recibe un rechazo de acceso

---

## 🧠 Mental model

`.kiroignore` = persiana selectiva del repo

👉 no es “lo que no uso”
👉 es “lo que el agente NO debe ver”

---

# ⚠️ Diferencia clave

## `.gitignore`
- oculta archivos del versionado

## Inclusion modes
- controlan cuándo se usa contexto

## `.kiroignore`
- **bloquea lectura real del agente**

👉 Es seguridad, no organización

---

# 🧩 Qué conviene ignorar

## 🔐 Secretos y credenciales

- `.env`, `.env.*`
- `*.pem`, `*.key`
- tokens
- secretos cloud
- certificados

---

## 🧱 Ruido técnico

- `node_modules/`
- `dist/`, `build/`, `.next/`
- `coverage/`
- logs
- bundles
- outputs compilados

---

## 📦 Archivos pesados o irrelevantes

- dumps
- temporales
- snapshots gigantes
- assets enormes si no aportan al trabajo actual

---

## ☠️ Zonas sensibles

- configs internas
- infraestructura delicada
- scripts críticos

👉 especialmente si no querés que Kiro sugiera cambios ahí

---

# 🚫 Qué NO conviene ignorar

No tapes lo que Kiro necesita para entender el sistema:

- `src/`
- tests
- `package.json`
- configs del framework
- contratos de API
- migraciones relevantes
- docs internas útiles
- tipos y utilidades importantes

👉 si ocultás esto, Kiro queda medio ciego.

---

# 🧪 Ejemplo recomendado

```gitignore
# secretos
.env
.env.*
*.pem
*.key

# dependencias / build
node_modules/
dist/
build/
.next/
coverage/

# logs / temp
*.log
tmp/
temp/

# binarios / caches
.cache/
*.zip
*.tar.gz
```

---

# 🔥 Regla de oro

Preguntate:

👉 “¿Quiero que Kiro use esto para pensar?”

- Sí → no ignorar
- No → ignorar

---

# ⚠️ Anti-patrones

## ❌ Ignorar demasiado
👉 Kiro no entiende el sistema y empieza a inventar

## ❌ No ignorar secretos
👉 riesgo innecesario

## ❌ Ignorar configs clave
👉 decisiones inconsistentes y bugs raros

---

# 🧠 Relación con otras piezas

| Concepto | Rol |
|----------|-----|
| Steering | qué reglas seguir |
| Specs | qué construir |
| Skills | cómo trabajar |
| `.kiroignore` | qué NO ver |

👉 `.kiroignore` define el **límite de percepción** del agente.

---

# 💡 Tip PRO

Arrancá simple:

- ignorá secretos
- ignorá build artifacts
- ignorá ruido obvio
- dejá visible todo lo que explica el sistema

Después ajustás fino.

---

# 🎯 Resumen final

- `.kiroignore` controla acceso real del agente
- no es para limpiar, es para proteger
- define qué entra en el “cerebro” de Kiro
- impacta directamente en la calidad del output

👉 bien usado = Kiro enfocado
👉 mal usado = Kiro confundido o peligroso
