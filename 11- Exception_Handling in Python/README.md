**Exception Handling**

Exception handling in Python is a way to manage errors that may occur during the execution of a program. Instead of letting the program crash, you can "catch" exceptions and decide how to handle them gracefully.

**Basic Syntax** <br>

try:<br>
    # Code that might raise an exception<br>
    x = 1 / 0<br>
except ZeroDivisionError:<br>
    # Code that runs if a ZeroDivisionError occurs<br>
    print("You can't divide by zero!")<br>

**Example**



<pre> ```try:<br>
    # Code that may raise an exception<br>
except <ExceptionType1>:<br>
    # Handle ExceptionType1<br>
except <ExceptionType2>:<br>
    # Handle ExceptionType2<br>
else:<br>
    # Runs if no exception occurs<br>
finally:<br>
    # Runs no matter what (used for cleanup)   <br>  ``` </pre>

**Example** <br>

<pre> ```
try:<br>
    number = int(input("Enter a number: "))<br>
    result = 10 / number<br>
except ValueError:<br>
    print("That's not a valid number.")<br>
except ZeroDivisionError:<br>
    print("Division by zero is not allowed.")<br>
else:<br>
    print("Result is:", result)<br>
finally:<br>
    print("Execution complete.")<br>
    ``` </pre>



**Custom Exceptions** <br>

You can define your own exceptions by creating a class that inherits from Exception.<br>

class MyError(Exception):
    pass

try:
    raise MyError("Something went wrong")
except MyError as e:
    print(e)    