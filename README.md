# PRODIGY_cyber_security3
prodigy 3rd task




def check_password_strength(password):
    """
    Checks the strength of a password based on various criteria.

    Args:
        password (str): The password to be checked.

    Returns:
        str: The strength of the password ('Weak', 'Medium', or 'Strong').
    """
    # Define the minimum requirements
    min_length = 8
    has_uppercase = False
    has_lowercase = False
    has_number = False
    has_special = False

    # Check the password against the requirements
    if len(password) >= min_length:
        for char in password:
            if char.isupper():
                has_uppercase = True
            elif char.islower():
                has_lowercase = True
            elif char.isdigit():
                has_number = True
            elif not char.isalnum():
                has_special = True

    # Determine the password strength
    if len(password) < min_length or not (has_uppercase and has_lowercase and has_number and has_special):
        return "Weak"
    elif len(password) >= min_length and (has_uppercase and has_lowercase and has_number and has_special):
        return "Strong"
    else:
        return "Medium"

# Example usage
password = input("Enter a password: ")
strength = check_password_strength(password)
print(f"The password strength is: {strength}")
