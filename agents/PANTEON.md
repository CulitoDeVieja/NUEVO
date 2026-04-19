# Panteón — Ragnarok

Todos los agentes del sistema multi-agente. Cada uno es un personaje con identidad, rol, y prompt de loop listo para activar.

**Cómo activar un agente:**
1. Abrí una terminal nueva en `D:\code\TONY`.
2. Corré `claude`.
3. Abrí `agents/sessions/<agente>.md` y copiá el prompt de loop.
4. En Claude Code, ejecutá: `/loop 10m <prompt copiado>`.
5. Dejá la terminal abierta.

El filesystem es el backbone — todos escriben en `agents/` y se sincronizan por git push/pull.

---

## 🌙 Activos hoy

| Avatar | ID | Rol | Estado |
|--------|----|----|--------|
| 👑 | **zeus** | CEO — coordinador + arquitecto | active (esta sesión) |
| 🎭 | **psique** | narrativa + data-only | active (remote Linux) |
| 🔭 | **scout-ideas** | explorador de ideas de juegos | active |
| 🔧 | **programador-agente** | implementa mejoras de código | active (IA externa, no sigue protocolo) |

## 🛌 En panteón — listos para despertar

| Avatar | ID | Rol |
|--------|----|----|
| 🕊️ | **hermes** | mensajero externo, dashboards, Telegram |
| 🔎 | **lupa** | QA visual (co-pulidor de UI con Zeus) |
| 🔨 | **hefesto** | builds, exports, CI, validación JSON |
| 🦉 | **atenea** | balance y estrategia de diseño |
| 🎵 | **apolo** | audio, música, SFX procedurales |
| 🏹 | **artemisa** | testing automatizado, smoke, Monte Carlo |
| 🍇 | **dioniso** | polish, juice visual, partículas |
| 🌊 | **poseidon** | gameplay core, keywords pendientes |
| ⚔️ | **ares** | combate específico, impacto, IA |
| 🌹 | **afrodita** | UI, estética, encuadre perfecto |
| ⏳ | **cronos** | scheduler, crons, timing de agentes |
| 🌙 | **morfeo** | narrativa onírica, flavor text, diálogos |
| 🔮 | **hecate** | Acto III horror cósmico |

**Total: 16 agentes** (4 activos + 12 durmientes + 1 externa).

---

## Reglas del panteón

1. **Un agente, una identidad.** No superponer roles.
2. **Smoke test obligatorio** antes de commitear código.
3. **Freeze de cartas** vigente — ningún agente agrega a `cards.csv` hasta nuevo aviso de Antonio.
4. **Directiva UX/encuadre** vigente (2026-04-19): todos priorizan renderizado impecable.
5. **Reportes a `agents/inbox/<id>-<ts>.md`.** Zeus procesa cada 10 min.
6. **Conflictos de archivo**: el segundo en llegar hace rebase + resuelve.
7. **Al morir o desconectar**: actualizar tu `sessions/<id>.md` con estado `disconnected` y motivo.

---

## Proyecto de dashboard visual

`tools/dashboard_gen.py` genera `agents/DASHBOARD.html` con cada agente como personaje (avatar + stats + última actividad + EVOs entregadas). El cron de Zeus lo regenera cada ciclo.
