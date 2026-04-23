# Providers y atajos

Formas de inyectar contexto en Kiro sin copiar/pegar.

## Providers principales

| Sintaxis | Qué hace | Cuándo usar |
|----------|---------|-------------|
| `#File` | Inyecta un archivo específico | Debug, refactor, foco puntual |
| `#Folder` | Inyecta una carpeta | Explorar un módulo completo |
| `#Terminal` | Inyecta output de la terminal | Errores de build, logs |
| `#Git Diff` | Inyecta los cambios actuales | Reviews, verificar cambios |
| `#Problems` | Inyecta errores del editor | Resolver errores de TypeScript/ESLint |
| `/skill` | Ejecuta una skill | Workflows, validaciones |
| `#steering` | Inyecta un steering manual | Activar contexto específico |

## Referencias en archivos

Dentro de steerings y specs podés referenciar archivos:

```md
Ver lógica en: #[[file:src/services/api.ts]]
```

Siempre apunta a la versión actual del archivo.

## Combinaciones útiles

**Debugging:**
```
#File src/services/api.ts
#Terminal
¿Qué está fallando?
```

**Review:**
```
#Git Diff
/pr-review
```

**Explorar código:**
```
#Folder src/shared/hooks
¿Qué hooks hay y qué hace cada uno?
```

## Atajos

| Atajo | Qué hace |
|-------|----------|
| `Cmd + Shift + P` | Paleta de comandos |
| `Cmd + L` | Nuevo chat |
| `/` | Ver skills disponibles |
| `#` | Ver providers y steerings manuales |
