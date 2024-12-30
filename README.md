# CODTECH-Task1
Name : Alphae P Khristi
Compamy : CODTECH IT Solutions
ID : CT08EWQ
Domain : CYBER ECURITY AND ETHICAL HACKING
Duration : 20/12/2024 to 20/1/2025
Mentor : Neela Santhosh Kumar 

Overview of CODTECH Internship Task 2 : Password Strength Checker 
This script is a Password Strength Checker written in Python. It is designed to evaluate the security of a password by checking for common vulnerabilities, such as predictability and lack of complexity. The script also provides clear feedback to users about the specific weaknesses in their password.

Key Components of the Script
1. Importing and Reading Data
The script uses a text file, common.txt, which contains a list of common passwords.

python
Copy code
with open('common.txt', 'r') as f:
    common = f.read().splitlines()
This ensures that the script can reject passwords that are too common or predictable.
The file common.txt must exist in the same directory as the script and be populated with frequently used passwords.
2. Checking for Common Passwords
python
Copy code
if password in common:
    print("strength of password is weak, very common password")
    exit()
The script immediately terminates and flags any password found in common.txt as weak.
3. Length Validation
python
Copy code
if (length < 6):
    print("Password must be at least 6 characters long!\n")
Ensures that passwords are at least 6 characters long, which is the minimum requirement for basic security.
4. Character Type Analysis
The script iterates through each character in the password to count occurrences of:

Uppercase letters
Lowercase letters
Digits
Special characters
python
Copy code
for i in range(0, length):
    if (password[i].isupper()):
        upperChars += 1
    elif (password[i].islower()):
        lowerChars += 1
    elif (password[i].isdigit()):
        digits += 1
    else:
        specialChars += 1
This analysis determines the password's complexity.

5. Evaluating Password Strength
The password is evaluated based on:

Complexity: A combination of uppercase, lowercase, numeric, and special characters.
Length: A strong password must have at least 8 characters.
python
Copy code
if (upperChars != 0 and lowerChars != 0 and digits != 0 and specialChars != 0):
    if (length >= 8):
        print("The strength of password is strong.")
    else:
        print("The strength of password is medium.")
Strong Passwords: Meet all complexity requirements and are at least 8 characters long.
Medium Passwords: Meet complexity requirements but are shorter than 8 characters.
6. Providing Feedback
If the password lacks any character type, the script provides specific guidance for improvement:

python
Copy code
if (upperChars == 0):
    print("Password must contain at least one uppercase character")
if (lowerChars == 0):
    print("Password must contain at least one lowercase character!")
if (specialChars == 0):
    print("Password must contain at least one special character!")
if (digits == 0):
    print("Password must contain at least one digit!")
This granular feedback helps users understand how to enhance their password security.

7. User Input
The script takes a password as input:

python
Copy code
password = input("Please enter password: ")
checkPassword(password)
The entered password is passed to the checkPassword function, where all checks are performed.
How the Code Works
Here’s the flow of the script:

Input Validation: The user provides a password.
Common Password Check: The password is checked against common.txt.
Length Validation: The script ensures the password is at least 6 characters long.
Complexity Validation: The script analyzes the password for uppercase, lowercase, numeric, and special characters.
Strength Assessment: The script evaluates the password's strength (weak, medium, or strong) and provides appropriate feedback.
Guidance: If the password is weak, the user receives specific suggestions to improve it.
