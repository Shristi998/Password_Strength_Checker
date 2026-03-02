# Password Strength Checker

def check_password_strength(password):
    """
    Checks the strength of a password based on:
    - Length
    - Uppercase letters
    - Lowercase letters
    - Numbers
    - Special characters
    Returns the score and strength description.
    """
    score = 0

    # Length check
    if len(password) >= 8:
        score += 1
        print("Good length")
    else:
        print("Too short")

    # Uppercase check
    if any(char.isupper() for char in password):
        score += 1
        print("Has uppercase")
    else:
        print("No uppercase")

    # Lowercase check
    if any(char.islower() for char in password):
        score += 1
        print("Has lowercase")
    else:
        print("No lowercase")

    # Number check
    if any(char.isdigit() for char in password):
        score += 1
        print("Has number")
    else:
        print("No number")

    # Special character check
    special_chars = "!@#$%^&*()-_=+[]{}|;:',.<>?/`~"
    if any(char in special_chars for char in password):
        score += 1
        print("Has special character")
    else:
        print("No special character")

    # Determine password strength
    if score <= 2:
        strength = "Weak"
    elif score <= 4:
        strength = "Medium"
    else:
        strength = "Strong"

    print("Final Score:", score)
    print("Password Strength:", strength)

    return score, strength


if __name__ == "__main__":
    password = input("Enter your password: ")
    check_password_strength(password)
