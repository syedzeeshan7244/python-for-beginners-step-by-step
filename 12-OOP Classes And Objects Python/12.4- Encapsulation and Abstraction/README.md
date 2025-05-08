**🔒 Encapsulation in Python**

**Definition:**

Encapsulation is the bundling of data (attributes) and methods (functions) that operate on that data into a single unit (i.e., a class). It also restricts direct access to some of the object's components, which is a way of preventing accidental modification.

In Python, we use:

Single underscore **_** to indicate a **protected member** (a convention, not enforced).

Double underscore **__** to indicate a **private member** (name mangling is used).
<pre>

class Car:
    def __init__(self, make, speed):
        self.make = make            # public attribute
        self._speed = speed         # protected attribute
        self.__engine_status = False  # private attribute

    def start_engine(self):
        self.__engine_status = True

    def get_status(self):
        return "Running" if self.__engine_status else "Stopped"

car = Car("Toyota", 100)
print(car.make)             # accessible
print(car._speed)           # accessible (but should be avoided)
# print(car.__engine_status)  # raises AttributeError

print(car.get_status())     # use method to access private data
</pre>

**🧠 Abstraction in Python**

Definition:
Abstraction is hiding complex implementation details and showing only the essential features of the object. This helps reduce complexity and increases efficiency.

In Python, abstraction is often implemented using abstract base classes (ABC) from the abc module.

<pre>
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Bark"

class Cat(Animal):
    def make_sound(self):
        return "Meow"

# animal = Animal()  # Error: can't instantiate abstract class
dog = Dog()
print(dog.make_sound())

</pre>

**Key Differences:**

| Feature        | Encapsulation                | Abstraction                              |
| -------------- | ---------------------------- | ---------------------------------------- |
| Purpose        | Protect internal state       | Hide unnecessary details                 |
| How            | Access modifiers (`_`, `__`) | Abstract classes and interfaces          |
| Real-world use | Private banking details      | Driving a car without knowing the engine |
