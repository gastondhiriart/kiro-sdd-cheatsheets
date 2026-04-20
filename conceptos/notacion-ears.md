# 🧩 Kiro EARS Cheat Sheet PRO

## 🎯 Objetivo

Escribir requisitos:
- claros
- sin ambigüedad
- verificables
- útiles para generar código y tests

👉 EARS elimina interpretaciones subjetivas y reduce bugs desde el origen.

---

# 🧠 Tipos de EARS

## 🟢 1. Ubiquitous

**Formato:**
`El sistema debe <comportamiento>`

**Ejemplo:**
El sistema debe cifrar todas las contraseñas usando bcrypt.

📌 Uso:
- reglas globales
- invariantes
- seguridad

---

## 🟡 2. Event-driven

**Formato:**
`Cuando <evento>, el sistema debe <respuesta>`

**Ejemplo:**
Cuando el usuario envía el formulario, el sistema debe validar los datos.

📌 Uso:
- acciones de usuario
- eventos del sistema
- endpoints

---

## 🔵 3. State-driven

**Formato:**
`Mientras <estado>, el sistema debe <respuesta>`

**Ejemplo:**
Mientras el carrito esté vacío, el sistema debe desactivar el botón de checkout.

📌 Uso:
- UI dinámica
- restricciones de flujo
- estados de negocio

---

## 🔴 4. Unwanted behavior

**Formato:**
`Si <condición no deseada>, el sistema debe <respuesta>`

**Ejemplo:**
Si el pago falla, el sistema debe rechazar la transacción y registrar el error.

📌 Uso:
- edge cases
- fallos externos
- resiliencia

---

## 🟣 5. Optional

**Formato:**
`Donde <condición>, el sistema debe <respuesta>`

**Ejemplo:**
Donde el usuario tenga 2FA habilitado, el sistema debe solicitar un código adicional.

📌 Uso:
- feature flags
- planes premium
- configuraciones opcionales

---

# ⚠️ Reglas rápidas

- ❌ Evitar: “manejar correctamente”, “validar bien”, “adecuadamente”
- ✔️ Especificar: qué pasa, cuándo pasa y qué hace el sistema
- ✔️ Un requisito = una idea
- ✔️ Frases cortas
- ✔️ Términos consistentes

---

# 🧪 Ejemplo completo

Cuando el usuario hace click en "Comprar", el sistema debe crear una orden

Si el pago falla, el sistema debe mostrar un mensaje de error

Mientras la orden esté en estado "pendiente", el sistema debe permitir reintentar el pago

Donde el usuario tenga saldo disponible, el sistema debe permitir usarlo como método de pago

---

# 🧠 Criterios de aceptación

Cada requisito debería poder validarse con:

## Formato

Given <contexto>
When <acción>
Then <resultado esperado>

---

## Ejemplo

**Requisito EARS:**
Cuando el usuario envía el formulario, el sistema debe validar el email.

**Acceptance Criteria:**

Given un email inválido
When el usuario envía el formulario
Then el sistema debe mostrar error y no enviar datos

Given un email válido
When el usuario envía el formulario
Then el sistema debe procesar correctamente

---

# 🔥 Dónde encaja en SDD

- EARS vive naturalmente en `requirements.md` o `business-spec.md`
- sirve para alinear negocio, desarrollo, QA y agentes
- ayuda muchísimo en fases behavior-first

👉 EARS no reemplaza el diseño.
Pero sí evita que el diseño arranque sobre ambigüedad.

---

# 🚨 Anti-patrones

❌ “El sistema debe manejar errores correctamente”
❌ “Validar datos del usuario”
❌ “Optimizar performance”

👉 No dicen nada accionable.

---

# 🎯 Regla de oro

Un requisito EARS está bien si:
- no admite doble interpretación
- se puede testear
- define claramente trigger + acción + resultado

---

# 🧠 Mental model

EARS = contrato operativo entre:
- negocio
- dev
- QA
- IA

Si está mal escrito, todo lo demás falla en cadena.

---

# 🎯 Resumen final

- EARS estructura requisitos
- reduce ambigüedad
- mejora specs y tests
- sirve especialmente bien en SDD

👉 buen EARS = menos bugs + mejor código + menos vueltas
