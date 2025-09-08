# Python Object-Oriented Programming (OOP) Tutorial

This tutorial introduces the fundamentals of Object-Oriented Programming (OOP) in Python, covering classes, objects, constructors, attributes, methods, static methods, and two key OOP concepts: abstraction and encapsulation. It includes practical examples to demonstrate how these concepts are applied in real-world scenarios.

## What is Object-Oriented Programming?

OOP is a programming paradigm that uses **objects** and **classes** to model real-world entities, improving code organization, reusability, and modularity. Unlike **procedural programming**, which follows a sequential flow, or **functional programming**, which emphasizes functions to reduce redundancy, OOP focuses on creating objects from classes to encapsulate data and behavior.

### Key Benefits of OOP
- **Reduces Redundancy**: Reusable code through classes and objects.
- **Improves Reusability**: Objects can be reused across different parts of the program.
- **Maps to Real-World Scenarios**: Models entities like students, cars, or bank accounts as objects.

## Core Concepts of OOP

### 1. Classes and Objects
- **Class**: A blueprint for creating objects. It defines the structure (attributes) and behavior (methods) of objects.
- **Object**: An instance of a class, representing a specific entity created from the class blueprint.

**Example**: Creating a `Student` class and objects.

```python
class Student:
    # Class attribute (shared by all objects)
    college_name = "ABC College"

    # Constructor (initializer)
    def __init__(self, name, marks):
        # Instance attributes (unique to each object)
        self.name = name
        self.marks = marks
        print(f"Adding new student {self.name} in database")

# Creating objects (instances)
s1 = Student("Karan", 97)
s2 = Student("Arjun", 88)

# Accessing instance attributes
print(s1.name)  # Output: Karan
print(s2.name)  # Output: Arjun
print(s1.marks)  # Output: 97
print(s2.marks)  # Output: 88

# Accessing class attribute
print(s1.college_name)  # Output: ABC College
print(Student.college_name)  # Output: ABC College
```

**Explanation**:
- The `Student` class is defined with a class attribute `college_name` (shared by all students) and instance attributes `name` and `marks` (unique to each student).
- The `__init__` method is the constructor, automatically called when an object is created. It takes `self` (a reference to the instance) and other parameters.
- Objects `s1` and `s2` are created with different names and marks, but they share the same `college_name`.

### 2. Constructors
A **constructor** is a special method (`__init__`) that initializes an object when it is created. It always takes `self` as the first parameter, representing the instance being created.

- **Default Constructor**: Takes only `self` and is automatically provided by Python if not defined.
- **Parameterized Constructor**: Takes additional parameters to initialize instance attributes.

**Example**:
```python
class Student:
    def __init__(self, name):  # Parameterized constructor
        self.name = name
        print("Creating new student")

    def __init__(self):  # Default constructor (this will override the parameterized one)
        print("Default constructor called")

# Only one constructor is used; the last defined constructor takes precedence
s1 = Student()  # Output: Default constructor called
```

**Note**: Python does not support multiple constructors. The last defined `__init__` method is used.

### 3. Attributes
Attributes are variables that store data in a class or object. There are two types:
- **Class Attributes**: Shared by all instances of a class, defined outside the constructor.
- **Instance Attributes**: Unique to each object, defined within the constructor using `self`.

**Example**:
```python
class Student:
    college_name = "ABC College"  # Class attribute

    def __init__(self, name, marks):
        self.name = name  # Instance attribute
        self.marks = marks  # Instance attribute

s1 = Student("Karan", 97)
s2 = Student("Arjun", 88)

# Accessing attributes
print(s1.name)  # Output: Karan
print(s2.name)  # Output: Arjun
print(s1.college_name)  # Output: ABC College
print(s2.college_name)  # Output: ABC College
```

**Key Point**: If a class attribute and an instance attribute have the same name, the instance attribute takes precedence.

### 4. Methods
Methods are functions defined within a class that operate on objects. They always take `self` as the first parameter to access instance attributes.

