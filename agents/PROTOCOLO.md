# Protocolo multi-agente TONY

Coordinador central: **Hermes** (esta sesión de Claude Code local).
Ciclo de coordinación: **cada 10 minutos**.

## Skill: `loop` (obligatoria para todo agente)

Cada agente del sistema multi-agente Ragnarok debe tener un **loop** propio que se dispare cada 10 minutos. Es el pulso que mantiene vivo al sistema.

### Qué hace un loop en cada agente

1. **Pull** de `main` para traer cambios de los otros agentes.
2. **Leer `agents/ERRORS.md`** — si hay errores activos en tu área, priorizar fix antes que nueva tarea.
3. **Leer `agents/assignments.json`** — si ya tenés una tarea asignada a vos, continuarla.
4. **Si no tenés tarea:** agarrar la próxima P0 del `BACKLOG.md` que matchee tu rol, reclamarla escribiéndote en `assignments.json` con tu `agent_id`, `task_slug`, `started_at`, `branch`.
5. **Correr `tools/smoke.gd`** antes de commitear. Si falla, no commitear hasta arreglar.
6. **Commitear en tu branch** `feat/<task-slug>` o directo en `main` si son cambios pequeños.
7. **Cuando termines:** dejar reporte en `agents/inbox/<agent_id>-<timestamp>.md`, borrar tu assignment, actualizar tu `agents/sessions/<agent_id>.md`.

### Configuración del loop

Cada agente es responsable de crear su propio cron de 10 minutos en su entorno. En Claude Code se usa la skill `/loop`:

```
/loop 10m <prompt del agente — qué tiene que hacer cada ciclo>
```

Recomendación: usar `3-59/10 * * * *` (dispara a `:03, :13, :23, :33, :43, :53`) para no saturar la API.

### Rol de Hermes respecto al loop

Hermes corre su propio loop (cron `8d99db17`) como **coordinador**. No hace tareas del BACKLOG — solo procesa reportes, actualiza estado, corre el gate smoke test, y re-exporta `TONY.exe`. Si el loop de Hermes muere, nadie procesa los reportes ni mantiene el `.exe` del escritorio sincronizado.

## Desconexión y recuperación

Cada IA mantiene un archivo `agents/sessions/<agent_id>.md` con su contexto. Permite que si se desconecta (crash, cierre, timeout), al reconectar pueda retomar donde quedó. **Ver `agents/sessions/README.md` para el formato.**

- **Al conectar:** crear/leer tu session file. Si el estado es `disconnected`, retomar desde "Para retomar".
- **Al trabajar:** actualizar `Última actividad` tras cada commit/reporte.
- **Al desconectar intencionalmente:** cambiar `Estado: disconnected` + escribir instrucciones en "Para retomar".
- **Timeout (>1h sin reporte):** Hermes marca tu session como `disconnected` con motivo "timeout" y libera tu assignment para que otra IA pueda retomarla.

## Canal de coordinación entre IAs

**`agents/ERRORS.md`** es el registro de bugs detectados. Toda IA debe:
1. **Antes de agarrar una tarea** → leer `ERRORS.md`. Si hay errores activos, priorizar su fix antes que la nueva tarea.
2. **Antes de commitear** → correr `tools/smoke.gd`. Si aparece `SCRIPT ERROR`/`Parse Error`, el commit no va.
3. **Convenciones obligatorias** → ver sección en `ERRORS.md` (inferencia de Variant, scope de variables).
4. **Al introducir un bug** que el smoke detecta, Hermes lo registra con el agente responsable. Se espera que ese agente se auto-corrija en el próximo ciclo.

## Rol de Hermes (coordinador + arquitecto)

Más allá de procesar el inbox, Hermes:

1. **Define y mantiene la hoja de ruta.** Ver `docs/ROADMAP.md` (10 pasos) + `agents/PROYECCION_100.md` (100 ítems agrupados en 4 horizontes: pre-EA, EA→1.0, post-1.0, legado). Cada 10 min Zeus hace un análisis profundo de la PROYECCION y suma/ajusta ítems a medida que los agentes entregan EVOs, manteniendo el colchón vivo en ~100. Punto final: **Paso 10 — 1.0 + PvP + móvil.** Milestone próximo: **Early Access Steam (~6 meses).**
2. **Filtra ideas nuevas** antes de meterlas al BACKLOG. Una idea entra solo si pasa los 5 criterios del roadmap:
   - **Fun first** — mejora la diversión *ahora*, no dentro de 3 pasos.
   - **Vertical slice antes de ancho** — pule lo existente antes de ampliar.
   - **Juice desde el día 1** — polish visual es core, no adorno.
   - **Playtest continuo** — Antonio puede probarla en la próxima build.
   - **Apunta a Early Access** — ayuda a llegar a Steam, no distrae.
3. **Organiza tareas por agente.** Cada agente tiene un track en `agents/tracks/<agent_id>.md` con su historial de EVOs.
4. **Corre tests antes de marcar done.** Regla dura: ninguna mejora se registra en `mejoras.json` hasta que pase `Godot --check-only`. Si falla, el reporte queda con `status: failed` y escala a Antonio.

## Flujo general

