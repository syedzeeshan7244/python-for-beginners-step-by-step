**Inheritance in Python**<br>

Inheritance in Python is a feature of object-oriented programming that allows a class (called a child or subclass) to inherit attributes and methods from another class (called a parent or superclass). This promotes code reuse and modularity.<br>

<pre>
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):  # Inheriting from Parent
    def greet_child(self):
        print("Hello from Child")

# Usage
c = Child()
c.greet()        # Inherited from Parent
c.greet_child()  # Defined in Child </pre>

**🔹 Types of Inheritance in Python**<br>

Single Inheritance – One child class inherits from one parent.<br>
Multiple Inheritance – One child class inherits from multiple parents.<br>
Multilevel Inheritance – A class inherits from a child class which itself inherits from another class.<br>
Hierarchical Inheritance – Multiple child classes inherit from one parent class.<br>
Hybrid Inheritance – A combination of two or more types above.<br>

***🔹 Method Overriding**<br>
A subclass can override methods from the parent class:<br>

 <pre>
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):
    def greet(self):  # Overrides parent method
        print("Hello from Child")

c = Child()
c.greet()  # Outputs: Hello from Child </pre>

**🔹 Using super()**<br>
You can use super() to call methods from the parent class:<br>
 <pre>
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):
    def greet(self):
        super().greet()   # Call method from Parent
        print("Hello from Child")

c = Child()
c.greet()
 </pre>