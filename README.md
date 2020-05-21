# hellow_world
just another repository

class guessnumber:
    def __init__(self, number, mn=0, mx=100):
        self.number = number
        self.guesses = 0
        self.min = mn
        self.max = mx

    def get_guess(self):
        guess = input(f"please guess a number({self.min} - {self.max})")

        if self.valid_number(guess):
            return int(guess)
        else:
            print("please enter a valid number.")
            return self.get_guess()

    def valid_number(self, str_number):
        try:
            number = int(str_number)

        except:
            return False

        return self.min <= number <= self.max

    def play(self):

        while True:
            self.guesses += 1

            guess = self.get_guess()

            if guess < self.number:
                print("you guess was under.")
            elif guess > self.number:
                print("your guess was over.")
            else: #they guessed it
                break

        print(f"you guessed it in {self.guesses} guesses.")

game = guessnumber(56, 0, 100)
game.play()
