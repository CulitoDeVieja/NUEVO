# Track de zeus (ex-hermes)

## 2026-04

- **EVO-092** — Alineación perfecta: tarjetas Evoluciones centradas en viewport
  Las tarjetas de Evoluciones estaban apoyadas a la izquierda del VBox (descentradas 400px del centro). Ahora cada una va envuelta en HBoxContainer centrado. El botón volver-arriba tiene margen simétrico de 32px.

- **EVO-089** — Botón volver arriba en Evoluciones
  Cuando scrolleás más de 500 píxeles en Evoluciones, aparece fade-in un botoncito redondo con una flecha hacia arriba en la esquina. Lo clickeás y la lista vuelve al inicio con una animación suave. Desaparece automáticamente cuando ya estás arriba.

- **EVO-086** — Contador animado + celebración al ver todas las mejoras
  Cada vez que pasás por una tarjeta nueva, el subtítulo pulsa con el color de la categoría y achica el contador. Cuando pasás por la última nueva, la pantalla se ilumina en dorado, suben 20 estrellitas giratorias y suena el acorde de victoria. Sentís que descubriste todo.

- **EVO-085** — Stagger al entrar a Evoluciones
  Cuando entrás a Evoluciones, las primeras 12 tarjetas aparecen una detrás de otra con un fade y un ligero slide desde abajo. Se siente menos sopa y más narrado. Las que quedan abajo (no se ven) aparecen al toque sin delay para no trabar el scroll.

- **EVO-084** — Dopamina al pasar: destello al hover sobre mejora nueva
  Al pasar el cursor por encima de una mejora que nunca viste, la tarjeta rebota suave, se ilumina con el color de la categoría, saltan 4 partículas brillantes y suena el arpegio de destello. Se marca como vista al instante y queda guardado. Si ya la pasaste antes, no destella de nuevo. El click sigue abriendo el detalle grande como antes.

- **EVO-080** — Destello dopamínico sobre mejoras nuevas
  En la pantalla de Evoluciones, las mejoras que todavía no viste aparecen con un cartelito dorado de "NUEVO" que pulsa. Cuando pasás el cursor encima por primera vez, la tarjeta rebota, se ilumina con el color de la categoría y saltan partículas. Una vez visto, queda guardado y ya no destella más.
