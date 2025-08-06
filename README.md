# python-project
# python program to create a simple calculator

# 3 steps to build calculator program
#   1. functions for operations 
#   2. user input 
#   3. print result 

# step-1: create functions:
# Function to add two numbers 
def add(num1,num2):
     return num1 + num2 

# Function to substract two numbers 
def sub(num1,num2):
     return num1 - num2 

# Function to multiply two numbers 
def multiply(num1,num2):
     return num1 * num2  

# Function to divide two numbers 
def divide(num1,num2):
     return num1 / num2 

# Function to average two numbers 
def avg(num1,num2):
     return (num1 + num2)/2  

#Step-2: user input 
print("Please select a operation:\n " \
      "1. Addition\n" \
      "2. Substraction\n" \
      "3. Multiplication\n" \
      "4. Division\n" \
      "5. Average\n") 

select = int(input("Select a operation from 1,2,3,4,5: ")) 

number1 = int(input("Enter first number: "))
number2 = int(input("Enter second number: "))

#Step-3: Print the result 

if select == 1:
     print(number1, "+", number2, "= ", \
           add(number1, number2))
     
elif select == 2:
     print(number1, "-", number2, "= ", \
           sub(number1, number2)) 
     
elif select == 3:
     print(number1, "*", number2, "= ", \
           multiply(number1, number2))
     
elif select == 4:
     print(number1, "/", number2, "= ", \
           divide(number1, number2))


     

elif select == 5:
     print("(",number1, "+", number2, ")", "/", "2", "= ", \
           avg(number1, number2)) 
    
else:
     print("Invalid operation! Pls select again!")  




     project 2 : check strengths of password using python 
# password strength checker

import re 

# password strength check conditions:
# min 8 chars, digit, uppercase, lowercase, special char

def check_password_strength(password):
    """
    Function to check the strength of a password.
    """
    if len(password) < 8:
        return "Weak: Password must be at least 8 characters long."
    
    if not any(char.isdigit() for char in password):
        return "Weak: Password must include at least one number."
    
    if not any(char.isupper() for char in password):
        return "Weak: Password must include at least one uppercase letter."
    
    if not any(char.islower() for char in password):
        return "Weak: Password must include at least one lowercase letter."
    
    if not re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        return "Medium: Add special characters to make your password stronger."
    
    return "Strong: Your password is secure!"

def password_checker():
    """
    Main function to take user input and check password strength.
    """
    print("Welcome to the Password Strength Checker!")

    while True:
        password = input("\nEnter your password (or type 'exit' to quit): ")
        
        if password.lower() == "exit":
            print("Thank you for using the Password Strength Checker! Goodbye!")
            break
        
        result = check_password_strength(password)
        print(result)


# Run the password checker
if __name__ == "__main__":
    password_checker()




     
