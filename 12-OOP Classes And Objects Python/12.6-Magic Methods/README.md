**Magic Methods/Dunder Methods**

In Python, magic methods (also known as dunder methods, short for double underscore) are special methods that begin and end with double underscores, like __init__, __str__, __len__, etc.

They allow you to define or customize how objects of your class behave with built-in functions and operators.

| Magic Method                    |             Purpose                                                                     |
| ------------------------------- | --------------------------------------------------------------------------- |
| `__init__(self, ...)`           | Constructor, called when a new object is created.                           |
| `__str__(self)`                 | Defines the human-readable string representation of an object (`str(obj)`). |
| `__repr__(self)`                | Defines the official string representation (`repr(obj)`).                   |
| `__len__(self)`                 | Used by `len(obj)`.                                                         |
| `__getitem__(self, key)`        | Enables indexing like `obj[key]`.                                           |
| `__setitem__(self, key, value)` | Allows item assignment `obj[key] = value`.                                  |
| `__eq__(self, other)`           | Defines behavior for the equality operator `==`.                            |
| `__add__(self, other)`          | Defines behavior for the `+` operator.                                      |
| `__call__(self, ...)`           | Makes an object callable like a function.                                   |

**Example**

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __str__(self):
        return f"Point({self.x}, {self.y})"

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

p1 = Point(1, 2)
p2 = Point(3, 4)
print(p1 + p2)  # Output: Point(4, 6)