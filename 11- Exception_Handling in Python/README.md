**Exception Handling**

Exception handling in Python is a way to manage errors that may occur during the execution of a program. Instead of letting the program crash, you can "catch" exceptions and decide how to handle them gracefully.

**Basic Syntax** <br>

try:<br>
    # Code that might raise an exception<br>
    x = 1 / 0<br>
except ZeroDivisionError:<br>

    # Code that runs if a ZeroDivisionError occurs
    print("You can't divide by zero!")

**Example**

try:
    # Code that may raise an exception
except <ExceptionType1>:
    # Handle ExceptionType1
except <ExceptionType2>:
    # Handle ExceptionType2
else:
    # Runs if no exception occurs
finally:
    # Runs no matter what (used for cleanup)    

**Example**

try:
    number = int(input("Enter a number: "))
    result = 10 / number
except ValueError:
    print("That's not a valid number.")
except ZeroDivisionError:
    print("Division by zero is not allowed.")
else:
    print("Result is:", result)
finally:
    print("Execution complete.")


**Custom Exceptions**
You can define your own exceptions by creating a class that inherits from Exception.

python
Copy
Edit
class MyError(Exception):
    pass

try:
    raise MyError("Something went wrong")
except MyError as e:
    print(e)    