1. Cada agente consulta `assignments.json` cuando se despierta.
2. Si tiene tarea asignada a su `agent_id` → trabaja.
3. Si terminó → deja reporte en `inbox/` + borra su entrada de `assignments.json`.
4. Si no tiene tarea → agarra la siguiente P0 sin asignar desde `BACKLOG.md` y la reclama.
5. Hermes procesa cada 10min:
   - **PASO 2 obligatorio: smoke test.** Corre `.engine/Godot_v4.6.2-stable_win64_console.exe --headless --path project --script tools/smoke.gd` y chequea el output por `SCRIPT ERROR`, `Parse Error`, `FAIL`, o exit≠0. Si alguno aparece, **nada se marca done**, los reportes quedan con `status: failed` y se escala a Antonio.
   - Si el test pasa: marca tareas cerradas, registra EVO-NNN en `project/data/mejoras.json` (con `agente` = el agent_id del reporte), actualiza `agents/tracks/<agent_id>.md`, y mueve el reporte a `inbox/archive/YYYY/MM/`.
   - Actualiza `STATE.md` (sección "Agentes activos"), commit + pull --rebase + push.
6. **Re-export SIEMPRE al final del ciclo** (si el test pasó). Hermes re-exporta `TONY.exe` con Godot headless y lo copia al escritorio de Antonio, haya o no cambios en `project/`. Garantiza que el ejecutable del escritorio nunca está más viejo que el `main` de DECK.

## `assignments.json`

```json
{
  "assignments": [
    {
      "agent_id": "nombre-unico-del-agente",
      "task_slug": "texto-corto-de-la-tarea",
      "backlog_line": "identificador exacto del checkbox [ ] en BACKLOG.md",
      "started_at": "2026-04-18T19:00:00-03:00",
      "branch": "feat/<task-slug>"
    }
  ]
}
```

## Schema de `mejoras.json` (ampliado)

Cada entrada debe incluir `agente` (quién la implementó):

```json
{
  "id": "EVO-NNN",
  "fecha": "YYYY-MM-DD",
  "categoria": "polish|gameplay|ui|...",
  "agente": "hermes|ui-programmer|game-designer|...",
  "titulo": "Una línea",
  "criollo": "2-3 frases argentinas, sin sonar IA"
}
```

Reglas:
- Un agente **nunca** toma más de 1 tarea por vez.
- Si una tarea lleva > 1h sin reporte, Hermes la libera automáticamente (timeout).
- Si dos agentes intentan reclamar la misma tarea, gana el primero que commiteó `assignments.json`. El otro, en el siguiente ciclo, agarra otra.

## Reporte en `inbox/<agent_id>-<YYYYMMDD-HHMMSS>.md`

Formato mínimo:

```markdown
# Reporte <agent_id>

- **Tarea:** <texto original del BACKLOG>
- **Status:** done | blocked | wip
- **Branch:** <nombre de la branch>
- **Commits:** <sha1>, <sha2>, …
- **Archivos tocados:** <lista>
- **Notas:** <qué hiciste, qué probaste, qué dejaste pendiente>
- **Próxima sugerencia:** <opcional — qué EVO podría venir después>
```

Hermes, al procesar el reporte, lo mueve a `inbox/archive/<año>/<mes>/` para no reprocesarlo.

## Branches

- `main` — estable, Hermes hace rebase + push.
- `feat/<task-slug>` — cada agente trabaja en su rama. Al terminar, abre PR o mergea si el reporte marca `done` y los tests pasan.
- Si un agente no sabe git, puede trabajar en `main` con commits pequeños. Hermes sincroniza.

## Conflictos

- Dos agentes tocando el mismo archivo: el segundo en llegar debe rebase + resolver.
- Si el conflicto es complejo → marcar `status: blocked` en el reporte y Hermes escala a Antonio.

## Directivas vivas de Antonio

- **2026-04-18 — Freeze de cartas nuevas (REFORZADO 2026-04-19).** ⏸️ **NINGÚN agente** agrega filas a `project/data/cards.csv` hasta aviso explícito de Antonio. Ver `agents/FREEZE.md` para el detalle: qué sí / qué no / cómo proponer ideas sin crearlas. Balance, rework de cartas existentes, reliquias, enemigos, eventos, pociones, keywords, mecánicas, specs: todo OK. Cartas nuevas: **NO**. Violaciones → rollback por Zeus + registro en `ERRORS.md`.
- **2026-04-19 — Foco total: UX, renderizado, encuadre perfecto.** Todos los agentes priorizan:
  - **Cada recuadro (Panel/Button/Container) debe estar alineado y con padding simétrico.** Ver `CardView.gd` como referencia de lo que debe funcionar 1:1.
  - **Todo se desliza suave.** Scroll con inercia, transiciones con easing, nada de cortes secos.
  - **Cada pantalla revisada visualmente.** Si un agente toca un script de UI, verifica en Godot abierto (o via `tools/test_<escena>.gd`) que los elementos no se solapan, no están cortados ni descentrados.
  - **Animaciones con Tween.TRANS_QUART + EASE_OUT** por defecto (a menos que haya razón). Consistencia en todo el juego.
  - **Regla práctica:** si tocás un Label con `HORIZONTAL_ALIGNMENT_CENTER`, el `position.x` y `size.x` deben ser simétricos respecto al contenedor padre (ver `fix(ui)` commit `1f2f4a4`).

## Reglas duras

- **Nunca borrar archivos sin confirmación de Antonio.**
- **Nunca tocar el token de GitHub ni archivos fuera de `D:\code\TONY\`.**
- **Nunca commitear binarios > 50 MB** (usar `.gitignore`, subirlos como Release).
- **Respuestas cortas en español** al reportar.
