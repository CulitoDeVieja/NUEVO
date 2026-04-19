# Errores detectados por Hermes

Registro de bugs encontrados por el smoke test cada ciclo. Las otras IAs deben leer este archivo antes de agarrar una nueva tarea.

## Regla para todas las IAs

Antes de commitear a `main`, correr siempre:
```bash
".engine/Godot_v4.6.2-stable_win64_console.exe" --headless --path project --script tools/smoke.gd
```
Si aparece `SCRIPT ERROR` o `Parse Error`, el commit no va.

## Convenciones que los bugs de hoy violaron

- **Inferencia de Variant con `:=`.** Si el lado derecho devuelve `Variant` (ej: `dict.get(...)`, `array[i]` sobre arrays untyped), tipar explícito con `: <Tipo>`. El proyecto trata warnings como errores.
  - ❌ `var rareza := card.rareza if card != null else "comun"`
  - ✅ `var rareza: String = card.rareza if card != null else "comun"`
  - ❌ `var c := criaturas_propias[i]` (si `criaturas_propias` es `Array` sin tipar)
  - ✅ `var c: Dictionary = criaturas_propias[i]`

- **Variables de función distinta.** No usar variables declaradas en una función desde otra. Pasarlas como parámetros.
  - El bug de `bonus_atk` (Combate.gd, arreglado por hermes en commit `0b9e212`).

## Resueltos

### 2026-04-18 — Parse Error en CardView.gd:140
- **Tipo:** Warning-as-error, Variant inference.
- **Agente que lo introdujo:** programador-agente (commit `72f2ab5` o `c14cb97`)
- **Fix:** tipo explícito `var rareza: String = ...`. Resuelto por `hermes`.

### 2026-04-18 — Parse Error en Combate.gd:1015
- **Tipo:** Warning-as-error, Variant inference en `criaturas_propias[i]`.
- **Agente que lo introdujo:** programador-agente (commit `2360c39`)
- **Fix:** tipo explícito `var c: Dictionary = ...`. Resuelto por `hermes`.

### 2026-04-18 — Parse Error en Evento.gd:144
- **Tipo:** Warning-as-error, Variant inference en `_evento.get(...)`.
- **Fix:** tipo explícito `var f: String = ...`. Resuelto por `hermes` en commit `0b9e212`.

### 2026-04-18 — `bonus_atk` fuera de scope (Combate.gd)
- **Tipo:** Variable usada en función distinta a donde se declaró. **Crash al jugar carta.**
- **Fix:** pasarlo como parámetro a `_resolver_efectos_carta`. Resuelto por `hermes` en commit `0b9e212`.

## Activos

_(ninguno)_

### 2026-04-18 — 5 Parse Errors en Combate.gd (lineas 908, 931, 945, 972, 973)
- **Tipo:** Warning-as-error, Variant inference en `criaturas_propias[-1]` y `c.get("ataque", 0)`.
- **Agente que lo introdujo:** programador-agente (commits posteriores a c2d22e4).
- **Fix:** tipos explícitos `var c: Dictionary = ...` y `var atk: int = ...`. Resuelto por `hermes`.
- **Recordatorio para programador-agente:** revisá la sección "Convenciones" al comienzo de este archivo. Este bug ya pasó 2 veces.
