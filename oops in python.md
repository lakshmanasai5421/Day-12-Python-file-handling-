# Python OOPs Concepts

Python Object-Oriented Programming (OOP) is a programming paradigm that organizes code using **classes** and **objects**. A class is a blueprint that defines attributes and methods, while an object is an instance of a class. OOP helps developers write modular, reusable, and maintainable code.

The four main principles of OOP are **encapsulation**, **inheritance**, **polymorphism**, and **abstraction**.

- **Encapsulation** protects data by restricting direct access and allowing interaction through methods.
- **Inheritance** enables a class to acquire properties and behaviors from another class, promoting code reuse.
- **Polymorphism** allows methods with the same name to behave differently depending on the object.
- **Abstraction** hides complex implementation details and exposes only essential features.

Python supports OOP through simple and readable syntax, making it easy to model real-world entities and relationships. By using OOP concepts, programmers can build scalable applications, improve code organization, reduce redundancy, and enhance overall software development efficiency and flexibility in large projects.

---

## Main OOP Concepts in Python

- Class
- Object
- Inheritance
- Encapsulation
- Polymorphism
- Abstraction

---

## What is a Class in Python?

A class in Python is a user-defined blueprint or template used to create objects. It defines the structure, properties, and behaviors that the objects created from it will possess. A class acts as a logical representation of a real-world entity by combining data (attributes) and functions (methods) into a single unit. It provides a way to organize code efficiently and supports the principles of Object-Oriented Programming (OOP).

A class is created using the `class` keyword and can contain variables, methods, constructors, and other class members. It does not occupy memory for individual data until objects are created from it. Each object created from a class is called an **instance** and has its own set of attribute values while sharing the common structure and behavior defined by the class.

For example, if `Student` is a class, it may define attributes such as `name`, `age`, and `roll_number`, along with methods such as `study()` and `display_details()`. Each student object created from this class will have its own values for these attributes while sharing the same structure and behaviors.

### Creating a Class in Python

```python
# Creating a class
class Student:
    pass
```

---

## Object in Python – Description

An **object** is an instance of a class. It is a real entity created from a class that occupies memory and contains actual data. While a class serves as a blueprint, an object represents the implementation of that blueprint. Objects allow access to the attributes and methods defined within a class.

Each object has its own identity, state, and behavior. The state of an object is represented by its attribute values, while its behavior is defined by the methods of the class. Multiple objects can be created from the same class, and each object can store different data while sharing the same structure and functionality.

Objects are fundamental to Object-Oriented Programming (OOP) because they enable programmers to model real-world entities such as students, employees, cars, and bank accounts. In Python, objects are created by calling the class name followed by parentheses. Once created, an object can access the class's attributes and methods using the dot (`.`) operator. Objects help make programs more organized, reusable, and easier to maintain.

### Object Creation

```python
class Student:

    def display(self):
        print("Class created successfully")


# Creating object
s1 = Student()

# Calling method
s1.display()
```

**Output:**

```
Class created successfully
```

---

## Methods in Python

A method is a function that is defined inside a class and is used to describe the behavior or actions of an object. Methods allow objects to perform specific tasks and operate on the data stored within the object. They are an essential part of Object-Oriented Programming (OOP) because they define what an object can do.

Methods are created inside a class using the `def` keyword and typically use the `self` parameter to access the attributes and other methods of the current object. When a method is called through an object, it can perform operations such as displaying information, updating data, or executing calculations.

### Why `self` is Used

- To access instance variables (object data)
- To call other methods inside the class
- To differentiate between instance variables and local variables

### Key Point

Methods are functions inside a class that define what an object can do.

### Example Program for Methods

```python
class Student:

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)

    def study(self):
        print(self.name, "is studying")


# Creating object
s1 = Student("John", 20)

# Calling methods
s1.display()
s1.study()
```

---

## Types of Methods in Python

In Python, methods are functions defined inside a class. They are used to define the behavior of objects. There are three main types of methods:

