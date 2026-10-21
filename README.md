# Caranqui FPS (prototipo, Parcial 1)

Prototipo de shooter en primera persona estilo "boomer shooter" clásico, ambientado en la resistencia Caranqui frente a los soldados del imperio Inca. Hecho en **Unity 6 (6000.0.71f1, URP)** usando **únicamente Visual Scripting**, sin scripts de C#.

Proyecto para la materia ISWZ3411 – Desarrollo de Videojuegos (UDLA, 202710).

## Cómo jugar
- **WASD**: moverse
- **Mouse**: mirar
- **Clic izquierdo**: disparar la honda
- Elimina **10 enemigos** para ganar. Si tu vida llega a 0, la partida se reinicia.

## Mecánicas
- **Movimiento y cámara**: `CharacterController` y rotación con el mouse (grafos de movimiento y cámara).
- **Disparo**: Raycast (hitscan) desde la cámara. Si golpea un objeto con tag `Enemy`, activa su muerte.
- **Enemigos**: persiguen al jugador (`FindWithTag` + `MoveTowards`), atacan con tiempo de espera entre golpes y siempre se orientan hacia la cámara (billboard). Tienen animaciones de caminar, ataque, impacto y muerte (Animator). El cadáver se queda en el suelo.
- **Spawner**: instancia (`Instantiate`) un prefab de enemigo cada 3 segundos en posiciones aleatorias, hasta 10.
- **Variables**: `vida` y `kills` en el jugador; el HUD y la pantalla de victoria las leen.
- **HUD**: barra inferior con vida y bajas. Munición y armadura son decorativas por ahora.
- **Animaciones**: honda (Animator con trigger `Disparo`) e inca (caminar, ataque, impacto, muerte).

## Estructura
- `Assets/Grafos`: grafos de Visual Scripting (movimiento, disparo, enemigo, spawner, salud, victoria, HUD).
- `Assets/Animaciones`: controladores y clips.
- `Assets/Sprites`: sprites de la honda, el inca y el HUD.

## Uso de IA
Los gráficos (sprites de la honda, de los enemigos, objetos y el HUD) fueron **generados con IA**. El desarrollo del prototipo se hizo con asistencia de IA (Claude) para generar los grafos de Visual Scripting. El diseño del juego, el armado de la escena, las pruebas y la depuración fueron hechos por el autor.

## Autor
Alexander Vinueza – Quilla Interactive
