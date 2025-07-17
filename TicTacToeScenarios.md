Feature: Partida en TicTacToe

Scenario: Inicio de juego
Given el jugador inicia el juego
When inicie el juego las casillas deben de estar vacias
Then el jugador puede elegir entre "X" o "O"
And se muestra el turno del actual jugador ("X" o "O")

Scenario: Realizar un movimiento
Given que el jugador marque una casilla
When la casilla sea marcada
Then mostrar la casilla marcada
And cambia el turno del otro jugador

Scenario: Determinar un Ganador
Given que un jugador realizo el ultimo movimiento
When sea 3 marcas en una fila,columna o diagonal
Then gana el juego

Scenario: Determinar un Empate
Given que un jugador realizo el ultimo movimiento
When esten todas las casillas marcadas y no exista 3 en linea vertical, horizontal o diagonal
Then se empata el juego

Scenario: Reinicio de Juego
Given que el jugador quiere reiniciar la partida
When presione el boton/enlace de reinicio
Then las casillas se limpian
And puede elegir si iniciar con "X" o "O"

Scenario: Interfaz Intuitiva
Given que el juegue se inicia
When los jugadores quieran ver el proceso del juego y las casillas
Then deben de estar bastante claras los limites
And mostrar la informacion

Scenario: Juego Multijugador 
Given que se inicie una partida en multijugador
When se alternan turnos para jugar
Then mostrar el proceso del juego 
And las casillas marcadas

Scenario: Juego vs IA
Given que el jugador seleccione vs la IA
When seleccione (Facil, Medio o Dificil)
Then la IA debe de haver movimientos validos 
And desafiar al jugador 