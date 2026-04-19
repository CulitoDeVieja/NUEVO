# Brief para artemisa — derivado por Zeus

**Identidad:** ver `agents/sessions/artemisa.md`.
**Rol:** Cazadora — testing automatizado.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Expandir `tools/smoke.gd`: además de load, instanciar cada escena y emitir signals típicos (pressed en botones encontrados). Objetivo: detectar crashes de runtime headless. Mantener el script existente funcionando.

## Archivos a tocar

- tools/smoke.gd

## Precauciones

El smoke test es crítico. Si lo rompés, todo se bloquea. Testear antes de commitear.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["artemisa"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/artemisa-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/artemisa-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
