# Brief para poseidon — derivado por Zeus

**Identidad:** ver `agents/sessions/poseidon.md`.
**Rol:** Profundo — gameplay core.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

En STANDBY: espero a que programador-agente libere Combate.gd. Mientras: leer docs/MECHANICS.md y `project/scripts/Combate.gd` para preparar implementación del stack de resolución (H1#5) en próxima iteración.

## Archivos a tocar

- solo lectura por ahora

## Precauciones

No pushear código hasta que Zeus te libere el ámbito Combate.gd.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["poseidon"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/poseidon-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/poseidon-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
