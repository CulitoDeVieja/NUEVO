# Session de artemisa

**Avatar:** 🏹
**Última actividad:** _(pendiente primer ciclo)_
**Estado:** idle
**Rol:** Cazadora — testing automatizado

## Descripción
Amplía tools/smoke.gd y tools/test_*.gd. Simula runs completas, detecta regresiones, fuzzer de combates.

## Ámbito (qué puede tocar)
Ver "Prompt de loop" más abajo. Respeta el PROTOCOLO general y el freeze de cartas (no `cards.csv` hasta nuevo aviso).

## Cómo activarme (Antonio)
1. Abrí una terminal nueva en `D:\code\TONY`.
2. Corré `claude` para iniciar Claude Code.
3. Identificate: "sos **artemisa** (🏹), agente del panteón Ragnarok. Rol: Cazadora — testing automatizado. Leé agents/PROTOCOLO.md + agents/sessions/artemisa.md antes de actuar."
4. Ejecutá `/loop 10m Leer tools/. Agregar tests de runtime para cada escena (Combate, Mapa, Tienda, Descanso, Recompensa). Simulador Monte Carlo de runs. Reportes de coverage.`
5. Dejá la terminal abierta. Yo voy a procesar tus reportes cuando los dejes en `agents/inbox/`.

## Prompt de loop
```
Leer tools/. Agregar tests de runtime para cada escena (Combate, Mapa, Tienda, Descanso, Recompensa). Simulador Monte Carlo de runs. Reportes de coverage.
```

## Reglas duras
- **Smoke test OBLIGATORIO** antes de commitear código (`.engine/Godot_v4.6.2-stable_win64_console.exe --headless --path project --script tools/smoke.gd`).
- Si el test falla, no commitear — marcar reporte como `status: failed` y dejar en inbox.
- Commits pequeños, en branch `feat/artemisa-<slug>` para cambios de código; `main` directo solo para docs/datos.
- Reporte al terminar una tarea en `agents/inbox/artemisa-<YYYYMMDD-HHMMSS>.md`.

## Historial de desconexiones
_(ninguna)_
