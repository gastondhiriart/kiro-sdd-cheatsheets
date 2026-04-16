# 🧩 EARS Cheat Sheet PRO (para Kiro / SDD)

## 🎯 Objetivo

Escribir requisitos:

* claros
* sin ambigüedad
* verificables
* útiles para generar código y tests automáticamente

👉 EARS elimina interpretaciones subjetivas y reduce bugs desde el origen.



---

# 🧠 Tipos de EARS

## 🟢 1. Ubiquitous (Siempre aplica)

**Formato:**
El sistema debe <comportamiento>

**Ejemplo:**
El sistema debe cifrar todas las contraseñas usando bcrypt

📌 Uso:

* reglas globales
* seguridad
* invariantes del sistema

---

## 🟡 2. Event-driven (Trigger)

**Formato:**
Cuando <evento>, el sistema debe <respuesta>

**Ejemplo:**
Cuando el usuario envía el formulario, el sistema debe validar los datos

📌 Uso:

* acciones del usuario
* eventos de sistema
* endpoints

---

## 🔵 3. State-driven (Estado)

**Formato:**
Mientras <estado>, el sistema debe <respuesta>

**Ejemplo:**
Mientras el carrito esté vacío, el sistema debe desactivar el botón de checkout

📌 Uso:

* UI dinámica
* restricciones de flujo
* estados de negocio

---

## 🔴 4. Unwanted behavior (Errores / fallos)

**Formato:**
Si <condición no deseada>, el sistema debe <respuesta>

**Ejemplo:**
Si el pago falla, el sistema debe rechazar la transacción y registrar el error

📌 Uso:

* edge cases
* resiliencia
* errores externos (APIs, timeouts)

---

## 🟣 5. Optional (Condicional)

**Formato:**
Donde <condición>, el sistema debe <respuesta>

**Ejemplo:**
Donde el usuario tenga 2FA habilitado, el sistema debe solicitar código adicional

📌 Uso:

* feature flags
* planes premium
* configuraciones opcionales

---

# ⚠️ Reglas rápidas

* ❌ Evitar:

  * “manejar correctamente”
  * “validar bien”
  * “adecuadamente”

* ✔️ Especificar:

  * qué pasa
  * cuándo pasa
  * qué hace el sistema

* ✔️ Un requisito = una idea

* ✔️ Frases cortas

* ✔️ Términos consistentes

---

# 🧪 Ejemplo completo

Cuando el usuario hace click en "Comprar", el sistema debe crear una orden

Si el pago falla, el sistema debe mostrar un mensaje de error

Mientras la orden esté en estado "pendiente", el sistema debe permitir reintentar el pago

Donde el usuario tenga saldo disponible, el sistema debe permitir usarlo como método de pago

---

# 🧠 Criterios de aceptación (CLAVE en Kiro)

Cada requisito debería poder validarse con:

## Formato:

Given <contexto>
When <acción>
Then <resultado esperado>



---

## Ejemplo:

**Requisito (EARS):**
Cuando el usuario envía el formulario, el sistema debe validar el email

**Acceptance Criteria:**

Given un email inválido
When el usuario envía el formulario
Then el sistema debe mostrar error y no enviar datos

Given un email válido
When el usuario envía el formulario
Then el sistema debe procesar correctamente

---

# 🔥 EARS dentro de Kiro (esto es lo importante)

* EARS vive en `requirements.md`
* Es la **fase 1 del Spec**
* Define la fuente de verdad del sistema

👉 Kiro usa esto para:

* diseñar arquitectura
* generar código
* crear tests automáticamente

---

# 🚨 Anti-patrones

❌ “El sistema debe manejar errores correctamente”
❌ “Validar datos del usuario”
❌ “Optimizar performance”

👉 No dicen nada accionable

---

# 🎯 Regla de oro

Un requisito EARS está bien si:

* no admite doble interpretación
* se puede testear
* define claramente trigger + acción + resultado

---

# 🧠 Mental model

EARS = contrato

👉 entre:

* negocio
* dev
* QA
* IA

Si está mal escrito → todo lo demás falla en cadena.

---

# 🚀 Resumen final

* EARS estructura requisitos
* elimina ambigüedad
* permite automatización real
* es la base de SDD en Kiro

👉 buen EARS = menos bugs + mejor código + menos vueltas

---
