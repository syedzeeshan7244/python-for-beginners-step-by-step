**Abstraction In Python**

Abstraction in Python is one of the core principles of object-oriented programming (OOP). It allows you to hide internal details of how an object works and only expose the necessary parts through a clear interface. This makes your code more modular, reusable, and easier to understand.

**🔹 Why Use Abstraction?**

To reduce complexity by hiding the internal workings.
To protect data and internal object structure.
To expose only what’s necessary for the user of the class.


***🔹 How Abstraction Works in Python***
Python uses abstract classes and abstract methods to implement abstraction, via the abc module (abc stands for Abstract Base Classes).

**✅ Example: Abstract Class in Python**
<pre>
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass  # abstract method - must be implemented by subclasses

class Dog(Animal):
    def make_sound(self):
        return "Woof!"

class Cat(Animal):
    def make_sound(self):
        return "Meow!"

# Usage
dog = Dog()
print(dog.make_sound())  
# Output: Woof!

cat = Cat()
print(cat.make_sound())  
# Output: Meow!
</pre>

**🔹 Key Concepts:**

ABC: A base class used to define abstract classes.
@abstractmethod: Decorator used to mark a method as abstract.
You cannot instantiate an abstract class directly. 
Subclasses must implement all abstract methods.

