**Polymorphism in Python** 

Polymorphism in Python is an object-oriented programming concept that means "many forms." It allows objects of different classes to be treated as objects of a common superclass. More practically, it means the same method name can have different behaviors depending on the object it is acting upon.

🔹 Types of Polymorphism in Python

Duck Typing (dynamic typing)
Method Overriding (in inheritance)
Operator Overloading

1. Duck Typing
If it walks like a duck and quacks like a duck, it must be a duck.

class Cat:
    def speak(self):
        print("Meow")

class Dog:
    def speak(self):
        print("Bark")

def make_animal_speak(animal):
    animal.speak()  # Doesn't care what type 'animal' is

make_animal_speak(Cat())
make_animal_speak(Dog())

2. Method Overriding
Subclass provides its own version of a method defined in the parent class.

class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):  # Polymorphic behavior
        print("Dog barks")

a = Animal()
d = Dog()

a.speak()  # Animal speaks
d.speak()  # Dog barks

3. Operator Overloading
Python allows operators like +, *, etc., to have different meanings based on the operands.

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):  # Overloads the '+' operator
        return Point(self.x + other.x, self.y + other.y)

p1 = Point(1, 2)
p2 = Point(3, 4)
p3 = p1 + p2  # Calls __add__

print(p3.x, p3.y)  # 4 6
