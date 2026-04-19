# Brief para cronos — derivado por Zeus

**Identidad:** ver `agents/sessions/cronos.md`.
**Rol:** Tiempo — scheduler.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Documentar en `agents/CRONS.md` todos los crons activos del sistema (Zeus ffa2dc1b + los de otros agentes si tienen). Incluir prompt, cadencia, última ejecución conocida. Detectar crons huérfanos o conflictos de timing.

## Archivos a tocar

- agents/CRONS.md (nuevo)

## Precauciones

Solo docs. No tocar crons reales.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["cronos"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/cronos-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/cronos-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
