# Jack-Man: Un Clon de Pac-Man en Jack para Nand2Tetris

Este proyecto es una implementación del clásico juego Pac-Man, desarrollado enteramente en el lenguaje de programación Jack, diseñado para ejecutarse en la plataforma Hack simulada del curso Nand2Tetris.

## Descripción del Juego

"Jack-Man" recrea la experiencia fundamental de Pac-Man. El jugador controla a Jack-Man, un personaje que debe navegar por un laberinto comiendo todas las píldoras mientras evita a los fantasmas que lo persiguen.

**Características Principales:**

*   **Personaje Principal (Jack-Man):** Controlado por el usuario mediante las teclas de flecha.
*   **Fantasmas:** Cuatro enemigos con una IA simple que intentan capturar a Jack-Man.
*   **Laberinto:** Un entorno definido por paredes donde ocurre el juego.
*   **Píldoras (Pellets):** Pequeños puntos que Jack-Man debe comer para ganar puntos y avanzar.
*   **Puntuación:** Se lleva un registro de la puntuación actual y la más alta.
*   **Interfaz de Usuario:** Muestra la puntuación, la puntuación más alta y mensajes de estado del juego.
*   **Pantalla de Bienvenida:** Un "splash screen" con el título del juego y créditos.
*   **Reinicio del Juego:** Permite reiniciar la partida después de un "Game Over".

## Estructura del Proyecto

El juego está implementado utilizando un enfoque orientado a objetos, con varias clases Jack que manejan diferentes aspectos del juego:

*   **`Main.jack`**: Punto de entrada del programa. Inicializa y ejecuta el juego.
*   **`Game.jack`**: Clase orquestadora principal. Gestiona el flujo del juego, los estados (inicio, en curso, game over) y la interacción entre los diferentes componentes.
*   **`PacMan.jack`**: Representa al personaje Jack-Man, su movimiento, estado (capturado o no) y la lógica de comer píldoras.
*   **`Ghost.jack`**: Representa a un solo fantasma, su movimiento (IA simple y aleatoria), y la lógica para capturar a Jack-Man.
*   **`Ghosts.jack`**: Gestiona la colección de todos los objetos `Ghost`.
*   **`Pellet.jack`**: Representa una píldora individual.
*   **`Pellets.jack`**: Gestiona la colección de todas las píldoras, su distribución en el laberinto y su estado (comida o no).
*   **`Wall.jack`**: Representa un segmento de pared rectangular.
*   **`Walls.jack`**: Gestiona la colección de todos los objetos `Wall` que forman el laberinto.
*   **`Score.jack`**: Maneja la lógica de la puntuación actual y la puntuación más alta.
*   **`Label.jack`**: Clase de utilidad para mostrar texto simple en una posición específica de la pantalla.
*   **`Labels.jack`**: Gestiona una colección de objetos `Label` para la interfaz de usuario.
*   **`Splash.jack`**: Muestra la pantalla de bienvenida gráfica al inicio del juego.
*   **`Random.jack`**: Proporciona funciones para generar números pseudoaleatorios, utilizados principalmente para el movimiento de los fantasmas y la inicialización de la semilla.

## Controles

*   **Teclas de Flecha (Arriba, Abajo, Izquierda, Derecha):** Mueven a Jack-Man.
    *   Flecha Arriba: Código ASCII `131`
    *   Flecha Abajo: Código ASCII `133`
    *   Flecha Izquierda: Código ASCII `130`
    *   Flecha Derecha: Código ASCII `132`
*   **Tecla 'R' (o 'r'):** Reinicia el juego después de un "Game Over" o en cualquier momento durante la partida.
    *   'R': Código ASCII `82`
    *   'r': Código ASCII `114`
*   *(Opcional: Si se implementan otras teclas, como 'Q' para salir, se listarían aquí).*

## Cómo Compilar y Ejecutar

1.  **Requisitos:**
    *   Software del curso Nand2Tetris (incluyendo `JackCompiler.bat` y `VMEmulator.bat`).
    *   Todas las clases `.jack` mencionadas anteriormente.
    *   Las librerías estándar del OS de Jack (`Screen.jack`, `Keyboard.jack`, `Output.jack`, `String.jack`, `Array.jack`, `Math.jack`, `Memory.jack`, `Sys.jack`).

2.  **Compilación:**
    *   Coloca todos los archivos `.jack` del juego (Main, Game, PacMan, etc.) y los archivos `.jack` de las librerías del OS en una misma carpeta (o asegúrate de que el compilador pueda encontrar la carpeta `OS` estándar).
    *   Abre una terminal o símbolo del sistema.
    *   Navega hasta el directorio que contiene la carpeta de tu proyecto.
    *   Ejecuta el compilador de Jack sobre la carpeta del proyecto:
        ```bash
        JackCompiler NombreDeTuCarpetaDelJuego
        ```
        (Ej. `JackCompiler JackManGame`)

3.  **Ejecución:**
    *   Abre el `VMEmulator.bat`.
    *   En el emulador, ve a "File" -> "Load Program".
    *   Navega y selecciona el **directorio** `NombreDeTuCarpetaDelJuego` (el que contiene los archivos `.vm` generados).
    *   Ajusta la velocidad de animación del emulador a "Fastest" (y "No animation" si está disponible) para un mejor rendimiento.
    *   Presiona el botón de "Run" (o Play).

## Personalizaciones Realizadas

*   Se cambió la tecla de reinicio de F2 a 'R' (o 'r').
*   Se modificaron los textos en la pantalla de bienvenida (`Splash.jack`) para incluir "[Tu Nombre]".
*   Se actualizaron los mensajes de "Game Over" y la indicación de la tecla de reinicio.
*   *(Añade aquí cualquier otra personalización importante que hayas hecho, como cambios en el diseño del laberinto, comportamiento de los fantasmas, power-ups, etc.)*

## Posibles Mejoras Futuras

*   Diseño de laberintos más dinámico o cargado desde una representación de datos.
*   IA de los fantasmas más avanzada (Blinky, Pinky, Inky, Clyde con comportamientos distintos).
*   Implementación de "Power Pellets" y el estado de vulnerabilidad de los fantasmas.
*   Animaciones más fluidas para Pac-Man (abrir/cerrar boca) y los fantasmas.
*   Múltiples niveles con diferentes laberintos o velocidades.
*   Efectos de sonido.

---

Este proyecto fue desarrollado como parte del curso de Arquitectura de Computadores, basado en los principios y herramientas de Nand2Tetris.
