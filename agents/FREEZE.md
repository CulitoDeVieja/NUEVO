# ⏸️ FREEZE DE CARTAS — VIGENTE

**Fecha:** 2026-04-18 (reforzada 2026-04-19)
**Ordenó:** Antonio
**Alcance:** **NINGÚN agente** puede crear cartas nuevas en `project/data/cards.csv`.

## Qué NO se puede hacer

- ❌ Agregar filas nuevas a `project/data/cards.csv`.
- ❌ Crear cartas bajo cualquier otra vía (CSV alternativo, JSON, hardcoded en `.gd`).
- ❌ "Solo agrego 5 para probar" — NO.
- ❌ Generar cartas desde scout / executor / cualquier agente.

## Qué SÍ se puede hacer

- ✅ Editar el **flavor** de cartas existentes (columna `flavor` de cards.csv).
- ✅ Rebalancear stats / coste / daño de cartas existentes.
- ✅ Crear / editar **reliquias** (`reliquias.json`).
- ✅ Crear / editar **enemigos** (`enemigos.json`).
- ✅ Crear / editar **eventos** (`eventos_acto*.json`).
- ✅ Crear / editar **pociones** (`pociones.json`).
- ✅ Crear / editar **keywords**, **mecánicas**, **IA**.
- ✅ Crear / editar **specs** en `agents/specs/` describiendo futuras cartas (pero SIN materializarlas).

## Cómo enterarse y cumplir

1. Todo agente lee `agents/PROTOCOLO.md` → sección "Directivas vivas".
2. Todo agente que se prende desde `FLOW.json` ve este archivo en su primer `git pull`.
3. Zeus (CEO) rechaza cualquier commit que agregue cartas nuevas a `cards.csv` → rollback + registro en `ERRORS.md`.

## Cuándo se levanta el freeze

Solo con aviso **explícito** de Antonio en esta conversación. Por ahora sin fecha de reactivación.

## Si tenés una idea para carta nueva

Dejala como **propuesta** en `agents/inbox/propuesta-carta-<nombre>.md` con:
- Nombre, clase, coste, tipo, ataque/vida, texto, flavor, keywords
- Por qué conviene agregarla

Zeus la archiva hasta que Antonio levante el freeze.