**Example**:
```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def welcome(self):
        print(f"Welcome {self.name}")

    def get_marks(self):
        return self.marks

s1 = Student("Karan", 97)
s1.welcome()  # Output: Welcome Karan
print(s1.get_marks())  # Output: 97
```

### 5. Static Methods
**Static methods** are methods that don’t require access to instance (`self`) or class attributes. They are defined using the `@staticmethod` decorator and work at the class level.

**Example**:
```python
class Student:
    @staticmethod
    def hello():
        print("Hello")

Student.hello()  # Output: Hello
```

**Explanation**: The `hello` method doesn’t use `self` and is called on the class directly, not on an object.

### 6. Abstraction
**Abstraction** means hiding implementation details and exposing only the necessary features to the user. It simplifies the interface while keeping internal workings hidden.

**Example**:
```python
class Car:
    def __init__(self):
        self.accelerator = False
        self.brake = False
        self.clutch = False

    def start(self):
        self.clutch = True
        self.accelerator = True
        print("Car started")

car1 = Car()
car1.start()  # Output: Car started
```

**Explanation**: The `start` method hides the internal steps (e.g., pressing the clutch and accelerator) and only exposes the result: the car starts.

### 7. Encapsulation
**Encapsulation** involves bundling data (attributes) and methods into a single unit (class) to protect data and provide controlled access.

**Example**:
The `Car` class above is an example of encapsulation, as it combines attributes (`accelerator`, `brake`, `clutch`) and methods (`start`) into a single unit, with the implementation details hidden from the user.

## Practice Questions

### 1. Student Class with Average Marks
Create a `Student` class that takes a name and a list of marks for three subjects, with a method to calculate and print the average.

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def get_average(self):
        sum_marks = sum(self.marks)
        average = sum_marks / len(self.marks)
        print(f"Hi {self.name}, your average score is {average}")

s1 = Student("Tony Stark", [99, 98, 97])
s1.get_average()  # Output: Hi Tony Stark, your average score is 98.0

# Changing attributes
s1.name = "Iron Man"
s1.get_average()  # Output: Hi Iron Man, your average score is 98.0
```

### 2. Account Class for Banking
Create an `Account` class with balance and account number attributes, and methods to debit, credit, and print the balance.

```python
class Account:
    def __init__(self, balance, account_number):
        self.balance = balance
        self.account_number = account_number

    def debit(self, amount):
        self.balance -= amount
        print(f"Rs {amount} was debited")
        print(f"Total balance = {self.get_balance()}")

    def credit(self, amount):
        self.balance += amount
        print(f"Rs {amount} was credited")
        print(f"Total balance = {self.get_balance()}")

    def get_balance(self):
        return self.balance

acc1 = Account(10000, "12345")
acc1.debit(1000)    # Output: Rs 1000 was debited, Total balance = 9000
acc1.credit(500)    # Output: Rs 500 was credited, Total balance = 9500
acc1.credit(40000)  # Output: Rs 40000 was credited, Total balance = 49500
acc1.debit(10000)   # Output: Rs 10000 was debited, Total balance = 39500
```

## Why Use Classes and Objects?
- **Organization**: Classes provide a structured way to organize code, making it easier to manage complex systems.
- **Real-World Mapping**: Objects map directly to real-world entities (e.g., students, bank accounts), improving code readability.
- **Reusability**: Classes allow code reuse through objects and methods, reducing redundancy.
- **Scalability**: OOP makes it easier to scale and maintain large applications.

# Python Object-Oriented Programming (OOP) Tutorial - Part 2

This tutorial continues our exploration of Object-Oriented Programming (OOP) in Python, focusing on advanced concepts such as the `del` keyword, private attributes and methods, inheritance, super method, class methods, property decorators, and polymorphism through operator overloading. We’ll also solve practice questions to reinforce these concepts. This is a straightforward guide designed to help you understand and implement these OOP principles effectively.

## 1. The `del` Keyword
The `del` keyword is used to delete object properties or entire objects, freeing up memory space occupied by them. This is useful when you no longer need an object or its attributes.

**Example**:
```python
class Student:
    def __init__(self, name):
        self.name = name
        print(f"Student {self.name} created")

