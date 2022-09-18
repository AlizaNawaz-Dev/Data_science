# Tic-Tac-Toe:
```python
board = ["-", "-", "-",
         "-", "-", "-",
         "-", "-", "-", ]
Game_Still_Going = True
Winner = None
Current_player = "X"


def Display_board():
    print(board[0] + " | " + board[1] + " | " + board[2])
    print(board[3] + " | " + board[4] + " | " + board[5])
    print(board[6] + " | " + board[7] + " | " + board[8])


def Play_game():
    Display_board()

    while Game_Still_Going:
        handle_turn(Current_player)
        check_if_game_over()
        flip_player()

    if Winner == 'X' or Winner == '0':
        print(Winner + " won!")

    elif Winner == None:
        print("TIE")


def handle_turn(player):
    print(player + "'s turn.")
    position = input("Choose a position from 1-9: ")
    valid = False
    while not valid:

        while position not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"]:
            position = input("Choose Valid Position again Please:(")

        position = int(position) - 1

        if board[position] == '-':
            valid = True

        else:
            print("you cant go there. GO AGAIN")
    board[position] = player
    Display_board()


def check_if_game_over():
    check_for_winner()
    check_if_tie()


def check_for_winner():
    global Winner

    row_winner = check_rows()
    column_winner = check_columns()
    diagonal_winner = check_diagonals()
    if row_winner:
        Winner = row_winner

    elif column_winner:
        Winner = column_winner

    elif diagonal_winner:
        Winner = diagonal_winner

    else:
        Winner = None
    return


def check_rows():
    global Game_Still_Going

    row_1 = board[0] == board[1] == board[2] != "-"
    row_2 = board[3] == board[4] == board[5] != "-"
    row_3 = board[6] == board[7] == board[8] != "-"

    if row_1 or row_2 or row_3:
        Game_Still_Going = False
    if row_1:
        return board[0]
    elif row_2:
        return board[3]
    elif row_3:
        return board[6]
    return


def check_columns():
    global Game_Still_Going

    column_1 = board[0] == board[3] == board[6] != "-"
    column_2 = board[1] == board[4] == board[7] != "-"
    column_3 = board[2] == board[5] == board[8] != "-"

    if column_1 or column_2 or column_3:
        Game_Still_Going = False
    if column_1:
        return board[0]
    elif column_2:
        return board[1]
    elif column_3:
        return board[2]
    return


def check_diagonals():
    global Game_Still_Going
    diagonals_1 = board[0] == board[4] == board[8] != "-"
    diagonals_2 = board[6] == board[4] == board[2] != "-"

    if diagonals_1 or diagonals_2:
        Game_Still_Going = False

    if diagonals_1:
        return board[0]

    elif diagonals_2:
        return board[6]
    return


def check_if_tie():
    global Game_Still_Going

    if "-" not in board:
        Game_Still_Going = False
    return


def flip_player():
    global Current_player

    if Current_player == 'X':
        Current_player = 'O'

    elif Current_player == 'O':
        Current_player = 'X'
    return


Play_game()
```
