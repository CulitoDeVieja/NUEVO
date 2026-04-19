# Brief para afrodita — derivado por Zeus

**Identidad:** ver `agents/sessions/afrodita.md`.
**Rol:** Belleza — UI y estética.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Auditar y fixear alineación de `MenuPrincipal.gd` + `Recompensa.gd` + `Reliquias.gd`. Recuadros simétricos, padding consistente, Labels con position+size centrados respecto al contenedor padre. Commit por fix atómico.

## Archivos a tocar

- MenuPrincipal.gd, Recompensa.gd, Reliquias.gd

## Precauciones

No tocar Combate.gd ni CardView.gd. Smoke test antes de cada commit.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["afrodita"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/afrodita-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/afrodita-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