### 1. Instance Methods

**Explanation:**

Instance methods are the most commonly used methods in Python. They work with object data (instance variables) and can access or modify it using the `self` parameter.

**Key Points:**

- First parameter is `self`
- Access instance variables
- Called using an object
- Can modify object state

**Example:**

```python
class Student:

    def show(self):
        print("This is an instance method")


s1 = Student()
s1.show()
```

**Explanation:**

- Uses `self`
- Works with object data
- Called using object

---

### 2. Class Methods

**Explanation:**

Class methods work with class variables instead of object data. They are used when we want to affect the class as a whole rather than individual objects.

**Key Points:**

- First parameter is `cls`
- Defined using `@classmethod`
- Can access and modify class variables
- Called using class name or object

**Example:**

```python
class Student:
    school = "ABC School"

    @classmethod
    def show_school(cls):
        print("School:", cls.school)


Student.show_school()
```

**Explanation:**

- Uses `cls`
- Works with class variables
- Called using class name

---

### 3. Static Methods

**Explanation:**

Static methods do not depend on class or object data. They behave like normal functions but are placed inside a class for logical grouping.

**Key Points:**

- No `self` or `cls`
- Defined using `@staticmethod`
- Cannot access instance or class variables
- Used for utility functions

**Example:**

```python
class Math:

    @staticmethod
    def add(a, b):
        print("Sum:", a + b)


Math.add(5, 3)
```

**Explanation:**

- No `self` or `cls`
- Works like a normal function inside class
- Used for simple logic

---

## Constructors in Python – More Description

A constructor is a special method in Python that is automatically executed when a new object of a class is created. Its main purpose is to initialize the state (values) of an object so that the object is ready to use immediately after creation.

In Python, the constructor is defined using the method name `__init__()`. The word "constructor" is used because it constructs or sets up the object by assigning values to its attributes.

### How Constructor Works

When you create an object like this:

```python
s1 = Student("John", 20)
```

Python automatically calls:

```python
Student.__init__(s1, "John", 20)
```

So the constructor runs without being called manually.

### Why Constructors are Important

- They automatically initialize object data
- They reduce repetitive code
- They ensure every object starts in a valid state
- They improve code readability and structure
- They make object creation simple and clean

### Real-Life Example

Think of a mobile phone factory:

- The factory design is the **class**
- Each phone produced is an **object**
- When a phone is created, it is automatically set with:
  - Battery level
  - Model name
  - Storage capacity

This automatic setup is similar to a constructor.

---

### Types of Constructors in Python

#### 1. Default Constructor

A constructor that does not take any parameters except `self`. It initializes objects with default values.

```python
class Student:

    def __init__(self):
        print("Default Constructor Called")


s1 = Student()
```

#### 2. Parameterized Constructor

A constructor that takes parameters to initialize object attributes with specific values.

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show(self):
        print(self.name, self.age)


s1 = Student("John", 20)
s1.show()
```

### Key Points about Constructors

- Constructor is defined using `__init__`
- It is called automatically when object is created
- It is used to initialize object data
- It always takes `self` as the first parameter
- It helps reduce manual setup of objects

---

## Inheritance in Python

Inheritance is an important concept of Object-Oriented Programming (OOP) in which one class (called the **child class**) acquires the properties and methods of another class (called the **parent class**). It helps in code reusability, meaning we can use existing code without rewriting it.

In inheritance, the child class can use the features of the parent class and can also add its own new features or modify existing ones. This makes the program easier to manage and extend.

### How it Works

- **Parent Class (Base Class):** The class whose properties are inherited.
- **Child Class (Derived Class):** The class that inherits properties from the parent class.

### Example

```python
class Animal:
    def sound(self):
        print("Animals make sound")


class Dog(Animal):
    def bark(self):
        print("Dog barks")


