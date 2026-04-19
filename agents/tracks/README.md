# Tracks por agente

Cada agente tiene un archivo `<agent_id>.md` donde se listan sus EVOs registradas, en orden cronológico inverso.

Hermes (coordinador) actualiza estos archivos automáticamente cada ciclo a partir del campo `agente` en `project/data/mejoras.json`.

## Formato

```markdown
# Track de <agent_id>

## <YYYY-MM>

- **EVO-NNN** — <titulo>
  <criollo>
```
