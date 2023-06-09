# Tic-tac-toe-Python ❌⭕
Programa simple que simula jugar a tic-tac-toe (gato, tres en raya) con el usuario.
## Escenario
- la máquina jugará utilizando las **X**;
- el usuario jugará utilizando las **O**;
- el primer movimiento es de la máquina - siempre se coloca una **X** en el centro del tablero;
- todos los cuadros están numerados comenzando con el 1;
- el usuario ingresa su movimiento introduciendo el número de cuadro elegido - el número debe de ser válido, por ejemplo un valor entero mayor que 0 y menor que 10, y no puede ser un cuadro que ya esté ocupado;
- el programa verifica si el juego ha terminado - existen cuatro posibles veredictos: el juego continúa, el juego termina en empate, el usuario gana o la máquina gana;
- la máquina responde con su movimiento y se verifica el estado del juego;
- no se debe implementar algún tipo de inteligencia artificial - la máquina elegirá un cuadro de manera aleatoria, eso es suficiente para este proyecto de mera demostración.
## Ejemplo
Ejemplo del juego en consola.
```

+-------+-------+-------+
|       |       |       |
|   1   |   2   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   4   |   X   |   6   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   8   |   9   |
|       |       |       |
+-------+-------+-------+
Ingresa tu movimiento: 1
+-------+-------+-------+
|       |       |       |
|   O   |   2   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   4   |   X   |   6   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   8   |   9   |
|       |       |       |
+-------+-------+-------+
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   4   |   X   |   6   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   8   |   9   |
|       |       |       |
+-------+-------+-------+
Ingresa tu movimiento: 8
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   4   |   X   |   6   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   O   |   9   |
|       |       |       |
+-------+-------+-------+
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   4   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   O   |   9   |
|       |       |       |
+-------+-------+-------+
Ingresa tu movimiento: 4
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   3   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   O   |   9   |
|       |       |       |
+-------+-------+-------+
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   7   |   O   |   9   |
|       |       |       |
+-------+-------+-------+
Ingresa tu movimiento: 7
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   O   |   X   |   X   |
|       |       |       |
+-------+-------+-------+
|       |       |       |
|   O   |   O   |   9   |
|       |       |       |
+-------+-------+-------+
¡Has Ganado!

```
## Importación de módulos
```python
from random import randrange
```
Esta línea importa la función `randrange` del módulo  `random`, que es necesaria para generar movimientos aleatorios.

Más información del [módulo Random](https://docs.python.org/es/3/library/random.html).
## Tablero
```python
def display_board(board):
	print("+-------" * 3,"+", sep="")
	for row in range(3):
		print("|       " * 3,"|", sep="")
		for col in range(3):
			print("|   " + str(board[row][col]) + "   ", end="")
		print("|")
		print("|       " * 3,"|",sep="")
		print("+-------" * 3,"+",sep="")
```
Se define una función llamada `Display_board` que toma como argumento una matriz de 3x3 llamada `board`, que representa el tablero de un juego clásico de tic-tac-toe. La función muestra el tablero en la consola.

El tablero se dibuja mediante carácteres de texto y la función hace uso de ciclos `for` para recorrer las filas y columnas del tablero. Los ciclos anidados se encargan de imprimir los carácteres necesarios para dibujar cada fila y columna.
## Movimiento
```python

def enter_move(board):
	ok = False
	while not ok:
		move = input("Ingresa tu movimiento: ") 
		ok = len(move) == 1 and move >= '1' and move <= '9'
		if not ok:
			print("Movimiento erróneo, ingrésalo nuevamente")
			continue
		move = int(move) - 1
		row = move // 3
		col = move % 3
		sign = board[row][col]
		ok = sign not in ['O','X'] 
		if not ok:
			print("¡Cuadro ocupado, ingresa nuevamente!")
			continue
	board[row][col] = 'O'

```
En este bloque se define una función llamda `enter_move` que toma como argumento la matriz generada en el bloque anterior y solicita al usuario que ingrese su movimiento.

El código utiliza un bucle `while` que se ejecuta hasta que el usuario ingresa un movimiento válido. Primero, se solicita al usuario que ingrese un movimiento utilizando la función `input()`. Luego, el código verifica si el movimiento ingresado es válido, es decir, si tiene una longitud de 1 y es un número del 1 al 9 inclusive. Si el movimiento no es válido, se muestra un mensaje de error y se solicita al usuario que ingrese un movimiento nuevamente.

Si el movimiento es válido, se resta 1 al número ingresado y se calcula la fila y la columna correspondiente a ese movimiento en la matriz `board`. Luego, se verifica si la casilla correspondiente en la matriz `board` está vacía, es decir, si no contiene las letras `O` o `X`. Si la casilla no está vacía, se muestra un mensaje de error y se solicita al usuario que ingrese un movimiento nuevamente.

Si la casilla está vacía, se establece la letra `O` en la casilla correspondiente en la matriz board.