d1 = Dog()
d1.sound()
d1.bark()
```

**Output:**

```
Animals make sound
Dog barks
```

### Types of Inheritance

- **Single Inheritance** – One child class inherits one parent class
- **Multiple Inheritance** – One child class inherits multiple parent classes
- **Multilevel Inheritance** – A class inherits from a class, which itself is a child of another class
- **Hierarchical Inheritance** – Multiple child classes inherit from one parent class

![Python OOPs Concepts](https://backend.jaroeducation.com/wp-content/uploads/2025/05/1740035836329.png)

---

## Types of Inheritance in Python (Huge Detailed Explanation)

Inheritance is one of the most powerful concepts in Object-Oriented Programming (OOP). It allows one class to reuse, extend, and modify the features of another class. This helps in reducing code duplication and improving program structure.

In Python, inheritance is divided into five main types, based on how classes are related to each other.

---

### 1. Single Inheritance

**Explanation:**

Single inheritance is the simplest form of inheritance. In this type, a child class inherits from only one parent class.

The child class can access all the properties and methods of the parent class and can also add its own new features.

**Real-Life Example:**

A Car inherits basic features from a Vehicle.

**Example:**

```python
class Vehicle:
    def start(self):
        print("Vehicle is starting")


class Car(Vehicle):
    def stop(self):
        print("Car is stopping")


c = Car()
c.start()
c.stop()
```

**Explanation:**

- `Car` inherits from `Vehicle`
- `Car` can use `start()` from parent class
- `Car` also has its own method `stop()`

---

### 2. Multiple Inheritance

**Explanation:**

Multiple inheritance means a single child class inherits from more than one parent class.

This allows the child class to combine features from multiple classes.

**Real-Life Example:**

A child inherits:

- Father's skills (driving)
- Mother's skills (cooking)

**Example:**

```python
class Father:
    def driving(self):
        print("Father can drive")


class Mother:
    def cooking(self):
        print("Mother can cook")


class Child(Father, Mother):
    pass


c = Child()
c.driving()
c.cooking()
```

**Explanation:**

- `Child` inherits from both `Father` and `Mother`
- `Child` gets all features of both classes

---

### 3. Multilevel Inheritance

**Explanation:**

Multilevel inheritance is like a chain of inheritance where a class is derived from another derived class.

It follows a **parent → child → grandchild** structure.

**Real-Life Example:**

Grandparent → Parent → Child

**Example:**

```python
class Grandparent:
    def home(self):
        print("Grandparent's home")


class Parent(Grandparent):
    def car(self):
        print("Parent's car")


class Child(Parent):
    def bike(self):
        print("Child's bike")


c = Child()
c.home()
c.car()
c.bike()
```

**Explanation:**

- `Child` inherits `Parent`
- `Parent` inherits `Grandparent`
- `Child` gets access to all levels

---

### 4. Hierarchical Inheritance

**Explanation:**

In hierarchical inheritance, one parent class is inherited by multiple child classes.

All child classes share the same base class but can have their own features.

**Real-Life Example:**

One Animal class → Dog, Cat, Cow

**Example:**

```python
class Animal:
    def sound(self):
        print("Animals make sound")


class Dog(Animal):
    def bark(self):
        print("Dog barks")


class Cat(Animal):
    def meow(self):
        print("Cat meows")


d = Dog()
c = Cat()

d.sound()
c.sound()
```

**Explanation:**

- `Dog` and `Cat` both inherit `Animal`
- Both share `sound()` method
- Each has its own behavior

---

### 5. Hybrid Inheritance

**Explanation:**

Hybrid inheritance is a combination of two or more types of inheritance. It is the most complex form of inheritance in Python.

It may include:

- Multiple inheritance
- Multilevel inheritance
- Hierarchical inheritance

**Real-Life Example:**

A system where:

- Class A is parent
- Class B and C inherit A
- Class D inherits both B and C

**Example:**

```python
class A:
    def showA(self):
        print("Class A")


class B(A):
    def showB(self):
        print("Class B")


class C(A):
    def showC(self):
        print("Class C")


class D(B, C):
    pass


