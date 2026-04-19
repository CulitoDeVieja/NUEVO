# Brief para hefesto — derivado por Zeus

**Identidad:** ver `agents/sessions/hefesto.md`.
**Rol:** Herrero — builds, CI, validación.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Crear `tools/validator.gd` (headless) que valide: (a) cards.csv sin IDs duplicados, (b) enemigos.json schema completo, (c) reliquias.json sin flags inconsistentes, (d) eventos_acto*.json con 3 opciones por evento. Output: reporte `agents/inbox/hefesto-validator-<ts>.md`.

## Archivos a tocar

- tools/validator.gd (nuevo)

## Precauciones

Smoke test obligatorio. Solo lectura de datos.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["hefesto"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/hefesto-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/hefesto-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
