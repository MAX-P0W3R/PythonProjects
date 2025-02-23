import random
import sys

def get_password_length():
    # Default length
    default_length = 28
    
    # If no argument provided, use default
    if len(sys.argv) == 1:
        return default_length
    
    while True:
        try:
            length = int(sys.argv[1])
            if 4 <= length <= 32:
                return length
            else:
                length = int(input("Please enter a number between 4 and 32: "))
                if 4 <= length <= 32:
                    return length
        except ValueError:
            length = int(input("Invalid input. Please enter a number between 4 and 32: "))
            if 4 <= length <= 32:
                return length

lower = "abcdefghijklmnopqrstuvwxyz"
upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
numbers = "0123456789"
symbols = "[]{}()*;/,_-!@$#^`"

# Get validated password length
length = get_password_length()

# Ensure one character from each set
password = [
    random.choice(lower),
    random.choice(upper),
    random.choice(numbers),
    random.choice(symbols)
]

# Fill the rest of the password with random characters
all = lower + upper + numbers + symbols
password.extend(random.choice(all) for _ in range(length - 4))

# Shuffle the password
random.shuffle(password)

# Join the characters into a string
final_password = "".join(password)

print(f"\nYour {length}-character password is: {final_password}")