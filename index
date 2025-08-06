import tkinter as tk
import random

# Generate random number between 1 and 100
secret_number = random.randint(1, 100)
attempts = 0

# Function to check the guess
def check_guess():
    global attempts
    try:
        guess = int(entry.get())
        attempts += 1

        if guess < secret_number:
            result_label.config(text="Too low! Try again.")
        elif guess > secret_number:
            result_label.config(text="Too high! Try again.")
        else:
            result_label.config(
                text=f"🎉 Correct! You guessed it in {attempts} tries."
            )
            guess_button.config(state="disabled")
    except ValueError:
        result_label.config(text="❗ Please enter a valid number.")

# Function to reset game
def reset_game():
    global secret_number, attempts
    secret_number = random.randint(1, 100)
    attempts = 0
    entry.delete(0, tk.END)
    result_label.config(text="")
    guess_button.config(state="normal")

# GUI window setup
root = tk.Tk()
root.title("Number Guessing Game")
root.geometry("350x250")
root.resizable(False, False)
root.configure(bg="#f0f0f0")

# Title
title_label = tk.Label(
    root,
    text="🎯 Guess a number between 1 and 100",
    font=("Arial", 13, "bold"),
    bg="#f0f0f0"
)
title_label.pack(pady=15)

# Entry field
entry = tk.Entry(root, font=("Arial", 12), justify="center")
entry.pack()

# Submit Guess button
guess_button = tk.Button(
    root,
    text="Submit Guess",
    font=("Arial", 11),
    command=check_guess
)
guess_button.pack(pady=10)

# Result message label
result_label = tk.Label(
    root,
    text="",
    font=("Arial", 11),
    fg="green",
    bg="#f0f0f0"
)
result_label.pack()

# Reset Game button
reset_button = tk.Button(
    root,
    text="🔁 Play Again",
    font=("Arial", 10),
    command=reset_game
)
reset_button.pack(pady=10)

# Run the GUI
root.mainloop()