d = D()
d.showA()
d.showB()
d.showC()
```

**Explanation:**

- Class `D` inherits from both `B` and `C`
- `B` and `C` inherit from `A`
- This forms a complex structure

---

## Encapsulation in Python

Encapsulation is one of the fundamental concepts of Object-Oriented Programming (OOP). It refers to the bundling of data (attributes) and the methods that operate on that data into a single unit called a class. It also involves restricting direct access to some of the object's components, which is a way of preventing accidental modification of data.

Encapsulation acts as a protective shield that prevents the data from being accessed or modified directly from outside the class. Instead, the data is accessed and updated through methods, which provides controlled and secure interaction with the object's internal state.

### Why Encapsulation is Important

- It protects data from unauthorized access and modification
- It keeps the internal representation of an object hidden from the outside
- It improves code maintainability and flexibility
- It allows validation before changing data
- It reduces complexity by hiding implementation details

### Real-Life Example

Think of an ATM machine:

- You can check balance, withdraw, and deposit money (these are **methods**)
- But you cannot directly access the bank's internal database or modify account balance manually (the **data is hidden**)
- The ATM provides a controlled interface to interact with your account

This is encapsulation — hiding data and providing controlled access.

### Access Modifiers in Python

Python uses naming conventions to indicate the level of access for attributes and methods:

#### 1. Public Members

Public members are accessible from anywhere — inside the class, outside the class, and from child classes. By default, all attributes and methods in Python are public.

```python
class Student:

    def __init__(self, name, age):
        self.name = name      # Public attribute
        self.age = age         # Public attribute

    def display(self):         # Public method
        print("Name:", self.name)
        print("Age:", self.age)


s1 = Student("John", 20)
s1.display()
print(s1.name)    # Accessible from outside
```

**Output:**

```
Name: John
Age: 20
John
```

#### 2. Protected Members

Protected members are indicated by a single underscore `_` prefix. They are meant to be accessed only within the class and its subclasses. However, Python does not strictly enforce this — it is a convention to signal that the member should not be accessed from outside.

```python
class Employee:

    def __init__(self, name, salary):
        self._name = name        # Protected attribute
        self._salary = salary    # Protected attribute

    def _display(self):          # Protected method
        print("Name:", self._name)
        print("Salary:", self._salary)


class Manager(Employee):

    def show(self):
        self._display()    # Accessing protected method from child class


m1 = Manager("Alice", 50000)
m1.show()
```

**Output:**

```
Name: Alice
Salary: 50000
```

**Explanation:**

- `_name` and `_salary` are protected attributes
- `_display()` is a protected method
- They can be accessed within the class and by child classes
- It is a convention, not a strict rule

#### 3. Private Members

Private members are indicated by a double underscore `__` prefix. They cannot be accessed directly from outside the class. Python performs **name mangling** to make them harder to access — the attribute name is internally changed to `_ClassName__attribute`.

```python
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance    # Private attribute

    def deposit(self, amount):
        self.__balance += amount
        print("Deposited:", amount)

    def get_balance(self):          # Getter method
        return self.__balance


acc = BankAccount(1000)
acc.deposit(500)
print("Balance:", acc.get_balance())

# print(acc.__balance)    # This will raise AttributeError
```

**Output:**

```
Deposited: 500
Balance: 1500
```

**Explanation:**

- `__balance` is a private attribute
- It cannot be accessed directly using `acc.__balance`
- It is accessed through the `get_balance()` method
- This provides controlled access to sensitive data

### Getters and Setters

Getters and setters are methods used to access and update private attributes in a controlled way. They provide an interface to interact with private data while allowing validation and restrictions.

```python
class Student:

    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    # Getter methods
    def get_name(self):
        return self.__name

    def get_age(self):
        return self.__age

    # Setter methods
    def set_name(self, name):
        self.__name = name

    def set_age(self, age):
        if age > 0:
            self.__age = age
        else:
            print("Age must be positive")


s1 = Student("John", 20)
print("Name:", s1.get_name())
print("Age:", s1.get_age())

