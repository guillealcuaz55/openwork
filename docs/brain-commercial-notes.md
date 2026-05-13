# Brain Commercial Notes

## Positioning

Brain vende una capa operativa para que una empresa convierta conocimiento, documentos y tareas repetidas en trabajo ejecutable por agentes, con revision humana y trazabilidad.

## Architecture Diagram

```mermaid
flowchart TD
  U["Equipo cliente"] --> UI["Claude Desktop / OpenWork / Cursor / ChatGPT"]
  UI --> MCP["MCP Server privado"]
  MCP --> BRAIN["Company Brain"]
  BRAIN --> K["knowledge/ procesos, políticas, criterios"]
  BRAIN --> S["skills/ procedimientos ejecutables"]
  BRAIN --> M["memory/ logs y aprendizajes"]
  MCP --> TOOLS["Conectores"]
  TOOLS --> D["Drive / SharePoint"]
  TOOLS --> E["Gmail / Outlook"]
  TOOLS --> C["Calendar"]
  TOOLS --> CRM["CRM / ERP / Helpdesk / Sheets"]
  TOOLS --> CHAT["Slack / Teams / WhatsApp"]
  MCP --> AG["Agentes especializados"]
  AG --> RQ["Review queue"]
  RQ --> H["Humano aprueba"]
  H --> M
```