# Create an object
s1 = Student("Shraddha")

# Print name before deletion
print(s1.name)  # Output: Shraddha

# Delete the name attribute
del s1.name

# Try to access name after deletion (will raise an error)
try:
    print(s1.name)
except AttributeError:
    print("AttributeError: 'Student' object has no attribute 'name'")

# Delete the entire object
del s1

# Try to access the object after deletion (will raise an error)
try:
    print(s1)
except NameError:
    print("NameError: name 's1' is not defined")
```

**Explanation**:
- The `del` keyword removes the `name` attribute or the entire `s1` object from memory.
- Attempting to access a deleted attribute or object results in an `AttributeError` or `NameError`, respectively.

## 2. Private Attributes and Methods
Private attributes and methods are restricted to the class and cannot be accessed directly from outside. In Python, private members are indicated by prefixing their names with double underscores (`__`).

**Example**:
```python
class Account:
    def __init__(self, account_number, account_password):
        self.account_number = account_number
        self.__account_password = account_password  # Private attribute

    def reset_password(self):
        print(f"Password: {self.__account_password}")  # Accessible within the class

# Create an account
acc1 = Account("12345", "abcd")

# Access public attribute
print(acc1.account_number)  # Output: 12345

# Try to access private attribute (will raise an error)
try:
    print(acc1.__account_password)
except AttributeError:
    print("AttributeError: 'Account' object has no attribute '__account_password'")

# Access private attribute via class method
acc1.reset_password()  # Output: Password: abcd
```

**Explanation**:
- The `__account_password` attribute is private and cannot be accessed outside the class.
- The `reset_password` method, being inside the class, can access the private attribute.
- Python’s private mechanism is implemented via **name mangling**, where `__attribute` is internally renamed to `_ClassName__attribute`.

**Private Methods Example**:
```python
class Person:
    def __init__(self):
        self.__name = "Anonymous"

    def __hello(self):  # Private method
        print(f"Hello, {self.__name}")

    def welcome(self):
        self.__hello()  # Call private method internally

# Create an object
p1 = Person()

# Call public method
p1.welcome()  # Output: Hello, Anonymous

# Try to access private method (will raise an error)
try:
    p1.__hello()
except AttributeError:
    print("AttributeError: 'Person' object has no attribute '__hello'")
```

**Explanation**:
- The `__hello` method is private and can only be called within the class (e.g., by the `welcome` method).
- Private attributes and methods are useful for hiding sensitive data or implementation details, enhancing security and encapsulation.

## 3. Inheritance
Inheritance allows one class (child/derived class) to inherit properties and methods from another class (parent/base class). This promotes code reuse and models real-world relationships.

### Types of Inheritance
1. **Single Inheritance**: One child class inherits from one parent class.
2. **Multilevel Inheritance**: A chain of inheritance where a class inherits from another derived class.
3. **Multiple Inheritance**: A class inherits from multiple parent classes (not covered in this tutorial).

**Single Inheritance Example**:
```python
class Car:
    def __init__(self):
        self.type = "Generic"

    @staticmethod
    def start():
        print("Car started")

    @staticmethod
    def stop():
        print("Car stopped")

class ToyotaCar(Car):  # Inherits from Car
    def __init__(self, name):
        self.name = name

# Create an object
car1 = ToyotaCar("Prius")
print(car1.name)  # Output: Prius
car1.start()      # Output: Car started
print(car1.type)  # Output: Generic
```

**Explanation**:
- The `ToyotaCar` class inherits the `start`, `stop`, and `type` attributes from the `Car` class.
- The child class can define its own attributes (e.g., `name`) and methods.

**Multilevel Inheritance Example**:
```python
class A:
    def __init__(self):
        self.a = "Welcome to Class A"

class B(A):  # Inherits from A
    def __init__(self):
        super().__init__()  # Call parent constructor
        self.b = "Welcome to Class B"

class C(B):  # Inherits from B
    def __init__(self):
        super().__init__()  # Call parent constructor
        self.c = "Welcome to Class C"

