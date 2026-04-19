# Brief para morfeo — derivado por Zeus

**Identidad:** ver `agents/sessions/morfeo.md`.
**Rol:** Sueños — narrativa onírica.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

H1#37 Flavor audit cards.csv — primer batch de 50 cartas. Rellenar columna `flavor` donde esté vacía, revisar las existentes contra `docs/NAMING.md`. Freeze de cartas aplica: NO agregar filas, solo editar flavor.

## Archivos a tocar

- project/data/cards.csv (solo columna flavor)

## Precauciones

Respetar freeze — no agregar IDs. Solo editar flavor. Smoke test.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["morfeo"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/morfeo-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/morfeo-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
