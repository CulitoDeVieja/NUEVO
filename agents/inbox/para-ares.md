# Brief para ares — derivado por Zeus

**Identidad:** ver `agents/sessions/ares.md`.
**Rol:** Guerrero — IA enemiga.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Auditar `project/data/enemigos.json`: detectar enemigos con `intenciones` monótonas (siempre mismo patrón). Reporte con 10 sugerencias de variedad (sin aplicar aún).

## Archivos a tocar

- solo lectura

## Precauciones

Respetar freeze. Solo reportar.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["ares"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/ares-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/ares-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
