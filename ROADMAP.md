# Hoja de ruta — Solitario TG FUTX

## Visión

Construir un solitario Klondike premium para Telegram Mini Apps: atractivo, fluido, justo, rejugable y con competición social. El juego vive en este repositorio independiente y no debe modificar ni depender del frontend o backend principal de FUTX durante las primeras etapas.

**Repositorio:** `nicolamona/solitario-tg-futx`  
**Publicación prevista:** GitHub Pages  
**Principios:** primero fiabilidad; después retención y competición; integración FUTX solo cuando exista una API segura y aprobada.

## Estado de implementación (19/10/2026)

Se ha integrado un bloque ampliado de funciones locales en la rama principal: guardado/recuperación, distribución reproducible, modo de robar 1 o 3, reto diario por fecha UTC, temas, reducción de animaciones, sonido opcional, XP/niveles locales, compartir resultados, rehacer movimientos, estadísticas y misiones locales, reversos cosméticos y celebración animada de victoria. La sintaxis JavaScript y las referencias de elementos HTML se comprobaron. Estas comprobaciones no sustituyen pruebas manuales completas en móvil/Telegram.

Las clasificaciones globales, competición real entre amigos con resultados verificados y sincronización quedan pendientes de un backend seguro. La integración FUTX no se ha activado.

## Etapa 0 — Proteger la versión actual

- Mantener una versión estable recuperable antes de cada cambio importante.
- Separar trabajo en ramas o cambios pequeños y verificables.
- No editar `nicolamona/futx-miniapp-demo` ni otros repositorios FUTX para desarrollar este juego.
- Registrar los cambios y comprobar que GitHub Pages publica los archivos esperados.
- Añadir una lista manual de pruebas para móvil y Telegram.

**Criterio de salida:** la versión estable puede recuperarse y el juego sigue abriendo desde su URL pública.

## Etapa 1 — Motor de juego sólido

- Revisar reglas Klondike: robar 1 y robar 3 como modalidades separadas.
- Corregir y probar selección, movimientos de secuencias, bases, mazo y reciclado del descarte.
- Hacer que deshacer restaure exactamente tablero, puntuación y estado del cronómetro.
- Añadir guardar y recuperar una partida localmente, con opción de empezar de cero.
- Evitar confirmaciones intrusivas cuando el entorno Telegram no las maneje bien.
- Añadir una opción de repetir la misma distribución para practicar y comparar resultados.
- Mejorar sugerencias para priorizar descubrir cartas ocultas y liberar columnas, no solo encontrar cualquier movimiento.
- Probar partidas ganadas, bloqueadas, reinicios y límites de pantalla.

**Criterio de salida:** las reglas esenciales y la restauración de movimientos pasan una lista de pruebas repetible sin perder cartas ni duplicarlas.

## Etapa 2 — Experiencia premium

- Animaciones breves y consistentes al repartir, mover, voltear y completar bases.
- Efectos visuales de victoria, rachas y nuevos récords, con opción de reducir movimiento.
- Sonidos y vibración opcionales, siempre apagables.
- Temas visuales: Esmeralda, Obsidiana, Zafiro y Oro; reversos de cartas combinables.
- Interfaz accesible en pantallas pequeñas, con objetivos táctiles cómodos y buen contraste.
- Menús de pausa, ajustes, reglas y ayuda contextual.
- Pantalla final con resumen y botón para compartir el resultado.

**Criterio de salida:** fluidez en móvil, sin desbordamientos, con controles accesibles y efectos que no dificulten leer o mover cartas.

## Etapa 3 — Progreso y recompensas locales

- Perfil local con nivel, XP, logros y récords personales.
- Estadísticas separadas por modalidad: victorias, tiempo, movimientos y puntuación.
- Misiones diarias y semanales, con progreso claro.
- Colección de cosméticos que se desbloquean jugando.
- Guardado resistente a recargas accidentales; opción para borrar los datos locales.
- Evitar recompensas que dependan de gastar dinero o que otorguen ventaja competitiva.

**Criterio de salida:** el progreso persiste en el mismo dispositivo y puede reiniciarse de forma explícita. Indicar que el progreso local no se sincroniza entre dispositivos.

