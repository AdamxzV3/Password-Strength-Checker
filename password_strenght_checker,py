import re

def check_password_strength(password):
    length_error = len(password) < 8
    uppercase_error = not re.search(r"[A-Z]", password)
    lowercase_error = not re.search(r"[a-z]", password)
    digit_error = not re.search(r"\d", password)
    special_char_error = not re.search(r"[!@#$%^&*(),.?\":{}|<>]", password)

    errors = []
    if length_error:
        errors.append("Password should be at least 8 characters long.")
    if uppercase_error:
        errors.append("Password should contain at least one uppercase letter.")
    if lowercase_error:
        errors.append("Password should contain at least one lowercase letter.")
    if digit_error:
        errors.append("Password should contain at least one digit.")
    if special_char_error:
        errors.append("Password should contain at least one special character.")

    strength = 10 - len(errors)
    rating = (strength / 10) * 10

    progress_bar = "#" * strength + "-" * (10 - strength)

    print("Password Strength: [{}]".format(progress_bar))
    print("Rating: {:.1f}/10".format(rating))

    if errors:
        print("\nPassword is not strong enough. Errors:")
        for error in errors:
            print("- " + error)
    else:
        print("\nPassword is strong!")

password = input("Enter your password: ")
check_password_strength(password)
