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

![Python OOPs Concepts](https://backend.jaroeducation.com/wp-content/uploads/2025/05/1740035836329.png)