## Etapa 4 — Desafío diario y competición social

- Distribución diaria compartida, generada de manera determinista para que los participantes reciban el mismo reto.
- Resumen de resultado con modalidad, distribución, tiempo, movimientos y puntuación.
- Retos entre amigos mediante enlace de invitación o código de partida.
- Clasificación global y semanal solo después de disponer de un servicio backend.
- Validación del resultado en servidor o mecanismos anti-trampas proporcionales; no confiar en puntuaciones enviadas sin verificar desde el navegador.
- Controles de privacidad, alias visibles, bloqueo de abuso y reglas claras de clasificación.
- Diseñar la clasificación para comparar partidas equivalentes y no mezclar modos o reglas distintas.

**Criterio de salida:** los retos son reproducibles y los rankings no dependen únicamente de datos manipulables desde el cliente.

## Etapa 5 — Arquitectura para funciones online

GitHub Pages puede alojar el frontend estático, pero no es por sí solo una base de datos ni un backend de confianza.

Antes de añadir cuentas, sincronización o rankings, elegir y documentar un backend adecuado. Diseñar una API con autenticación, validación de entradas, límites de uso, protección de secretos, copias de seguridad y política de privacidad.

- Mantener el frontend funcional aunque la conexión falle.
- Separar puntuaciones locales de resultados verificados.
- No incluir claves privadas, tokens de bot ni secretos en `index.html`, `style.css` o `game.js`.
- Revisar privacidad y minimización de datos antes de guardar identificadores de Telegram.
- Documentar cómo desactivar el servicio online sin romper el modo individual.

**Criterio de salida:** contrato de API documentado, pruebas de errores y seguridad básicas, y modo offline todavía jugable.

## Etapa 6 — Integración futura con FUTX (opcional)

Esta etapa no debe comenzar hasta que el usuario decida explícitamente cómo conectar ambos proyectos y exista un endpoint autorizado y seguro.

- Mantener Solitario TG FUTX como repositorio independiente.
- Definir con precisión qué datos se comparten y para qué.
- Verificar identidad y acciones en backend; nunca confiar en el cliente para conceder saldos, artículos o recompensas.
- No guardar claves del bot ni secretos FUTX en el frontend.
- Comenzar, si se aprueba, por una integración de solo lectura o cosmética.
- Cualquier recompensa FUTX debe ser limitada, auditable, anti-repetición y aprobada en el backend.
- No modificar el proyecto principal de FUTX como parte del desarrollo normal del solitario.

**Criterio de salida:** revisión de seguridad y pruebas en entorno controlado antes de habilitar cualquier operación real.

## Orden recomendado

1. Etapa 0 — proteger la versión estable.
2. Etapa 1 — motor de juego y pruebas.
3. Etapa 2 — pulido premium.
4. Etapa 3 — progreso y cosméticos locales.
5. Etapa 4 — desafíos y competición.
6. Etapa 5 — backend online.
7. Etapa 6 — integración FUTX, solo si se aprueba.

## Lista de comprobación antes de publicar cambios

- [ ] El tablero carga en móvil y Telegram.
- [ ] Robar, reciclar el mazo y deshacer funcionan.
- [ ] Se pueden mover secuencias válidas y descubrir cartas ocultas.
- [ ] Las bases solo aceptan cartas válidas.
- [ ] Puntuación, movimientos y tiempo se actualizan correctamente.
- [ ] Reiniciar y nueva partida se distinguen y piden confirmación cuando corresponde.
- [ ] No se pierden cartas ni se duplican durante una partida de prueba.
- [ ] El juego sigue siendo utilizable sin sonido y con movimiento reducido.
- [ ] Los errores de red no bloquean el modo individual.
- [ ] Ningún secreto ni operación privilegiada se expone en el frontend.
- [ ] El proyecto principal de FUTX permanece intacto.

## Fuera de alcance por ahora

- Modificar otros repositorios FUTX.
- Premios económicos, transferencias de saldo o recompensas automáticas.
- Rankings que acepten puntuaciones sin validación.
- Añadir dependencias o infraestructura online antes de definir su necesidad, coste y seguridad.
