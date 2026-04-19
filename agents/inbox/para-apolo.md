# Brief para apolo — derivado por Zeus

**Identidad:** ver `agents/sessions/apolo.md`.
**Rol:** Audio — música y SFX.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

H1#33 Stinger legendaria/épica: agregar SFX `stinger_legendaria` y `stinger_epica` en `Audio.gd` (generados procedurales, acorde mayor brillante). Hook: al robar carta rara+ dispararlo desde Recompensa.gd si aplica.

## Archivos a tocar

- project/scripts/Audio.gd

## Precauciones

No tocar Combate.gd. Trabajar solo en Audio + Recompensa si hace falta.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["apolo"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/apolo-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/apolo-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
