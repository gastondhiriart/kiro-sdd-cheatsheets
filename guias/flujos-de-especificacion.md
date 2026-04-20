# 🧩 Kiro Flujos de especificación Cheat Sheet PRO

## 🎯 Objetivo

Tener una guía rápida para elegir **por dónde empezar un spec** según el tipo de problema.

👉 No todos los cambios se entienden mejor desde el mismo ángulo.

---

# 🧠 Los dos flujos principales

## 🟢 1. Comportamiento y criterios primero

También conocido como:
- behavior-first
- requirements-first

### Idea
Primero definís:
- qué debería pasar
- qué reglas de negocio aplican
- qué criterios de aceptación existen

Después bajás eso a diseño y tasks.

### Conviene cuando
- producto manda más que la técnica
- el comportamiento esperado está bastante claro
- todavía hay libertad para diseñar la solución

### Secuencia mental
1. requirements / business spec
2. design / architecture
3. tasks / implementation plan

---

## 🔵 2. Diseño y restricciones primero

También conocido como:
- design-first
- architecture-first

### Idea
Primero definís:
- contratos externos
- restricciones técnicas
- arquitectura obligatoria
- limitaciones del entorno

Después aterrizás requisitos y tareas.

### Conviene cuando
- el trabajo está condicionado por una API externa
- ya existe un diseño o contrato aprobado
- el problema está dominado por restricciones técnicas

### Secuencia mental
1. architecture / design spec
2. ajuste del requisito
3. tasks / implementation plan

---

# 🧠 Cómo elegir

| Situación | Suele convenir |
|----------|-----------------|
| historia con criterios claros y libertad técnica | comportamiento primero |
| integración con API externa o protocolo fijo | diseño primero |
| spike técnico | diseño primero |
| nueva funcionalidad de negocio | comportamiento primero |
| bug con superficie de regresión sensible | bugfix flow específico |

---

# 🔴 Caso especial: bugs

Los bugs suelen pedir otro camino:

1. análisis del fallo
2. delimitación del impacto
3. corrección acotada
4. pruebas de no regresión

👉 no conviene tratarlos igual que una feature nueva

---

# 🔥 Lo importante

No son flujos enemigos.

Es común:
- usar diseño primero para un spike
- usar comportamiento primero para la entrega final

👉 lo importante es **ser coherente dentro del ciclo actual**.

---

# ⚠️ Anti-patrones

## ❌ Arrancar siempre igual
👉 no todos los problemas se entienden desde el mismo lado

## ❌ Cambiar de enfoque a mitad de camino sin reordenar el spec
👉 confusión y retrabajo

## ❌ Diseñar sin entender el comportamiento
👉 solución técnicamente linda, pero incorrecta

## ❌ Escribir requirements ignorando restricciones duras
👉 spec idealista e irrealizable

---

# 💡 Tip PRO

Si no sabés por dónde arrancar, preguntate:

👉 “¿Hoy entiendo mejor el comportamiento o las restricciones?”

Esa respuesta casi siempre te dice cuál flujo usar.

---

# 🎯 Resumen final

- behavior-first = qué debería pasar
- design-first = qué sí o sí debe respetarse
- bugfix = análisis del fallo + corrección acotada

👉 elegir bien el flujo reduce muchísimo el retrabajo
