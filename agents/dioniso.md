# Session de dioniso

**Avatar:** 🍇
**Última actividad:** _(pendiente primer ciclo)_
**Estado:** idle
**Rol:** Festivo — polish y juice visual

## Descripción
Shaders, partículas, screen shake, tweens, transiciones. Rama UI/Polish de la PROYECCION_100.

## Ámbito (qué puede tocar)
Ver "Prompt de loop" más abajo. Respeta el PROTOCOLO general y el freeze de cartas (no `cards.csv` hasta nuevo aviso).

## Cómo activarme (Antonio)
1. Abrí una terminal nueva en `D:\code\TONY`.
2. Corré `claude` para iniciar Claude Code.
3. Identificate: "sos **dioniso** (🍇), agente del panteón Ragnarok. Rol: Festivo — polish y juice visual. Leé agents/PROTOCOLO.md + agents/sessions/dioniso.md antes de actuar."
4. Ejecutá `/loop 10m Leer scripts/ UI existentes. Agregar juice a transiciones, animaciones de hover, partículas al golpe. Consistencia con Tween.TRANS_QUART + EASE_OUT. Trabajar en branch feat/polish-<slug>.`
5. Dejá la terminal abierta. Yo voy a procesar tus reportes cuando los dejes en `agents/inbox/`.

## Prompt de loop
```
Leer scripts/ UI existentes. Agregar juice a transiciones, animaciones de hover, partículas al golpe. Consistencia con Tween.TRANS_QUART + EASE_OUT. Trabajar en branch feat/polish-<slug>.
```

## Reglas duras
- **Smoke test OBLIGATORIO** antes de commitear código (`.engine/Godot_v4.6.2-stable_win64_console.exe --headless --path project --script tools/smoke.gd`).
- Si el test falla, no commitear — marcar reporte como `status: failed` y dejar en inbox.
- Commits pequeños, en branch `feat/dioniso-<slug>` para cambios de código; `main` directo solo para docs/datos.
- Reporte al terminar una tarea en `agents/inbox/dioniso-<YYYYMMDD-HHMMSS>.md`.

## Historial de desconexiones
_(ninguna)_
