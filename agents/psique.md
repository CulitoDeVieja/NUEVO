# Session de psique

**Última actividad:** 2026-04-18T22:09-03:00
**Estado:** active
**Rol:** Agente remoto (Claude Code hosted en Linux, sin Godot). Trabaja en data-only (cards.csv, JSONs, docs) y en branches `feat/*` para que Hermes local corra el smoke gate y mergee. Loop cada 10 min (cron `e08bc175`, disparos a :03/:13/:23/:33/:43/:53). Antonio dio "permiso para todo" → puede commitear a main cuando sea data/docs.

## Tarea actual
`docs/ACTO3.md` creado como guía canónica del Acto III (para hecate al despertar + resto del panteón). `feat/transitions-dopamina` sigue pending de smoke gate de Zeus.

## Última acción conocida
- `docs/ACTO3.md` NUEVO — guía A3 con arquetipos, mecánicas únicas, antipatrones, 4 preguntas abiertas para Antonio.
- Reporte: `agents/inbox/psique-20260418-220900.md`.
- Rama `feat/transitions-dopamina` (commit `57e6b60`) sigue pendiente de mergear.

## Para retomar
Si volvés como Psique:
1. Leé `agents/PROTOCOLO.md`, `agents/ERRORS.md`, `agents/assignments.json`.
2. Verificá con `CronList` que el cron `e08bc175` (o el sucesor) sigue vivo.
3. Leé README sección "Instrucciones de Antonio" y "Cola de mejoras — Tanda 3" para saber qué falta.
4. Leé el `sessions/hermes.md` para no pisar lo que Hermes esté haciendo localmente.
5. Reglas duras para Psique:
   - **No commits a `main` sin que Hermes gate-ee** (no puedo correr smoke test acá).
   - Código de gameplay/UI → siempre en rama `feat/<slug>`, reporte en `inbox/` marcando `status: wip` para que Hermes lo corra.
   - Data-only (CSV, JSON, docs) sí puede ir a `main` directo con commits pequeños.

## Historial de desconexiones
_(ninguna todavía)_
