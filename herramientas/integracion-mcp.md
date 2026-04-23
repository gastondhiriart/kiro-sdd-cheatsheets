# Integración MCP

MCP (Model Context Protocol) conecta Kiro con servicios externos: APIs, repos, bases de datos, herramientas de búsqueda.

## Configuración

Archivo: `.kiro/settings/mcp.json` (workspace) o `~/.kiro/settings/mcp.json` (global)

```json
{
  "mcpServers": {
    "github": {
      "command": "/path/to/github-mcp-server",
      "args": ["stdio"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_PAT}"
      }
    },
    "atlassian": {
      "url": "https://mcp.atlassian.com/v1/mcp"
    }
  }
}
```

Servidores locales usan `command` + `args`. Servidores remotos usan `url`.

## Servidores comunes

| Servidor | Tipo | Qué permite |
|----------|------|------------|
| GitHub | Local (binario) | Repos, issues, PRs, code search |
| Atlassian | Remoto (OAuth) | Jira, Confluence |

## Powers

Un Power combina un MCP server + documentación + steering en un paquete instalable. Se gestionan desde el panel de Kiro.

- **Install Powers** — Preconstruidos, listos para usar
- **Create Powers** — Hechos a medida para APIs internas

## Seguridad

- Usar variables de entorno para tokens (`${VAR_NAME}`)
- Agregar `.kiro/settings/` al `.gitignore`
- Revisar permisos antes de agregar tools a `autoApprove`
- Combinar MCP + Hooks para controlar acciones peligrosas

## Cuándo usar MCP

- Necesitás datos reales (issues, PRs, tickets)
- Integrar con servicios del equipo (Jira, GitHub)
- Consultar APIs o repos remotos

## Cuándo NO usar MCP

- Podés resolverlo localmente
- No necesitás datos reales
- Hay riesgo innecesario (ej: acceso a DB de producción sin restricciones)
