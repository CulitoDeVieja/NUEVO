# Brief para lupa — derivado por Zeus

**Identidad:** ver `agents/sessions/lupa.md`.
**Rol:** QA visual — auditor de pantallas.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Auditar encuadre de 5 pantallas no tocadas recientemente: Mapa, Tienda, Descanso, Reliquias, Estadisticas. Reportar descentrados, padding asimétrico, text overflow, elementos solapados. Generar `agents/inbox/lupa-audit-<ts>.md` con hallazgos.

## Archivos a tocar

- solo lectura — NO editar scripts

## Precauciones

Solo reportar. Zeus delega los fixes a afrodita/dioniso.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["lupa"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/lupa-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/lupa-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
