# Tic-tac-toe-Python ❌⭕
Programa simple que simula jugar a tic-tac-toe (gato, tres en raya) con el usuario
## Importación de módulos
```python
from random import randrange
```
Esta línea importa la función *randrange* del módulo  *random*, que es necesaria para generar movimientos aleatorios.

Más información del [módulo Random](https://docs.python.org/es/3/library/random.html).
## Tablero
```python
def display_board(board):
```
Se define una función llamada display_board que toma un parámetro board y se encarga de mostrar el estado actual del tablero.
```python
print("+-------" * 3, "+", sep = ""): 
```
Esta línea imprime la primera fila de la cuadrícula, que es una cadena que consta de tres bloques de "+-------" separados por "|" y seguida por otro "+". El argumento sep="" se usa para evitar que se agregue un espacio entre las cadenas.
