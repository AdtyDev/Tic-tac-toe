# Tic-tac-toe

Sure, here's a detailed description of each line of code in the Tic Tac Toe game:

```python
def sum(a, b, c):
    return a + b + c
```
- **Function `sum`**: Takes three numbers `a`, `b`, and `c` as input and returns their sum.

```python
def printBoard(xstate, zstate):
    # This logic is used to check whether the board is filled or not by using if else
    # If xstate[0] is taken by X else if taken by O if no position is taken then it displays the position number
    zero = 'X' if xstate[0] else ('O' if zstate[0] else 0)
    one = 'X' if xstate[1] else ('O' if zstate[1] else 1)
    two = 'X' if xstate[2] else ('O' if zstate[2] else 2)
    three = 'X' if xstate[3] else ('O' if zstate[3] else 3)
    four = 'X' if xstate[4] else ('O' if zstate[4] else 4)
    five = 'X' if xstate[5] else ('O' if zstate[5] else 5)
    six = 'X' if xstate[6] else ('O' if zstate[6] else 6)
    seven = 'X' if xstate[7] else ('O' if zstate[7] else 7)
    eight = 'X' if xstate[8] else ('O' if zstate[8] else 8)
    print(f"{zero} | {one} | {two}")
    print("--|---|--")
    print(f"{three} | {four} | {five}")
    print("--|---|--")
    print(f"{six} | {seven} | {eight}")
```
- **Function `printBoard`**: Prints the Tic Tac Toe board based on the current state (`xstate` for X and `zstate` for O). It checks each position and prints 'X', 'O', or the position number if the position is empty (`0`).

```python
def winner(xstate, zstate):
    wins = [[0, 1, 2], [3, 4, 5], [6, 7, 8], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 4, 8], [2, 4, 6]]
    for win in wins:
        if sum(xstate[win[0]], xstate[win[1]], xstate[win[2]]) == 3:
            print("X is the Winner")
            return 1
        if sum(zstate[win[0]], zstate[win[1]], zstate[win[2]]) == 3:
            print("O is the Winner")
            return 0
    return -1
```
- **Function `winner`**: Checks all possible winning combinations (`wins`) on the board (`xstate` for X and `zstate` for O). If any player (X or O) has three in a row, it prints the winner and returns `1` for X, `0` for O, or `-1` if there's no winner yet.

```python
if __name__ == "__main__":
    xstate = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    zstate = [0, 0, 0, 0, 0, 0, 0, 0, 0]
    turn = 1  # 1 for X and 2 for O
    print("Welcome to TIC TAC TOE")
    while True:
        printBoard(xstate, zstate)
        if turn == 1:
            print("X's chance")
            value = int(input("Please enter a value: "))
            xstate[value] = 1
        else:
            print("O's chance")
            value = int(input("Please enter a value: "))
            zstate[value] = 1
        champ = winner(xstate, zstate)
        if champ != -1:
            print("Match is over")
            break
        turn = 1 - turn
```
- **Main Program (`__name__ == "__main__"`)**: 
  - Initializes `xstate` and `zstate` to represent the board state (empty at the beginning).
  - `turn` variable tracks whose turn it is (starting with X).
  - Enters a loop to continue the game until there's a winner or draw.
  - Prints the board, prompts the current player to input a position (`value`), updates the board state accordingly, checks for a winner using `winner` function, and alternates the turn.

This code implements a basic Tic Tac Toe game in Python, showcasing fundamental concepts like functions, loops, conditionals, and list operations.
