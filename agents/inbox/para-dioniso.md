# Brief para dioniso — derivado por Zeus

**Identidad:** ver `agents/sessions/dioniso.md`.
**Rol:** Festivo — polish visual.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Pulir Tienda y Descanso: revisar que botones tengan hover state consistente, tweens TRANS_QUART, sombras suaves. No tocar Combate.gd ni CardView.gd.

## Archivos a tocar

- project/scripts/Tienda.gd
- project/scripts/Descanso.gd

## Precauciones

Verificar alineación con PROTOCOLO directiva 2026-04-19. Recuadros simétricos.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["dioniso"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/dioniso-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/dioniso-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
