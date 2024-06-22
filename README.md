import random
def number_guesing_game():
    print("**NUMBER GUESSING GAME**")
    print("guess a number in choosen range.")
    while True:
        try:
            lower_bound=int(input("enter the lower bound of the range:"))
            upper_bound=int(input("enter the upper bound of the range:"))
            break
        except ValueError:
            print("invalid input. please enter integers for range")
  #Generate random number within the range
    random_number=random.randint(lower_bound,upper_bound)
    print(f"A random number between {lower_bound} and {upper_bound} has been choosen.guess the number!")
    #initialize variables
    num_guesses=0
    guessed=False
    while not guessed:
        while True:
            try:
                user_guess=int(input("make a guess:"))
                break
            except ValueError:
                print("invalid input.please enter an integer.")
        num_guesses += 1
        if user_guess == random_number:
            print(f"congratulations!!you guessed the number {random_number} in {num_guesses} guesses.")
            guessed=True
        elif user_guess<random_number:
            print("guess higher!")
        else:
            print("guess lower!")
#Main program entry point
if __name__=="__main__":
    number_guesing_game()
