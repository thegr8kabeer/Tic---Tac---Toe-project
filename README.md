# Tic---Tac---Toe-project
The favourite game of ours, "Tic Tac Toe" is back. You can now create your own game of "Tic Tac Toe" by seeing my code. This project is aimed at those people who had learned the basics of Python and want to implement them. My code is listed in easy to read comments that will help you understand the syntax of Python according to PEP8

# Implementatiom

This project features the use of:

- Variables
- Functions
- Loops (If and While )
- Lists
- Print
- etc.

# Preview 
Below is a GIf that shows the working of this code

![github](https://user-images.githubusercontent.com/64730390/86235270-99133600-bbb1-11ea-8a36-80a6ab0aa19f.gif)

# Explanation

We are going to use 10 functions all having their specific roles that are explained in detail below:

# 1. def play_game():

This function will literaly let you play the game

```
def play_game():

  # Show the initial game board
  display_board()

  # Loop until the game stops (winner or tie)
  while game_still_going:

    # Handle a turn
    handle_turn(current_player)

    # Check if the game is over
    check_if_game_over()

    # Flip to the other player
    flip_player()
  
  # Since the game is over, print the winner or tie
  if winner == "X" or winner == "O":
    print(winner + " won.")
  elif winner == None:
    print("Tie.")

```

# 2. def display_board():

This function is used to display the boaard game which is the most important and interesting in this game

```
# Display the game board to the screen
def display_board():
  print("\n")
  print(board[0] + " | " + board[1] + " | " + board[2] + "     1 | 2 | 3")
  print(board[3] + " | " + board[4] + " | " + board[5] + "     4 | 5 | 6")
  print(board[6] + " | " + board[7] + " | " + board[8] + "     7 | 8 | 9")
  print("\n")
```

# 3. def handle_turn():

This function is responsible for handling the turns of the arbitary players 

```
# Handle a turn for an arbitrary player
def handle_turn(player):

  # Get position from player
  print(player + "'s turn.")
  position = input("Choose a position from 1-9: ")

  # Whatever the user inputs, make sure it is a valid input, and the spot is open
  valid = False
  while not valid:

    # Make sure the input is valid
    while position not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"]:
      position = input("Choose a position from 1-9: ")

    # Get correct index in our board list
    position = int(position) - 1

    # Then also make sure the spot is available on the board
    if board[position] == "-":
      valid = True
    else:
      print("You can't go there. Go again.")

  # Put the game piece on the board
  board[position] = player

  # Show the game board
  display_board()

```

# 4. def check_if_game_over():

This function is responsible for checking wheter the game is over ( as the name of the function suggests :laughing:)

```
# Check if the game is over
def check_if_game_over():
  check_for_winner()
  check_for_tie()
```

# 5. def check_for_winner():
This function's responsibility is to check who is the winner in the end of the game

```
# Check if the game is over
def check_if_game_over():
  check_for_winner()
  check_for_tie()
```
# 6. def check_rows():
This is responsible to check the win in the row entries of the game board that is 3 same entries in any rows of the game board

```
# Check the rows for a win
def check_rows():
  # Set global variables
  global game_still_going
  # Check if any of the rows have all the same value (and is not empty)
  row_1 = board[0] == board[1] == board[2] != "-"
  row_2 = board[3] == board[4] == board[5] != "-"
  row_3 = board[6] == board[7] == board[8] != "-"
  # If any row does have a match, flag that there is a win
  if row_1 or row_2 or row_3:
    game_still_going = False
  # Return the winner
  if row_1:
    return board[0] 
  elif row_2:
    return board[3] 
  elif row_3:
    return board[6] 
  # Or return None if there was no winner
  else:
    return None
```

# 7. def check_columns
This function checks the column entries of the game board for wins that is 3 same entries in any columns of the game board

```
# Check the columns for a win
def check_columns():
  # Set global variables
  global game_still_going
  # Check if any of the columns have all the same value (and is not empty)
  column_1 = board[0] == board[3] == board[6] != "-"
  column_2 = board[1] == board[4] == board[7] != "-"
  column_3 = board[2] == board[5] == board[8] != "-"
  # If any row does have a match, flag that there is a win
  if column_1 or column_2 or column_3:
    game_still_going = False
  # Return the winner
  if column_1:
    return board[0] 
  elif column_2:
    return board[1] 
  elif column_3:
    return board[2] 
  # Or return None if there was no winner
  else:
    return None
```

# 8.Check_diagonals()
This function is responsible to check the diagnol entries of the game board for wins that is 3 same entries in any diagnols of the game board

```
# Check the diagonals for a win
def check_diagonals():
  # Set global variables
  global game_still_going
  # Check if any of the columns have all the same value (and is not empty)
  diagonal_1 = board[0] == board[4] == board[8] != "-"
  diagonal_2 = board[2] == board[4] == board[6] != "-"
  # If any row does have a match, flag that there is a win
  if diagonal_1 or diagonal_2:
    game_still_going = False
  # Return the winner
  if diagonal_1:
    return board[0] 
  elif diagonal_2:
    return board[2]
  # Or return None if there was no winner
  else:
    return None
```

# 9. def check_for_tie()
This function's role is to check for tie in the board of the game

```
# Flip the current player from X to O, or O to X
def flip_player():
  # Global variables we need
  global current_player
  # If the current player was X, make it O
  if current_player == "X":
    current_player = "O"
  # Or if the current player was O, make it X
  elif current_player == "O":
    current_player = "X"
```

# 10. def flip_player()
This functions is to flip the player that is to go from "X" to "O" and vice versa

```
# Flip the current player from X to O, or O to X
def flip_player():
  # Global variables we need
  global current_player
  # If the current player was X, make it O
  if current_player == "X":
    current_player = "O"
  # Or if the current player was O, make it X
  elif current_player == "O":
    current_player = "X"
```


Steve Jobs once said:
>“You've baked a really lovely cake, but then you've used dog shit for frosting.”

Happy Coding!!! :smiley:

And don't forget to follow me on [Twitter](https://twitter.com/thegr8kabeer)