s1.set_name("Alice")
s1.set_age(22)
print("Updated Name:", s1.get_name())
print("Updated Age:", s1.get_age())

s1.set_age(-5)    # Invalid age
```

**Output:**

```
Name: John
Age: 20
Updated Name: Alice
Updated Age: 22
Age must be positive
```

**Explanation:**

- `get_name()` and `get_age()` are getter methods that return private data
- `set_name()` and `set_age()` are setter methods that update private data
- `set_age()` includes validation to ensure age is positive
- This provides controlled and safe modification of data

### Key Points about Encapsulation

- Encapsulation bundles data and methods together into a class
- It hides internal data from outside access
- Public members: accessible everywhere (no underscore)
- Protected members: accessible in class and subclasses (single underscore `_`)
- Private members: accessible only within the class (double underscore `__`)
- Getters and setters provide controlled access to private data
- It improves security, maintainability, and flexibility of code

---

## Polymorphism in Python

Polymorphism is a core concept of Object-Oriented Programming (OOP). The word **polymorphism** is derived from Greek words: **poly** means "many" and **morph** means "forms". So, polymorphism means **many forms**.

In programming, polymorphism means the ability of a method, function, or object to take on multiple forms. It allows the same method name to behave differently based on the object that is calling it or the parameters passed to it. This makes programs more flexible and extensible.

### Why Polymorphism is Important

- It allows the same interface to be used for different data types
- It makes code more flexible and reusable
- It simplifies code by reducing the need for multiple method names
- It supports clean and organized program design
- It enables method overriding and method overloading concepts

### Real-Life Example

Think of the word "open":

- **Open a door** — you push or pull it
- **Open a book** — you flip the cover
- **Open a file on computer** — you double-click it

The same action word "open" behaves differently depending on the context. This is polymorphism.

### Types of Polymorphism in Python

#### 1. Method Overriding (Runtime Polymorphism)

Method overriding occurs when a child class provides its own implementation of a method that is already defined in the parent class. When the method is called using the child class object, the child class version of the method is executed instead of the parent class version.

```python
class Animal:
    def sound(self):
        print("Animals make sound")


class Dog(Animal):
    def sound(self):
        print("Dog barks")


class Cat(Animal):
    def sound(self):
        print("Cat meows")


# Creating objects
a = Animal()
d = Dog()
c = Cat()

a.sound()
d.sound()
c.sound()
```

**Output:**

```
Animals make sound
Dog barks
Cat meows
```

**Explanation:**

- `Dog` and `Cat` both override the `sound()` method of `Animal`
- The same method name `sound()` behaves differently for each object
- The method that gets executed depends on the object calling it

#### 2. Method Overloading

Python does not support traditional method overloading like Java or C++. However, we can achieve similar behavior using default arguments or variable-length arguments.

```python
class Calculator:

    def add(self, a=0, b=0, c=0):
        return a + b + c


calc = Calculator()
print(calc.add(5))
print(calc.add(5, 10))
print(calc.add(5, 10, 15))
```

**Output:**

```
5
15
30
```

**Explanation:**

- The same method `add()` works with different numbers of arguments
- Default values allow flexible method calls
- This simulates method overloading in Python

#### 3. Polymorphism with Functions

A single function can work with objects of different classes if those classes have the same method name. This demonstrates polymorphism at the function level.

```python
class Dog:
    def sound(self):
        print("Dog barks")


class Cat:
    def sound(self):
        print("Cat meows")


class Cow:
    def sound(self):
        print("Cow moos")


def make_sound(animal):
    animal.sound()


d = Dog()
c = Cat()
w = Cow()

make_sound(d)
make_sound(c)
make_sound(w)
```

**Output:**

```
Dog barks
Cat meows
Cow moos
```

**Explanation:**

- `make_sound()` is a single function that accepts any object
- It calls `sound()` on the object passed to it
- The behavior changes based on the type of object — this is polymorphism

#### 4. Polymorphism with Inheritance

Polymorphism works naturally with inheritance. A parent class reference can point to child class objects, and the correct method is called based on the actual object type.

```python
class Shape:
    def area(self):
        print("Calculating area")


