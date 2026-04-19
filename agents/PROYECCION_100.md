# Proyección 100 — Hoja de ruta larga de Ragnarok

**Mantenida por:** Zeus (CEO).
**Actualización:** cada 10 min durante el análisis profundo. A medida que los agentes entregan EVOs, Zeus tacha o ajusta ítems acá y suma nuevos al final del horizonte correspondiente para mantener el colchón en ~100.
**Basada en:** `docs/ROADMAP.md` (10 pasos) + `agents/ROADMAP_AGENTES.md` (120 tareas por rol) + tandas del scout-ideas (EVOs 81, 82, 87, 88).

Cada ítem apunta al paso del ROADMAP al que contribuye y al agente responsable sugerido.

---

## HORIZONTE 1 — Pre-Early Access (próximos 3 meses, Pasos 4-7) — 40 tareas

### 🔧 Gameplay core (10)
1. **Keyword Veneno** con fichas apilables (1 dmg/turno/ficha). → `gameplay-programmer`
2. **Keyword Congelar** — bloquea 1 turno de criatura objetivo. → `gameplay-programmer`
3. **Keyword Silenciar** — remueve keywords y efectos del objetivo. → `gameplay-programmer`
4. **Keyword Sobrecarga** — bloquea N cristales de maná el próximo turno. → `gameplay-programmer`
5. **Stack de resolución deterministic** (Veneno post-ataque → Estertor pre-triggers). → `gameplay-programmer`
6. **Autoguardado de run** al ganar cada nodo + resume al reabrir. → `gameplay-programmer`
7. **Mapa progresivo**: ganar un nodo desbloquea solo los conectados siguientes. → `gameplay-programmer`
8. **Sistema de Ascensiones 0-10** (efectos acumulativos). → `gameplay-programmer`
9. **Mulligan inicial**: descartar N cartas y robar de nuevo. → `gameplay-programmer`
10. **Combo tracker**: contador visual + bonus al jugar 3+ cartas/turno. → `gameplay-programmer`

### 🃏 Contenido (8)
11. **15 enemigos Acto III** con estética realidad rota. → `game-designer`
12. **3 élites Acto III**. → `game-designer`
13. **Jefe final Acto III (El Silencio)** con 3 fases. → `game-designer`
14. ⏸️ **10 cartas neutrales del Umbral** — PAUSADO por Antonio 2026-04-18. → `game-designer`
15. ⏸️ **5 legendarias por clase** (15 totales) — PAUSADO por Antonio 2026-04-18. → `game-designer`
16. **10 reliquias de jefe** (game-changers). → `game-designer`
17. **5 reliquias "curse"** (desventaja con beneficio). → `game-designer`
18. **10 eventos narrativos Acto III** (lovecraftianos). → `content-writer`

### 🎨 UI / Polish (12)
19. **Tooltips keywords** consistentes (Combate/Colección/Recompensa). → `ui-programmer`
20. **Previsualización daño al hover** (considera armadura + reliquias + estados). → `ui-programmer`
21. **Animación de robo** (carta vuela desde mazo a mano). → `ui-programmer`
22. **Pantalla post-run** con stats (daño total, cartas top, turnos). → `ui-programmer`
23. **Pantalla de muerte con contexto** (qué jugaste en el último turno). → `ui-programmer`
24. **Transición mask** entre escenas (wipe mapa↔combate). → `ui-programmer`
25. **Menú opciones**: volumen, daltonismo, reduced motion, escala texto. → `ui-programmer`
26. **Paletas daltónicas** (3: rojo-verde, azul-amarillo, monocromo). → `ui-programmer`
27. **Escala texto global** 1.0x / 1.2x / 1.5x. → `ui-programmer`
28. **Shortcuts teclado** completos (1-9 carta, Espacio fin turno, Tab mazo, Esc pausa). → `ui-programmer`
29. **Animación de reliquia** al obtenerla (zoom + glow + SFX). → `ui-programmer`
30. **Parallax** 3 capas en fondo de combate (mouse-reactive). → `ui-programmer`

### 🔊 Audio (4)
31. **Música ambiental por acto** (3 loops refinados). → `ui-programmer`
32. **Heartbeat SFX** cuando HP héroe < 25%. → `ui-programmer`
33. **Stinger legendaria/épica** al robarla. → `ui-programmer`
34. **Voces crípticas / susurros Acto III** (panning inverso procedural). → `ui-programmer`

### 📖 Narrativa (3)
35. **Diálogos únicos** para los 34 enemigos (hoy 8+). → `content-writer`
36. **Diálogos pre/post batalla** de los 3 jefes (3 líneas mínimo c/u). → `content-writer`
37. **Flavor text audit** para las 195 cartas siguiendo `docs/NAMING.md`. → `content-writer`

