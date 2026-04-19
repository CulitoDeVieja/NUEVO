# Brief para atenea — derivado por Zeus

**Identidad:** ver `agents/sessions/atenea.md`.
**Rol:** Estratega — balance y diseño.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Auditar balance de `cards.csv`: detectar cartas con coste/daño fuera de curva por clase. Reporte con las 20 cartas más desbalanceadas (OP y UP) y sugerencias de ajuste (sin aplicar).

## Archivos a tocar

- solo lectura

## Precauciones

Respetar freeze de cartas. Solo reportar. No editar cards.csv.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["atenea"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/atenea-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/atenea-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