class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        print("Area of Rectangle:", self.length * self.width)


class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        print("Area of Circle:", 3.14 * self.radius * self.radius)


shapes = [Rectangle(10, 5), Circle(7)]

for shape in shapes:
    shape.area()
```

**Output:**

```
Area of Rectangle: 50
Area of Circle: 153.86
```

**Explanation:**

- `Rectangle` and `Circle` both inherit from `Shape`
- Both override the `area()` method with their own implementation
- A single loop calls `area()` on each object, and the correct version is executed
- This is polymorphism through inheritance

#### 5. Operator Overloading

Python allows operators like `+`, `-`, `*` to be overloaded so that they work with user-defined objects. This is done by defining special methods (also called magic methods or dunder methods) in the class.

```python
class Point:

    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"


p1 = Point(1, 2)
p2 = Point(3, 4)
p3 = p1 + p2

print(p3)
```

**Output:**

```
(4, 6)
```

**Explanation:**

- The `+` operator is overloaded using the `__add__()` method
- When `p1 + p2` is used, Python internally calls `p1.__add__(p2)`
- The `__str__()` method is overloaded to provide a readable string representation
- This allows custom objects to use standard operators

### Key Points about Polymorphism

- Polymorphism means "many forms"
- The same method name can behave differently based on the object
- Method overriding allows child classes to redefine parent class methods
- Method overloading can be simulated using default arguments
- Polymorphism works with functions, inheritance, and operators
- Operator overloading uses special methods like `__add__`, `__str__`, etc.
- It makes code flexible, extensible, and easier to maintain

---

## Abstraction in Python

Abstraction is one of the key concepts of Object-Oriented Programming (OOP). It refers to the process of hiding the complex implementation details and showing only the essential features or functionality to the user. The user interacts with the object through a simplified interface without needing to understand the internal workings.

Abstraction focuses on **what** an object does rather than **how** it does it. It reduces complexity and helps in designing cleaner and more manageable code.

### Why Abstraction is Important

- It hides unnecessary details from the user
- It reduces complexity and simplifies interaction
- It improves code readability and maintainability
- It provides a clear separation between interface and implementation
- It allows changes to implementation without affecting the user

### Real-Life Example

Think of a car:

- When you drive a car, you use the **steering wheel**, **accelerator**, and **brakes** (the interface)
- You do not need to know how the **engine**, **transmission**, or **fuel injection system** works internally (the hidden implementation)
- The car **abstracts** the complex mechanics and provides a simple interface to the driver

This is abstraction — exposing only the essential functionality and hiding the complexity.

### Abstract Classes in Python

In Python, abstraction is achieved using **abstract classes** and **abstract methods**. The `abc` module (Abstract Base Classes) is used to create abstract classes.

An **abstract class** is a class that cannot be instantiated (you cannot create objects from it directly). It serves as a base class that defines a common interface for its subclasses. It can contain both abstract methods (without implementation) and concrete methods (with implementation).

An **abstract method** is a method that is declared in the abstract class but does not have an implementation. The child classes that inherit the abstract class **must** provide their own implementation of the abstract methods.

### Creating an Abstract Class

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass
```

**Explanation:**

- `Shape` is an abstract class that inherits from `ABC`
- `area()` and `perimeter()` are abstract methods decorated with `@abstractmethod`
- These methods have no implementation (just `pass`)
- Any class that inherits `Shape` must implement both `area()` and `perimeter()`
- You cannot create an object of `Shape` directly

### Implementing Abstract Classes

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass


class Rectangle(Shape):

    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * (self.length + self.width)


class Circle(Shape):

    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

    def perimeter(self):
        return 2 * 3.14 * self.radius


# Creating objects
r = Rectangle(10, 5)
c = Circle(7)