# Create an object
c1 = C()
print(c1.a)  # Output: Welcome to Class A
print(c1.b)  # Output: Welcome to Class B
print(c1.c)  # Output: Welcome to Class C
```

**Explanation**:
- Class `C` inherits from `B`, which inherits from `A`, forming a chain.
- The `super()` method ensures parent class constructors are called to initialize inherited attributes.

## 4. The `super()` Method
The `super()` method is used to call methods or constructors from the parent class, enabling the child class to extend or modify parent behavior.

**Example**:
```python
class Car:
    def __init__(self, type):
        self.type = type
        print(f"Car type: {self.type}")

    @staticmethod
    def start():
        print("Car started")

class ToyotaCar(Car):
    def __init__(self, name, type):
        super().__init__(type)  # Call parent constructor
        self.name = name
        super().start()  # Call parent method

# Create an object
car1 = ToyotaCar("Prius", "Electric")
print(car1.name)  # Output: Prius
print(car1.type)  # Output: Electric
```

**Explanation**:
- `super().__init__(type)` calls the parent class’s constructor to initialize `type`.
- `super().start()` calls the parent class’s `start` method, ensuring the car starts upon creation.

## 5. Class Methods
Class methods operate on the class itself rather than an instance. They take `cls` as the first parameter and are defined using the `@classmethod` decorator. They can modify class attributes (shared across all instances).

**Example**:
```python
class Person:
    name = "Anonymous"  # Class attribute

    def change_name(self, new_name):  # Instance method
        self.name = new_name  # Creates instance attribute

    @classmethod
    def change_class_name(cls, new_name):  # Class method
        cls.name = new_name  # Modifies class attribute

# Create an object
p1 = Person()
p1.change_name("Rahul Kumar")
print(p1.name)        # Output: Rahul Kumar (instance attribute)
print(Person.name)    # Output: Anonymous (class attribute unchanged)

# Use class method
Person.change_class_name("John Doe")
print(Person.name)    # Output: John Doe (class attribute changed)
print(p1.name)        # Output: Rahul Kumar (instance attribute unchanged)
```

**Explanation**:
- The instance method `change_name` creates a new instance attribute, leaving the class attribute unchanged.
- The class method `change_class_name` modifies the class attribute, affecting all instances that don’t have their own `name` attribute.

## 6. Property Decorators
Property decorators (`@property`) allow methods to be accessed like attributes, enabling dynamic computation of values. They are useful when an attribute’s value depends on other attributes.

**Example**:
```python
class Student:
    def __init__(self, physics, chemistry, math):
        self.physics = physics
        self.chemistry = chemistry
        self.math = math

    @property
    def percentage(self):
        return str((self.physics + self.chemistry + self.math) / 3) + "%"

# Create an object
s1 = Student(98, 97, 100)
print(s1.percentage)  # Output: 98.33%

# Change marks
s1.physics = 86
print(s1.percentage)  # Output: 94.33%
```

**Explanation**:
- The `percentage` method is decorated with `@property`, making it accessible like an attribute (`s1.percentage` instead of `s1.percentage()`).
- When `physics` is updated, the `percentage` property automatically reflects the new value, ensuring consistency.

## 7. Polymorphism and Operator Overloading
Polymorphism allows the same operation to behave differently based on the object’s type or class. In Python, **operator overloading** is a form of polymorphism, where operators like `+` or `-` are given custom meanings for user-defined classes using special methods (dunder methods, e.g., `__add__`, `__sub__`).

**Example (Operator Overloading with Complex Numbers)**:
```python
class Complex:
    def __init__(self, real, imag):
        self.real = real
        self.imag = imag

    def show_number(self):
        print(f"{self.real} + {self.imag}i")

    def __add__(self, other):  # Overload + operator
        new_real = self.real + other.real
        new_imag = self.imag + other.imag
        return Complex(new_real, new_imag)

    def __sub__(self, other):  # Overload - operator
        new_real = self.real - other.real
        new_imag = self.imag - other.imag
        return Complex(new_real, new_imag)