### 🎲 Meta (3)
38. **Daily Run** con seed del día compartido. → `roguelike-designer`
39. **Leaderboard local** del Daily Run (top 10 por clase). → `roguelike-designer`
40. **Sistema de 30 logros** con recompensas cosméticas. → `roguelike-designer`

---

## HORIZONTE 2 — Early Access → 1.0 (6-12 meses, Pasos 8-9) — 25 tareas

### 🧠 Expansión de reglas (6)
41. **Sistema de Rasgos** disparado por Cordura → 0 (Darkest Dungeon-like). Origen: scout IDEA 5. → `game-designer` + `gameplay-programmer`
42. **Codex de lore** desbloqueable jugando (Dark Souls-like). Origen: scout IDEA 2. → `content-writer` + `ui-programmer`
43. **Ediciones cósmicas** (foil/holo/glitch/negativo) al dropear cartas. Origen: scout IDEA 21. → `game-designer` + `ui-programmer`
44. **Objetos Alterados**: reliquias bi-estado que mutan tras N triggers. Origen: scout IDEA 22. → `game-designer` + `gameplay-programmer`
45. **Presagios del Bardo** al iniciar cada run (3 modificadores globales). Origen: scout IDEA 16. → `game-designer` + `gameplay-programmer`
46. **Visión del Umbral**: preview de combo completo antes de confirmar. Origen: scout IDEA 20. → `gameplay-programmer` + `ui-programmer`

### 🧠 Expansión de reglas (ampliación desde scout ciclo 5)
46a. **Memoria fragmentada de legendarias** (Signalis): 5 fragmentos por legendaria que se revelan por trigger hasta mutar en "Recordada". Origen: scout IDEA 23. → `content-writer` + `gameplay-programmer` + `ui-programmer`
46b. **Sinergias ocultas de reliquias** (Binding of Isaac): 10 combos con nombre propio que se descubren al cumplir condición, van al Codex. Origen: scout IDEA 24. → `game-designer` + `gameplay-programmer` + `ui-programmer`
46c. **Presión del Umbral** (Pentiment): timer visible en ~20% de eventos con stakes altos, toggle off en accesibilidad. Origen: scout IDEA 25. → `game-designer` + `content-writer` + `gameplay-programmer` + `ui-programmer`
46d. **Rituales con timer** (Cultist Simulator): cartas que cocinan N turnos y disparan efecto mayor / backlash si mueren. Origen: scout IDEA 17. → `game-designer` + `gameplay-programmer` + `ui-programmer`
46e. **Dados del Bardo** (Citizen Sleeper): mini-fase 5s pre-combate con 3 dados para gestos preparatorios. Origen: scout IDEA 19. → `game-designer` + `gameplay-programmer` + `ui-programmer`
46f. **Mensajes del Umbral** (Elden Ring): 80 frases asincrónicas pre-jefe/pre-tienda, pool local con cooldown. Origen: scout IDEA 26. → `content-writer` + `gameplay-programmer` + `ui-programmer`
46g. **Golpe Justo** (Sea of Stars): timing window de 350ms al jugar carta de ataque con +25% daño y medidor de Ritmo. Toggle accesibilidad obligatorio. Origen: scout IDEA 27. → `gameplay-programmer` + `ui-programmer`
46h. **Honestidad / Máscara** (Lies of P): eventos con par Honesta/Engaño, medidor Máscara invisible hasta Acto III cambiando epílogo. Origen: scout IDEA 28. → `content-writer` + `gameplay-programmer` + `ui-programmer`

### 🌌 Contenido post-EA (6)
47. **Acto IV secreto** desbloqueable tras 3 victorias. → `game-designer` + `content-writer`
48. ⏸️ **30 cartas nuevas** (primera mini-expansión) — PAUSADO por Antonio 2026-04-18. → `game-designer`
49. **10 reliquias nuevas** con sinergias inter-clase. → `game-designer`
50. **10 enemigos Boss Rush**. → `game-designer`
51. **5 eventos endgame** lovecraftianos profundos. → `content-writer`
52. **Modo Horde**: oleadas infinitas con escalado. → `roguelike-designer`

### 🎮 Modos (5)
53. **Modo Endless** post-Acto III con leaderboard. → `roguelike-designer`
54. **Modo Pacifist** (solo defensivas, desbloqueo único). → `roguelike-designer`
55. **Modo Cursed** (solo curse, 2× oro). → `roguelike-designer`
56. **Modo Speed** (timer 5min por combate). → `roguelike-designer`
57. **Modo Draft** (elegí tu mazo antes de empezar). → `roguelike-designer`

