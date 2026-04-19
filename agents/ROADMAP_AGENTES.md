# Hoja de ruta — 20 tareas por agente

Asignaciones P0 priorizadas para cada agente del sistema multi-agente Ragnarok. Alineadas con `docs/ROADMAP.md` (rumbo hacia Early Access en ~6 meses) y con las 5 reglas de filtro (Fun first, Vertical slice, Juice día 1, Playtest continuo, apunta a EA).

Cada agente toma de su lista en orden, reclamándola en `assignments.json`. Al terminar, reporte en `inbox/` + Hermes registra EVO-NNN.

---

## 🔧 gameplay-programmer (mecánicas, keywords, combate)

1. Keyword Veneno: fichas + 1 dmg/turno/ficha con stack.
2. Keyword Congelar: bloquea 1 turno de la criatura objetivo.
3. Keyword Silenciar: remueve todas las keywords y efectos.
4. Keyword Sobrecarga: bloquea N cristales de maná al próximo turno.
5. Keyword Afilar: +1/+0 cada turno que la criatura está en mano.
6. Keyword Ritual: efecto extra si se cumple condición (jugar 2 hechizos antes).
7. Keyword Eco: la carta se puede jugar múltiples veces en el mismo turno.
8. Keyword Descubrir: overlay con 3 cartas, elegís 1 a la mano.
9. Estertor completo con efectos variados (no solo daño al morir).
10. Stack de resolución con orden deterministic (Veneno post-ataque, Estertor pre-triggers).
11. Autoguardado de run al ganar cada nodo.
12. Cerrar el juego y retomar la run exactamente donde quedó.
13. Sistema de Ascensiones nivel 0-20 (dificultad progresiva, efectos acumulativos).
14. Mapa: ganar un nodo desbloquea solo los conectados siguientes.
15. Mulligan inicial: descartar N cartas y robar de nuevo.
16. Combo tracker: contador visual + bonus si jugás N cartas en un turno.
17. Buff/debuff persistente entre turnos (con ícono y contador).
18. Escudo apilable coexistiendo con armadura.
19. Provocar enemigo: enemigos defienden a su jefe.
20. Sigilo (reveal on attack) con interacción de Provocar.

---

## 🎨 ui-programmer (UI, animaciones, polish visual)

1. Tooltips de keywords consistentes en Combate + Recompensa + Colección.
2. Animación de carta al ir al cementerio (flip + fade).
3. Indicador visual de combo: contador + borde pulsante al jugar 2ª carta del turno.
4. Previsualización de daño al hover: muestra "harías X daño" antes de clickear.
5. Pantalla de pausa durante combate (ESC en combate).
6. Shortcuts teclado: 1-9 jugar carta N, Espacio fin turno, Tab ver mazo.
7. Animación de reliquia nueva al obtenerla (zoom + glow + SFX).
8. Log scrolleable de daño/curación en combate (panel lateral).
9. Pantalla post-run con estadísticas (daño total, turnos, cartas top).
10. Pantalla de muerte con contexto (qué jugaste en el último turno).
11. Transición mask entre escenas (wipe diagonal mapa↔combate).
12. Parallax 2 capas en fondo de combate reaccionando al mouse.
13. Menú de opciones: volumen, daltonismo, reduced motion, escala texto.
14. Modo daltonismo: 3 paletas (rojo-verde, azul-amarillo, monocromo).
15. Escala de texto 1.0x / 1.2x / 1.5x aplicada globalmente.
16. Opción cursor 2× tamaño.
17. Animación de curación (partículas verdes flotando al héroe).
18. Top del mazo visible (preview de próxima carta a robar).
19. Panel reliquias activas siempre visible en combate (íconos con tooltip).
20. Selector de modo en menú: Normal / Daily / Endless / Desafíos.

---

## 🃏 game-designer (cartas, balance, enemigos)

1. 10 cartas neutrales nuevas del Umbral (temática liminal).
2. 5 cartas legendarias por clase (15 totales).
3. Balance pass de costos de maná usando datos del tester.
4. 15 enemigos nuevos del Acto III con estética realidad rota.
5. 3 élites Acto III con mecánicas específicas del acto.
6. Jefe final Acto III (El Silencio) con 3 fases diferenciadas.
7. Rework del mazo inicial Caballero: curva de maná 0-1-2-3 suave.
8. Rework del mazo inicial Tecnomante.
9. Rework del mazo inicial Sombra.
10. 10 reliquias de jefe que rompen arquetipo (game-changers).
11. 5 reliquias "curse" (desventaja con beneficio grande).
12. Versión mejorada "+" de cada carta común (70 cartas mejoradas).
13. Sinergias claras por arquetipo: Aggro / Control / Combo por clase.
14. Cartas anti-combo (silencio, descartar mano enemiga).
15. Intenciones enemigas más variadas (hoy: ataque/def/buff).
16. Enemigos especializados por acto (medievales I, tech II, aliens III).
17. Rework pociones: 6 → 10 con efectos únicos no-redundantes.
18. 10 eventos narrativos Acto III (trade-offs lovecraftianos).
19. Balance pass completo con simulador Monte Carlo del tester.
20. Starter deck "learn to play" (tutorial deck con 8 cartas simples).

