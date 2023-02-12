import random
def main():
    print("Welcome to Rock-Paper-Scissors!")
    player1 = input("Enter your name: ")
    player2 = "Computer"

    choices = ["rock", "paper", "scissors"]
    result = {"tie": "It's a tie!", "win": "{} wins!", "lose": "{} loses!"}

    while True:
        print("{} vs {}".format(player1, player2))
        player1_choice = input("{}, choose rock, paper, or scissors: ".format(player1)).lower()
        if player1_choice not in choices:
            print("Invalid choice, try again.")
            continue
        player2_choice = random.choice(choices)
        print("Player 1: {}  Player 2: {}".format(player1_choice, player2_choice))

        if player1_choice == player2_choice:
            print(result["tie"])
        elif (player1_choice == "rock" and player2_choice == "scissors") or \
             (player1_choice == "scissors" and player2_choice == "paper") or \
             (player1_choice == "paper" and player2_choice == "rock"):
            print(result["win"].format(player1))
        else:
            print(result["lose"].format(player1))

        play_again = input("Do you want to play again? (yes/no) ").lower()
        if play_again != "yes":
            break

if __name__ == '__main__':
    main()
