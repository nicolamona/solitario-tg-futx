# Solitario TG FUTX

Solitario Klondike en español, con una mesa premium esmeralda y dorada, diseñado para móvil y Telegram Mini Apps.

## Funciones disponibles

- Tablero Klondike: mazo, descarte, siete columnas y cuatro bases.
- Modos de robar 1 o 3 cartas.
- Mover cartas con toque/clic; arrastrar en escritorio.
- Deshacer, sugerencias, cronómetro, puntuación y movimientos.
- Guardado automático local y recuperación al volver a abrir.
- Repetir la misma distribución y reto diario determinista por fecha UTC.
- Temas Esmeralda, Obsidiana, Zafiro y Oro real.
- Preferencia para reducir animaciones y efectos de sonido opcionales.
- XP y niveles locales; las victorias otorgan XP.
- Compartir el resumen de una partida mediante las opciones del dispositivo.
- Animaciones de selección, cartas y celebración de victoria con partículas (respetan movimiento reducido).
- Rehacer además de deshacer, y doble toque sobre una carta para intentar subirla a una base.
- Panel de estadísticas locales, misiones orientativas, logros y colección cosmética por victorias.
- Reversos de cartas: clásico, océano, aurora y real.
- Diseño adaptable y soporte básico de Telegram Web Apps.

## Progreso y privacidad

El progreso, las preferencias, la partida y el récord se guardan en el almacenamiento local del navegador. No hay cuentas ni sincronización entre dispositivos. Borrar el almacenamiento del navegador elimina estos datos. El reto diario comparte una distribución por fecha, pero todavía no tiene clasificación online ni validación en servidor.

## Publicar con GitHub Pages

1. Abre **Settings → Pages**.
2. En **Build and deployment**, elige **Deploy from a branch**.
3. Selecciona la rama `main` y la carpeta `/ (root)`, y guarda.
4. Espera a que GitHub publique el sitio. La dirección suele ser `https://nicolamona.github.io/solitario-tg-futx/`.

Para abrirlo como Mini App, utiliza la URL HTTPS publicada en el botón de tu Mini App o en la configuración de tu bot de Telegram.

## Siguiente fase

Para clasificaciones globales, retos entre amigos con resultados verificados o sincronización, hace falta un backend de confianza. GitHub Pages solo aloja el frontend; no se deben simular rankings reales ni confiar en puntuaciones enviadas por el navegador. La integración con FUTX queda fuera hasta que se apruebe explícitamente y exista una API segura.
