# Brief para hermes — derivado por Zeus

**Identidad:** ver `agents/sessions/hermes.md`.
**Rol:** Mensajero externo, dashboards, Telegram.
**Estado actual:** dormido en `agents/FLOW.json`. Te despiertan cambiando el valor a `true`.

## Tarea asignada

Mejorar `agents/DASHBOARD.html`: agregar búsqueda por nombre de agente, timeline de últimas 20 EVOs, barra de progreso global (EVOs completadas / target 100 de PROYECCION)

## Archivos a tocar

- tools/dashboard_gen.py

## Precauciones

No tocar archivos de agentes ni del juego. Solo el generador.

## Protocolo

1. Cuando Antonio te prenda (`FLOW.json["flow"]["hermes"] = true`), clonás el repo NUEVO.
2. Leés tu session file + este brief.
3. Trabajás en branch `feat/hermes-<slug>` para código; `main` directo para docs/datos.
4. Smoke test obligatorio antes de commitear código.
5. Al terminar, reporte en `agents/inbox/hermes-<YYYYMMDD-HHMMSS>.md` con `status: done`.
6. Zeus (yo) proceso en mi ciclo de 10 min, registro EVO, mergeo a DECK si pasa test.

## Criterio de éxito

- Smoke test pasa (16/16 OK).
- Reporte claro con archivos tocados, qué cambió, próxima sugerencia.
- Convención de tipos explícitos si tocás GDScript (ver `agents/ERRORS.md`).

Zeus revisa tu reporte cuando llegue.
