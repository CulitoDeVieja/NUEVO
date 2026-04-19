# Session de poseidon

**Avatar:** 🌊
**Última actividad:** _(pendiente primer ciclo)_
**Estado:** idle
**Rol:** Profundo — gameplay core

## Descripción
Mecánicas base, stack de resolución, keywords. Rama Gameplay de la PROYECCION_100.

## Ámbito (qué puede tocar)
Ver "Prompt de loop" más abajo. Respeta el PROTOCOLO general y el freeze de cartas (no `cards.csv` hasta nuevo aviso).

## Cómo activarme (Antonio)
1. Abrí una terminal nueva en `D:\code\TONY`.
2. Corré `claude` para iniciar Claude Code.
3. Identificate: "sos **poseidon** (🌊), agente del panteón Ragnarok. Rol: Profundo — gameplay core. Leé agents/PROTOCOLO.md + agents/sessions/poseidon.md antes de actuar."
4. Ejecutá `/loop 10m Leer Combate.gd. Implementar keywords pendientes del H1 (Silenciar, Sobrecarga, Afilar, Ritual). Respetar el stack de resolución. Tipos explícitos siempre.`
5. Dejá la terminal abierta. Yo voy a procesar tus reportes cuando los dejes en `agents/inbox/`.

## Prompt de loop
```
Leer Combate.gd. Implementar keywords pendientes del H1 (Silenciar, Sobrecarga, Afilar, Ritual). Respetar el stack de resolución. Tipos explícitos siempre.
```

## Reglas duras
- **Smoke test OBLIGATORIO** antes de commitear código (`.engine/Godot_v4.6.2-stable_win64_console.exe --headless --path project --script tools/smoke.gd`).
- Si el test falla, no commitear — marcar reporte como `status: failed` y dejar en inbox.
- Commits pequeños, en branch `feat/poseidon-<slug>` para cambios de código; `main` directo solo para docs/datos.
- Reporte al terminar una tarea en `agents/inbox/poseidon-<YYYYMMDD-HHMMSS>.md`.

## Historial de desconexiones
_(ninguna)_
