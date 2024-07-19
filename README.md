print("Welcome to Rock Paper Scissors Game")
import random

def main():
    user_wins = 0
    computer_wins = 0
    choices = ["rock", "paper", "scissors"]

    while True:
        user_choice = input("Choose rock/paper/scissors: ").lower()
        while user_choice not in choices:
            print("Invalid choice. Please try again.")
            user_choice = input("Choose rock/paper/scissors: ").lower()

        computer_choice = random.choice(choices)

        if user_choice == computer_choice:
            winner = 'tie'
        elif (user_choice == 'rock' and computer_choice == 'scissors') or \
             (user_choice == 'scissors' and computer_choice == 'paper') or \
             (user_choice == 'paper' and computer_choice == 'rock'):
            winner = 'user'
        else:
            winner = 'computer'

        print(f"\nYou chose: {user_choice}")
        print(f"Opponent chose: {computer_choice}")
        if winner == 'tie':
            print("It's a tie!")
        elif winner == 'user':
            print("You win!")
            user_wins += 1
        else:
            print("You lose!")
            computer_wins += 1

        print(f"\nScores: \nYou: {user_wins} \t Opponent: {computer_wins}")

        play_again_input = input("\nDo you want to play again? (yes/no): ").lower()
        if play_again_input != "yes":
            print("\nThanks for playing!")
            break

main()
