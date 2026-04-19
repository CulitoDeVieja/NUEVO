# Sessions

Un archivo `<agent_id>.md` por cada IA que haya pasado por el repo. Guarda contexto para que si un agente se desconecta (crash, cierre, timeout), al reconectarse pueda retomar donde quedó.

## Formato obligatorio

```markdown
# Session de <agent_id>

**Última actividad:** ISO8601 (ej. 2026-04-18T20:00-03:00)
**Estado:** active | disconnected | idle
**Rol:** (una línea describiendo qué hace este agente)

## Tarea actual
(identificador de `BACKLOG.md` o "ninguna")

## Última acción conocida
(commit SHA, archivo tocado, reporte enviado)

## Para retomar
(instrucciones concretas: qué leer primero, en qué archivo seguir, qué no tocar)

## Historial de desconexiones
- YYYY-MM-DD HH:MM — motivo (ej. timeout >1h sin reporte)
```

## Flujo

**Al conectarse (primera vez o retomando):**
1. Buscar `sessions/<mi_agent_id>.md`. Si no existe, crearlo con `Estado: active`.
2. Si existe con `Estado: disconnected`, leer **"Para retomar"**, actualizar a `active`, continuar desde ahí.
3. Si existe con `Estado: active` pero la "Última actividad" es > 5 min vieja y NO sos vos → conflicto, escalá a Hermes.

**Durante el trabajo:**
- Después de cada commit o reporte, actualizar `Última actividad` y `Última acción conocida`.
- Si vas a hacer algo largo (>5 min), dejar una nota en "Para retomar" sobre qué estabas haciendo.

**Al desconectarse intencionalmente:**
- Cambiar `Estado: disconnected`.
- Escribir en "Para retomar" qué quedó pendiente y qué NO tocar.
- Agregar fila al historial.

**Si te desconectás sin aviso (crash):**
- Hermes lo detecta cuando una assignment lleva > 1h sin reporte. Libera la tarea y escribe en tu `sessions/<agent_id>.md`:
  - `Estado: disconnected`
  - Último commit conocido (del git log)
  - Motivo: "timeout >1h sin reporte"
- Otra IA (o vos al volver) puede retomar.
