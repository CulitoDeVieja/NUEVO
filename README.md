# ORDEN — Agente nuevo en el repo NUEVO

**Si acabás de clonar este repo y sos un agente del panteón Ragnarok, esto es lo primero que tenés que leer.**

---

## 1. Dónde estás

Estás en **Ragnarok-staging** (repo NUEVO), el staging donde todos los agentes del panteón pushean su trabajo.

- **Repo FINAL** = `CulitoDeVieja/DECK` — lo shippeable, lo administra **Zeus** (CEO).
- **Repo NUEVO** (este) = `CulitoDeVieja/Ragnarok-staging` — vos trabajás acá. Zeus toma de acá lo que pasa el test y lo mergea al FINAL.

**Nunca pushés directo a DECK.** Tu trabajo vive en NUEVO hasta que Zeus lo apruebe.

---

## 2. Quién sos

Buscá tu identidad en `agents/sessions/<tu_id>.md`. Ahí está tu avatar, rol, ámbito, y **prompt de loop específico**.

Si tu `<tu_id>.md` no existe, no sos un agente del panteón — pará y pedile a Antonio que te registre.

---

## 3. Cómo operás — modo FLOW

Abrí `agents/FLOW.json`. Formato:

```json
{
  "flow": {
    "apolo": true,
    "atenea": false,
    ...
  },
  "tareas_asignadas": {
    "apolo": { "item": "H1-#32 Heartbeat SFX", "started_at": "2026-04-19T01:00-03:00" }
  }
}
```

**Bucle principal:**

```
while FLOW.json["flow"][tu_id] == true:
    1. git pull origin main
    2. leer FLOW.json["tareas_asignadas"][tu_id]
       - si tenés tarea → ejecutarla
       - si no tenés → dejar un ping en agents/inbox/para-zeus-<tu_id>.md ("necesito tarea")
    3. al terminar una tarea:
       a. correr smoke test
       b. si pasa → commit + push a origin (este repo NUEVO, nunca DECK)
       c. dejar reporte en agents/inbox/<tu_id>-<timestamp>.md con status=done
       d. limpiar FLOW.json["tareas_asignadas"][tu_id]
    4. sleep (o esperar próximo ciclo de tu cron)

# Cuando FLOW.json[tu_id] == false → te dormís. Ver "Cómo dormir".
```

---

## 4. Smoke test OBLIGATORIO

Antes de commitear cualquier cambio de código:

```
".engine/Godot_v4.6.2-stable_win64_console.exe" --headless --path project --script tools/smoke.gd
```

- Exit 0 + sin "SCRIPT ERROR" / "Parse Error" → OK, podés commitear.
- Si falla → **no commitees**. Dejá el reporte con `status: failed` en el inbox. Zeus decide.

Cambios que NO tocan `.gd` ni `.tscn` (solo docs, CSV, JSON, markdown) pueden pushearse sin smoke gate, pero es buena práctica correrlo igual.

---

## 5. Reglas vivas del panteón

- **⏸️ FREEZE DE CARTAS (REFORZADO 2026-04-19)**: **NINGÚN agente** agrega filas a `project/data/cards.csv`. Ver `agents/FREEZE.md`. Violaciones → rollback automático + log en `ERRORS.md`. Balance/rework/flavor de cartas existentes sí. Reliquias/enemigos/eventos/pociones/keywords/specs sí. Cartas nuevas: **NO**.
- **🎨 Foco UX/encuadre** (2026-04-19): cada recuadro alineado, scroll suave, `Tween.TRANS_QUART + EASE_OUT` consistente.
- **🪢 Tipos explícitos** siempre. Si `var x := dict.get(...)` crashea el parser → `var x: Tipo = dict.get(...)`.
- **📦 Tu branch**: `feat/<tu_id>-<slug>` para código. Docs/datos directo a `main` de NUEVO.
- **🚫 Nunca toques**: token de GitHub en remotes, `.env*`, archivos fuera de `D:\code\TONY\` (o su equivalente).

---

## 6. Comunicación con Zeus

- **Reportar tarea terminada** → `agents/inbox/<tu_id>-<YYYYMMDD-HHMMSS>.md`
- **Pedir tarea** (si estás en flow sin asignación) → `agents/inbox/para-zeus-<tu_id>.md`
- **Escalar un bug o duda** → `agents/inbox/escalado-<tu_id>.md` con detalles
- **Bug que vos introdujiste y ya arreglaste** → registrar en `agents/ERRORS.md` (histórico)

Zeus lee el inbox cada 10 min. Respuestas típicas:
- Si tu commit pasa el test → lo mergea a DECK, tu EVO queda registrada en `mejoras.json`.
- Si falla → rollback en NUEVO, entrada en `ERRORS.md`, te escala con el reporte.

---

## 7. Cómo dormir (quedar idle)

Cuando `FLOW.json["flow"][tu_id] == false`:
1. Cerrá tu tarea actual si la terminaste (o dejala `wip` en el inbox).
2. Actualizá `agents/sessions/<tu_id>.md` con `Estado: idle`.
3. Parar el loop (no llamar a ScheduleWakeup/CronCreate de nuevo).

Antonio puede volverte a prender cambiando el valor a `true` y volviendo a lanzar tu loop.

---

## 8. Atajo — tu primer ciclo

1. `git pull origin main`
2. Leer `agents/sessions/<tu_id>.md` (quién sos + prompt de loop)
3. Leer `agents/PROTOCOLO.md` (reglas del sistema)
4. Leer `agents/ROADMAP_AGENTES.md` + `agents/PROYECCION_100.md` (qué hay por hacer)
5. Leer `agents/ERRORS.md` (bugs activos a evitar)
6. Leer `agents/FLOW.json` (si estás en flow, qué tarea tenés)
7. Ejecutar.

---

## Resumen operativo

| Qué | Dónde | Cuándo |
|-----|-------|--------|
| Tu identidad | `agents/sessions/<tu_id>.md` | primer inicio |
| Flow on/off + asignación | `agents/FLOW.json` | cada ciclo |
| Cola de tareas | `agents/PROYECCION_100.md` | cuando pedís tarea |
| Reportar tarea done | `agents/inbox/<tu_id>-<ts>.md` | al terminar |
| Test previo a commit | `tools/smoke.gd` | siempre |
| Destino de tus commits | **NUEVO** (este repo), nunca DECK | siempre |

Zeus controla el flujo hacia DECK. Vos enfocate en tu tarea, dejá el merge al CEO.
