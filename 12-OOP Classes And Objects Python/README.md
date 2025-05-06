**Object Oriented Programming in Python**<br>

Object-Oriented Programming (OOP) in Python is a programming paradigm that structures 
code using classes and objects. It allows you to model real-world entities and their interactions more naturally and helps with code organization, reuse, and maintenance.

**Basic Concepts of OOP in Python**<br>

**1. Class**<br>

A blueprint for creating objects (like a template).<br>
<pre>
class Person:
    def __init__(self, name, age):  # Constructor
        self.name = name            # Attributes
        self.age = age

    def greet(self):                # Method
        print(f"Hello, my name is {self.name}")</pre>


**2. Object**<br>
An instance of a class.<br>
<pre>
p1 = Person("Alice", 30)
p1.greet()  # Output: Hello, my name is Alice </pre>

**3. The __init__ Method**<br>
This is the constructor; it runs automatically when an object is created.<br>

**4. Inheritance**<br>
Allows one class to inherit the attributes and methods of another.<br>
<pre>
class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id

    def show_id(self):
        print(f"My ID is {self.student_id}")</pre>

**5. Encapsulation**<br>
Keeping internal data private and using methods to access or modify it.<br>
<pre>
class Account:
    def __init__(self, balance):
        self.__balance = balance  # Private variable

    def get_balance(self):
        return self.__balance

    def deposit(self, amount):
        self.__balance += amount</pre>

**6. Polymorphism**<br>
Different classes can have methods with the same name, but different behavior.<br>
<pre>
class Dog:
    def speak(self):
        return "Woof!"

class Cat:
    def speak(self):
        return "Meow!"

def make_sound(animal):
    print(animal.speak())

make_sound(Dog())  # Woof!
make_sound(Cat())  # Meow! </pre>

***Simple Banking System (OOP in Python)***<br>
Simple Banking System example using OOP in Python. This project demonstrates key OOP principles: classes, inheritance, encapsulation, and methods.<br>

 **1. Define the base Account class**<br>
<pre>
 class Account:

    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance  # Encapsulation (private variable)

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"Deposited ${amount}. New balance: ${self.__balance}")
        else:
            print("Deposit amount must be positive.")

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.__balance}")
        else:
            print("Insufficient balance or invalid amount.")

    def get_balance(self):
        return self.__balance

    def __str__(self):
        return f"Account owner: {self.owner}\nBalance: ${self.__balance}" </pre>

**2. Create a subclass SavingsAccount**<br>
<pre>
class SavingsAccount(Account):
    def __init__(self, owner, balance=0, interest_rate=0.02):
        super().__init__(owner, balance)
        self.interest_rate = interest_rate

    def apply_interest(self):
        interest = self.get_balance() * self.interest_rate
        self.deposit(interest)
        print(f"Interest of ${interest:.2f} applied.")</pre>

**3. Using the classes**<br>

<pre>
# Create an account
john_account = SavingsAccount("John Doe", 1000)

# Check balance
print(john_account)

# Deposit money
john_account.deposit(500)

# Withdraw money
john_account.withdraw(200)

# Apply interest
john_account.apply_interest()

# Final balance
print(john_account)</pre>

**What you’ve learned in this example:**
Class creation and object instantiation
Encapsulation (__balance)
Inheritance (SavingsAccount from Account)
Method overriding and extending functionality