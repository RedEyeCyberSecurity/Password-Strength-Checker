# Password-Strength-Checker
A tool to assess password security by evaluating their strength based on entropy, length, and common patterns.


```python
import re


# Function to calculate password strength
def check_password_strength(password):
    length = len(password)
    score = 0

    if length >= 8:
        score += 2
    if re.search(r'[A-Z]', password):
        score += 2
    if re.search(r'[0-9]', password):
        score += 2
    if re.search(r'[^A-Za-z0-9]', password):
        score += 2

    if score >= 8:
        return "Strong"
    elif score >= 5:
        return "Moderate"
    else:
        return "Weak"


# Main execution
password = input("Enter a password to check: ")
strength = check_password_strength(password)
print(f"Password Strength: {strength}")