### 🏛️ Social & hub (5)
58. **Desafíos semanales** con reglas raras. → `roguelike-designer`
59. **Hub narrativo tipo Hades** con NPCs filosóficos. Origen: scout IDEA 1. → `game-designer` + `content-writer` + `ui-programmer`
60. **Compartir runs** (código o imagen auto-generada). → `roguelike-designer`
61. **Steam Workshop** para mazos compartidos. → `gameplay-programmer`
62. **Discord webhook** para logros (opt-in). → `tester`

### 🔧 Tech (3)
63. **PvP hotseat local** (2 jugadores mismo PC). → `gameplay-programmer`
64. **Build macOS nativa**. → `tester`
65. **Telemetría local de balance** (pick/win rate agregado). → `tester`

---

## HORIZONTE 3 — Post-1.0 / Expansión (año 2, Paso 10) — 20 tareas

### ⚔️ PvP online (5)
66. **Matchmaking ELO**. → `gameplay-programmer`
67. **Ligas rankeadas** con reset mensual. → `roguelike-designer`
68. **Replays** con scrub timeline. → `gameplay-programmer`
69. **Espectador mode**. → `ui-programmer`
70. **Temporadas rankeadas** con rewards cosméticos. → `roguelike-designer`

### 📱 Móvil (5)
71. **Build iOS** + UX touch. → `ui-programmer`
72. **Build Android**. → `ui-programmer`
73. **Cloud save** cross-device (Steam Cloud + Apple/Google). → `gameplay-programmer`
74. **Controles verticales** optimizados para mobile. → `ui-programmer`
75. **Monetización cosmética respetuosa** (solo skins, sin pay-to-win). → `game-designer`

### 🌠 Expansiones (5)
76. **1ª expansión de cartas**: 60 nuevas + 2 mecánicas nuevas. → `game-designer`
77. **4ª clase: El Tejedor** (mecánica de tejido/hilos del destino). → `game-designer` + `content-writer`
78. **Acto V: La Raíz** (post-Silencio, origen del multiverso). → `game-designer` + `content-writer`
79. **20 reliquias nuevas** del Tejedor. → `game-designer`
80. **Soundtrack OST completo** licenciable. → `ui-programmer`

### 🔁 Retención (5)
81. **Temporadas mensuales** con modificadores globales. → `roguelike-designer`
82. **Battle Pass cosmético 100% gratuito**. → `roguelike-designer`
83. **Eventos temporales** (Halloween, fin de año) con cartas temporales. → `content-writer`
84. **Ligas mensuales** con rewards. → `roguelike-designer`
85. **Sistema de clanes/guildas** con progresión compartida. → `gameplay-programmer`

---

## HORIZONTE 4 — Legado / Visión lejana (año 3+) — 15 tareas

### 🛠️ Creación comunitaria (5)
86. **Editor de cartas in-game** (reglas declarativas). → `gameplay-programmer`
87. **Steam Workshop** para cartas y mazos custom. → `gameplay-programmer`
88. **Modos custom** (reglas editables). → `roguelike-designer`
89. **Replays compartidos con comentarios**. → `gameplay-programmer`
90. **Mod tools oficiales**. → `gameplay-programmer`

### 📜 Narrativa extendida (5)
91. **DLC "El Bardo Infinito"** (precuela cósmica). → `content-writer` + `game-designer`
92. **Campaña narrativa lineal** 8-10h separada del roguelike. → `content-writer`
93. **Voice acting** para los jefes principales. → `ui-programmer`
94. **Lore book físico** (edición coleccionista). → `content-writer`
95. **Novela gráfica del multiverso**. → `content-writer`

### 🏆 Legacy (5)
96. **Port Nintendo Switch**. → `tester`
97. **Port PlayStation**. → `tester`
98. **Port Xbox**. → `tester`
99. **Secuela conceptual: Ragnarok II — El Ciclo**. → `game-designer`
100. **Universo expandido** (board game físico, TCG coleccionable). → `game-designer`

---

## Reglas de esta proyección

- **Colchón objetivo:** ~100 ítems vivos. Cuando un agente entrega una EVO que tacha un ítem, Zeus suma una al final del mismo horizonte para mantener el 100.
- **Nunca se descarta sin justificar.** Si un ítem queda obsoleto (ej. Antonio pivotea), Zeus lo mueve a `archive/` con la razón.
- **Filtro de los 5 criterios** (PROTOCOLO): ningún ítem entra sin pasar *Fun first + Vertical slice + Juice día 1 + Playtest continuo + apunta a EA o más allá*.
- **Cross-referencia:** cada ítem que nace del scout-ideas mantiene el origen ("scout IDEA N") para trazabilidad.

## Estado del análisis

**Última actualización profunda:** 2026-04-19 (post EVO-088).
**Tareas tachadas de los horizontes:** 0 (es la proyección inicial).
**Próximo análisis:** siguiente disparo del cron.
