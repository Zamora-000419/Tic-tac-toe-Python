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