print("Rectangle Area:", r.area())
print("Rectangle Perimeter:", r.perimeter())
print("Circle Area:", c.area())
print("Circle Perimeter:", c.perimeter())
```

**Output:**

```
Rectangle Area: 50
Rectangle Perimeter: 30
Circle Area: 153.86
Circle Perimeter: 43.96
```

**Explanation:**

- `Shape` is the abstract class with abstract methods `area()` and `perimeter()`
- `Rectangle` and `Circle` are concrete classes that inherit `Shape`
- Both classes provide their own implementation of `area()` and `perimeter()`
- Objects can be created from `Rectangle` and `Circle`, but not from `Shape`

### What Happens If Abstract Method Is Not Implemented?

If a child class does not implement all the abstract methods from the parent abstract class, Python will raise a `TypeError` when you try to create an object of that child class.

```python
from abc import ABC, abstractmethod


class Shape(ABC):

    @abstractmethod
    def area(self):
        pass


class Square(Shape):
    pass    # Does not implement area()


# s = Square()    # This will raise TypeError
```

**Error:**

```
TypeError: Can't instantiate abstract class Square with abstract method area
```

**Explanation:**

- `Square` inherits `Shape` but does not implement `area()`
- Python raises a `TypeError` because abstract methods must be implemented
- This enforces the rule that all child classes must follow the interface defined by the abstract class

### Abstract Class with Concrete Methods

An abstract class can also have concrete methods (methods with implementation). These methods are shared by all child classes and do not need to be overridden.

```python
from abc import ABC, abstractmethod


class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass

    def fuel_type(self):
        print("This vehicle uses fuel")


class Car(Vehicle):

    def start(self):
        print("Car is starting with key")


class Bike(Vehicle):

    def start(self):
        print("Bike is starting with kick")


c = Car()
b = Bike()

c.start()
c.fuel_type()

b.start()
b.fuel_type()
```

**Output:**

```
Car is starting with key
This vehicle uses fuel
Bike is starting with kick
This vehicle uses fuel
```

**Explanation:**

- `Vehicle` is an abstract class with one abstract method `start()` and one concrete method `fuel_type()`
- `Car` and `Bike` implement the `start()` method
- Both classes inherit the `fuel_type()` method without overriding it
- This shows that abstract classes can provide both mandatory interface (abstract methods) and shared functionality (concrete methods)

### Key Points about Abstraction

- Abstraction hides complex implementation and shows only essential features
- It is achieved using abstract classes and abstract methods in Python
- The `abc` module provides the `ABC` class and `@abstractmethod` decorator
- Abstract classes cannot be instantiated directly
- Abstract methods must be implemented by all child classes
- Abstract classes can contain both abstract and concrete methods
- It provides a clear contract that child classes must follow
- It reduces complexity and improves code organization

---

## `if __name__ == "__main__"` in Python

In Python, `if __name__ == "__main__"` is a special conditional statement that is used to determine whether a Python file is being run directly or being imported as a module into another file. It is one of the most commonly used constructs in Python programming.

### What is `__name__`?

`__name__` is a special built-in variable in Python. Every Python file (module) has this variable automatically set by the Python interpreter.

- When a Python file is **run directly**, the value of `__name__` is set to `"__main__"`
- When a Python file is **imported as a module** into another file, the value of `__name__` is set to the **name of the file (module name)**

### How it Works

When you run a Python script directly:

```python
python myfile.py
```

Python internally sets:

```python
__name__ = "__main__"
```

When you import the file into another script:

```python
import myfile
```

Python internally sets:

```python
__name__ = "myfile"
```

### Basic Example

**File: greet.py**

```python
def hello():
    print("Hello from greet module")


print("__name__ value:", __name__)

if __name__ == "__main__":
    hello()