# Create complex numbers
num1 = Complex(1, 3)
num2 = Complex(4, 6)
num1.show_number()  # Output: 1 + 3i
num2.show_number()  # Output: 4 + 6i

# Add complex numbers
num3 = num1 + num2
num3.show_number()  # Output: 5 + 9i

# Subtract complex numbers
num4 = num1 - num2
num4.show_number()  # Output: -3 + -3i
```

**Explanation**:
- The `__add__` method defines how the `+` operator works for `Complex` objects, adding real and imaginary parts separately.
- The `__sub__` method defines the `-` operator, subtracting real and imaginary parts.
- Without these dunder methods, using `+` or `-` would raise a `TypeError` for unsupported operand types.

**More on Operator Overloading**:
- Python supports many dunder methods for operators, such as:
  - `__add__` for `+`
  - `__sub__` for `-`
  - `__mul__` for `*`
  - `__gt__` for `>`
  - `__lt__` for `<`
  - `__eq__` for `==`
- These are defined in Python’s documentation (Section 3.3.8) and allow customization of operator behavior.

## Practice Questions

### 1. Circle Class
Define a `Circle` class with a radius attribute, and methods to calculate its area and perimeter.

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return (22/7) * self.radius ** 2

    def perimeter(self):
        return 2 * (22/7) * self.radius

# Create an object
c1 = Circle(21)
print(c1.area())      # Output: 1386.0
print(c1.perimeter()) # Output: 132.0
```

**Explanation**:
- The `area` method calculates the area using the formula πr² (using 22/7 for π).
- The `perimeter` method calculates the circumference using 2πr.

### 2. Employee and Engineer Classes
Define an `Employee` class with attributes for role, department, and salary, and a method to show details. Create an `Engineer` class that inherits from `Employee` with additional attributes for name and age.

```python
class Employee:
    def __init__(self, role, department, salary):
        self.role = role
        self.department = department
        self.salary = salary

    def show_details(self):
        print(f"Role: {self.role}")
        print(f"Department: {self.department}")
        print(f"Salary: {self.salary}")

class Engineer(Employee):
    def __init__(self, name, age):
        super().__init__("Engineer", "IT", 75000)  # Call parent constructor
        self.name = name
        self.age = age

# Create an object
e1 = Engineer("Elon Musk", 40)
e1.show_details()  # Output: Role: Engineer, Department: IT, Salary: 75000
```

**Explanation**:
- The `Engineer` class inherits from `Employee` and uses `super()` to initialize parent attributes.
- The `show_details` method is inherited and displays the engineer’s details.

### 3. Order Class with Operator Overloading
Define an `Order` class with attributes for item and price, and overload the `>` operator to compare orders based on price.

```python
class Order:
    def __init__(self, item, price):
        self.item = item
        self.price = price

    def __gt__(self, other):  # Overload > operator
        return self.price > other.price

# Create objects
order1 = Order("Chips", 20)
order2 = Order("Tea", 15)

# Compare orders
print(order1 > order2)  # Output: True
```

**Explanation**:
- The `__gt__` method defines the behavior of the `>` operator, comparing orders based on their `price` attributes.
- `order1 > order2` returns `True` because 20 > 15.

## Why Use These Concepts?
- **Del Keyword**: Frees memory by removing unneeded objects or attributes.
- **Private Attributes/Methods**: Enhances security and encapsulation by restricting access.
- **Inheritance**: Promotes code reuse and organizes code hierarchically.
- **Super Method**: Allows seamless extension of parent class functionality.
- **Class Methods**: Enable manipulation of class-level data.
- **Property Decorators**: Provide dynamic, consistent attribute access.
- **Polymorphism/Operator Overloading**: Enables flexible, context-specific behavior for operators.

## Next Steps
This tutorial covers key OOP concepts in Python. To deepen your understanding:
- Explore **getter and setter decorators** (`@property`, `@<attribute>.setter`) for controlled attribute access.
- Study Python’s documentation for more dunder methods (e.g., `__mul__`, `__eq__`).
- Practice building real-world projects using OOP to structure code effectively.



