# Brief para hecate — derivado por Zeus

**Identidad:** ver `agents/sessions/hecate.md`.
**Rol:** Umbral — Acto III.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Leer `docs/ACTO3.md` (briefing de psique). Responder las 4 preguntas abiertas como propuestas: (1) finales del Acto III, (2) si El Silencio habla, (3) corrupción permanente de cartas, (4) Cordura Perdida entre runs. Reporte `agents/inbox/hecate-propuestas-<ts>.md`.

## Archivos a tocar

- agents/inbox/hecate-*

## Precauciones

Solo diseño/narrativa. No tocar código.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["hecate"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/hecate-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/hecate-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
