# guessing_game
import random as ran

print("Hello and thank you for taking the time to review this game..")
enter = input("Please press enter to continue...")

check_players = True
players = []

while check_players:
    player_count = input("Are there 1 or 2 players?: ").upper()
    if player_count == "1":
        name = input("Please enter your name: ").title()
        players.append(name)
        check_players = False
    elif player_count == "2":
        name_1 = input("Player 1, please enter your name: ").title()
        name_2 = input("Player 2, please enter your name: ").title()
        players.append(name_1)
        players.append(name_2)
        check_players = False
    else:
        print("Error, please enter a valid number of players...")
        check_players = True

for player in players:
    print(f'HELLO, {player}!')

print("Time to begin our guessing game..")

play = True

while play and player_count == "1":
    if player_count == "1":
        print("You've got 5 try's to guess the secret number between 1-20...")

        secret_number = ran.randrange(1, 20) # create error if they chose a number over 20
        guess = ""
        guess_count = 0
        MAX_GUESS = 5
        out_of_guesses = False

        while secret_number != guess and not out_of_guesses:
            if guess_count < MAX_GUESS:
                guess = int(input("Enter your guess now: "))  # need to create a error check/catch for non-integer entry
                guess_count += 1
                print(secret_number)
            else:
                out_of_guesses = True
        if guess == secret_number:
            print(f"Congrats {players[0]}, you won!")
        else:
            print(f"Sorry, {players[0]}")

        check_play_again = True
        while check_play_again:
            play_again = input("Play again? [Y/N]: ").upper()
            if play_again == "Y":
                play = True
                check_play_again = False
            elif play_again == "N":
                play = False
                check_play_again = False
            else:
                print('Error, please enter "Y" or "N"')
                check_play_again = True

else:                                                         # beginning of two player game
    while play:
        print(f"Alright {players[0].title()}. You have 5 tries to guess the secret number between 1-20..")

        secret_number = ran.randrange(1, 20)
        guess = ""
        guess_count = 0
        MAX_GUESS = 5
        out_of_guesses = False

        while secret_number != guess and not out_of_guesses:
            if guess_count < MAX_GUESS:
                guess = int(input("Enter your guess now: "))  # need to create a error check/catch for non-integer entry
                guess_count += 1
                print(secret_number)
            else:
                out_of_guesses = True
        if guess == secret_number:
            print(f"Congrats {players[0]}, you won!")
            print(f"Now it's {players[1].title()}'s turn.. ")
        else:
            print(f"Sorry, {players[0]}, you lose!")
            out_of_guesses = False
            guess_count = 0
            print(f"Now it's {players[1].title()}'s turn.. ")

        secret_number = ran.randrange(1, 20)
        guess = ""
        guess_count = 0
        MAX_GUESS = 5
        out_of_guesses = False

        while secret_number != guess and not out_of_guesses:
            if guess_count < MAX_GUESS:
                guess = int(input("Enter your guess now: "))  # need to create a error check/catch for non-integer entry
                guess_count += 1
                print(secret_number)
            else:
                out_of_guesses = True
        if guess == secret_number:
            print(f"Congrats {players[1]}, you won!")
        else:
            print(f"Sorry, {players[1]}, you lose!")
            out_of_guesses = False
            guess_count = 0

        check_play_again = True
        while check_play_again:
            play_again = input("Play again? [Y/N]").upper()
            if play_again == "Y":
                play = True
                check_play_again = False
            elif play_again == "N":
                play = False
                check_play_again = False
            else:
                error_1 = input('Error, please enter "Y" or "N"')
                check_play_again = True