---

## 📖 content-writer (narrativa, eventos, diálogos)

1. 6 eventos narrativos Acto III lovecraftianos.
2. Diálogo único para los 34 enemigos (hoy 8+ tienen).
3. Diálogo pre-batalla para los 3 jefes (3 líneas mínimo c/u).
4. Diálogo de victoria/derrota por jefe (2 variantes c/u).
5. Flavor text auditado para las 195 cartas.
6. Codex de lore desbloqueable al ganar runs (entradas por carta/enemigo/reliquia).
7. Intro del juego (texto estilizado al primer New Game).
8. Epílogo único por clase al vencer Acto III.
9. 10 "cartas cósmicas" tipo tarot: eventos aleatorios de alto impacto.
10. Textos ambiente al entrar a cada nodo (combate / tienda / descanso).
11. Susurros aleatorios en Acto III (textos fragmentados de fondo).
12. Audit de nombres de cartas por facción siguiendo `docs/NAMING.md`.
13. Descripciones de reliquias con anclaje de lore.
14. Textos del tutorial interactivo (6 pasos).
15. Textos de pantalla de opciones, settings, ayudas.
16. Variaciones de texto para pantallas de recompensa.
17. Historia secreta desbloqueable al completar las 3 clases.
18. "Desafío del Umbral": evento final ultra-raro (1% probabilidad).
19. 20 líneas de flavor para pociones.
20. Textos para 30 logros/achievements.

---

## 🎲 roguelike-designer (meta-juego, rejugabilidad)

1. Daily Run con seed del día compartido globalmente.
2. Leaderboard local de Daily Run (top 10 por clase).
3. Sistema de Ascensiones 0-20 con efectos progresivos.
4. Desbloqueos narrativos: perder 3 runs dispara evento especial.
5. Desafíos semanales con reglas raras (sin robar, solo comunes, 1 HP).
6. Modo Endless post-Acto III con escalado infinito.
7. Sistema de logros con recompensas cosméticas (30 logros).
8. Codex in-game desbloqueable jugando.
9. Meta-progresión: desbloquear cartas nuevas al cumplir hitos.
10. Desbloqueo cruzado de héroes: vencer con X desbloquea poder en Y.
11. Racha de victorias con recompensa cosmética cada 5.
12. Build archetypes sugeridos al elegir héroe (Aggro / Control / Combo).
13. Estadísticas persistentes: mejor run, carta top, oro total.
14. Draft mode: elegí tu mazo completo antes de empezar.
15. Cursed mode: solo cartas "curse", multiplica oro ganado.
16. Pacifist mode: solo defensivas, desbloqueos especiales.
17. Speed mode: timer de 5 min por combate.
18. Endless Boss Rush: solo jefes seguidos con escalado.
19. Co-op hotseat 2 jugadores (turnos alternados).
20. Temporadas: reset mensual con modificadores globales.

---

## 🧪 tester (QA, simulación, regresión)

1. Simulador Monte Carlo 1000 runs por clase reporteando cartas OP/UP.
2. Suite de tests unitarios por keyword (16 tests mínimo).
3. Tests de regresión de combate (ataque, defensa, muerte).
4. Tests de flujo completo de una run (script end-to-end).
5. Tests de persistencia (save/load + restart).
6. Tests de UI en 1920×1080, 1280×720, 3840×2160.
7. Profiling de performance por escena (FPS mínimo 60).
8. Runtime test de todas las pantallas (ampliar test_evoluciones.gd).
9. Validación de balance por enemigo (HP/daño/curva).
10. Fuzzer de interacciones: generar 1000 combos aleatorios, detectar crashes.
11. Tests de filtros en UI (colección, evoluciones).
12. Detectar cartas "muertas" (0 picks en 1000 runs).
13. Reporte de curva de dificultad por acto (tiempo promedio, muerte ratio).
14. Validación de `cards.csv`: IDs únicos, campos completos, costos válidos.
15. Tests de variedad de IA enemiga (no debe ser 100% predecible).
16. Balance de reliquias: pick rate + win rate correlacionado.
17. Regresión visual: screenshots comparativas pre/post cambio.
18. Stress test: 100+ criaturas en campo sin caída de FPS.
19. Tests de audio: todos los SFX se disparan en sus eventos correctos.
20. Tests de accesibilidad: navegación completa con teclado.

---

## Reglas de la hoja de ruta

- **Orden importa.** Las primeras 5 de cada lista son las más urgentes para llegar al próximo hito (Paso 4-5 del ROADMAP: reliquias serias + 3 clases pulidas).
- **No saltear de lista.** Si sos `ui-programmer` no toques gameplay. Si el BACKLOG tiene una tarea que pisa otro rol, coordinar con Hermes antes.
- **Actualizar al terminar.** Cuando completés una tarea, tacharla acá también (o pedile a Hermes que lo haga al procesar tu reporte).
- **Filtro de ideas.** Si Antonio propone algo nuevo, Hermes evalúa con las 5 reglas y lo inserta donde corresponda (o lo descarta con justificación).