```

**When run directly:** `python greet.py`

**Output:**

```
__name__ value: __main__
Hello from greet module
```

**When imported from another file:**

**File: main.py**

```python
import greet
```

**Output:**

```
__name__ value: greet
```

**Explanation:**

- When `greet.py` is run directly, `__name__` is `"__main__"`, so the `if` block executes and `hello()` is called
- When `greet.py` is imported into `main.py`, `__name__` is `"greet"` (the module name), so the `if` block does **not** execute
- The `hello()` function is not called during import — only the `print` statement outside the `if` block runs

### Why is it Important?

Without `if __name__ == "__main__"`, any code written at the top level of a module would execute every time the module is imported. This can cause unwanted behavior.

**Example Without the Check:**

**File: calculator.py**

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


# Testing code
print("Testing add:", add(5, 3))
print("Testing subtract:", subtract(10, 4))
```

**File: app.py**

```python
import calculator

result = calculator.add(20, 30)
print("Result:", result)
```

**Output of app.py:**

```
Testing add: 8
Testing subtract: 6
Result: 50
```

**Problem:** The testing code in `calculator.py` runs when it is imported, which is not desired.

**Example With the Check:**

**File: calculator.py**

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


if __name__ == "__main__":
    # Testing code — only runs when file is executed directly
    print("Testing add:", add(5, 3))
    print("Testing subtract:", subtract(10, 4))
```

**File: app.py**

```python
import calculator

result = calculator.add(20, 30)
print("Result:", result)
```

**Output of app.py:**

```
Result: 50
```

**Explanation:**

- The testing code inside `if __name__ == "__main__"` does **not** run during import
- Only the `add()` function call in `app.py` runs
- This keeps the module clean and prevents unwanted side effects during import

### Real-Life Example

Think of a recipe book:

- When you **read the book yourself** (run directly), you follow the recipes and cook the food — everything executes
- When someone **borrows your recipe book** (imports the module), they only take the recipes (functions) they need — they don't cook everything in the book automatically

The `if __name__ == "__main__"` block is like saying: "Only cook these dishes if I am reading the book myself, not when someone else borrows it."

### Practical Use Cases

#### 1. Testing Functions

```python
def square(n):
    return n * n


def cube(n):
    return n * n * n


if __name__ == "__main__":
    print("Square of 4:", square(4))
    print("Cube of 3:", cube(3))
```

**Output (when run directly):**

```
Square of 4: 16
Cube of 3: 27
```

When imported, only `square()` and `cube()` functions are available — the test code does not run.

#### 2. Running a Main Program

```python
def greet(name):
    print(f"Hello, {name}!")


def farewell(name):
    print(f"Goodbye, {name}!")


def main():
    greet("John")
    farewell("John")


if __name__ == "__main__":
    main()
```

**Output (when run directly):**

```
Hello, John!
Goodbye, John!
```

**Explanation:**

- A `main()` function is defined to organize the program's entry point
- `if __name__ == "__main__"` calls `main()` only when the file is run directly
- This is a common and recommended pattern in Python programming

#### 3. Script with Command-Line Behavior

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(f"Name: {self.name}, Age: {self.age}")


if __name__ == "__main__":
    s1 = Student("Alice", 21)
    s2 = Student("Bob", 22)
    s1.display()
    s2.display()
```

**Output (when run directly):**

```
Name: Alice, Age: 21
Name: Bob, Age: 22
```

When imported, only the `Student` class is available for use — no objects are created automatically.

### Summary Table

| Scenario | `__name__` Value | `if __name__ == "__main__"` Block |
|---|---|---|
| File run directly | `"__main__"` | Executes |
| File imported as module | `"module_name"` | Does NOT execute |

### Key Points about `if __name__ == "__main__"`

- `__name__` is a special built-in variable set by the Python interpreter
- When a file is run directly, `__name__` is set to `"__main__"`
- When a file is imported, `__name__` is set to the module's file name
- `if __name__ == "__main__"` prevents code from running during import
- It is used to separate reusable code (functions, classes) from test or execution code
- It is a best practice to use this in every Python script
- It keeps modules clean and avoids unwanted side effects during import
- It is commonly used for testing, running main programs, and organizing scripts
