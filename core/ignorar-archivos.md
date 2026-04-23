# Ignorar archivos del agente

Controlar qué puede ver el agente y qué no. Esto impacta directamente en la calidad del output.

## Cómo funciona en Kiro

Kiro respeta el `.gitignore` para excluir archivos del contexto del agente. Todo lo que esté en `.gitignore` queda fuera automáticamente.

Para control adicional, se usa un steering (ej: `ignore.md`) que le indica al agente qué paths no debe leer ni modificar.

**Nota:** No existe un archivo `.kiroignore` como feature nativa de Kiro. El control se hace via `.gitignore` + steering.

## Qué conviene ignorar

### Secretos
- `.env`, `.env.*`
- `*.pem`, `*.key`
- Carpetas con tokens (ej: `.kiro/settings/`)

### Ruido técnico
- `node_modules/`
- `dist/`, `build/`
- `coverage/`
- `*.log`
- `package-lock.json`

### Archivos pesados o irrelevantes
- Dumps, temporales, snapshots
- Assets enormes que no aportan al trabajo actual

## Qué NO conviene ignorar

- `src/` — código fuente
- `package.json` — dependencias y scripts
- Configs del framework (tsconfig, eslint, vite)
- Tipos y utilidades compartidas
- Tests

Si ocultás esto, el agente queda ciego y empieza a inventar.

## Regla práctica

¿Quiero que el agente use esto para pensar?
- Sí → no ignorar
- No → ignorar
