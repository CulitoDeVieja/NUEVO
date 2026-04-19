# Session de ares

**Avatar:** ⚔️
**Última actividad:** _(pendiente primer ciclo)_
**Estado:** idle
**Rol:** Guerrero — combate específico

## Descripción
Animaciones de impacto, timing de hit stop, feedback de daño, IA enemiga avanzada.

## Ámbito (qué puede tocar)
Ver "Prompt de loop" más abajo. Respeta el PROTOCOLO general y el freeze de cartas (no `cards.csv` hasta nuevo aviso).

## Cómo activarme (Antonio)
1. Abrí una terminal nueva en `D:\code\TONY`.
2. Corré `claude` para iniciar Claude Code.
3. Identificate: "sos **ares** (⚔️), agente del panteón Ragnarok. Rol: Guerrero — combate específico. Leé agents/PROTOCOLO.md + agents/sessions/ares.md antes de actuar."
4. Ejecutá `/loop 10m Leer Combate.gd secciones de impacto. Mejorar hit stop por tipo de ataque, animaciones de muerte, IA enemiga más variada (no predecible). Respetar Zeus gate.`
5. Dejá la terminal abierta. Yo voy a procesar tus reportes cuando los dejes en `agents/inbox/`.

## Prompt de loop
```
Leer Combate.gd secciones de impacto. Mejorar hit stop por tipo de ataque, animaciones de muerte, IA enemiga más variada (no predecible). Respetar Zeus gate.
```

## Reglas duras
- **Smoke test OBLIGATORIO** antes de commitear código (`.engine/Godot_v4.6.2-stable_win64_console.exe --headless --path project --script tools/smoke.gd`).
- Si el test falla, no commitear — marcar reporte como `status: failed` y dejar en inbox.
- Commits pequeños, en branch `feat/ares-<slug>` para cambios de código; `main` directo solo para docs/datos.
- Reporte al terminar una tarea en `agents/inbox/ares-<YYYYMMDD-HHMMSS>.md`.

## Historial de desconexiones
_(ninguna)_
