# What is a Runtime Error in Python?

Runtime errors in Python are errors that occur while a program is running, even though the code has successfully passed the syntax check. These errors happen when Python encounters a problem it cannot handle during execution. Common runtime errors include division by zero, accessing an index that does not exist in a list, opening a file that cannot be found, or using a variable before it has been assigned a value. For example, attempting to execute `10 / 0` raises a `ZeroDivisionError`. Runtime errors cause the program to stop unless they are properly handled. Python provides exception handling through `try`, `except`, `else`, and `finally` blocks, allowing programmers to manage errors gracefully and prevent unexpected crashes. Understanding runtime errors is important because they help developers identify logical issues and improve program reliability. By reading error messages carefully and testing code thoroughly, programmers can diagnose problems quickly and create more robust and user-friendly Python applications.

---

## What is a Runtime Error?

A runtime error occurs while your program is running. The syntax is correct, but something goes wrong during execution and Python crashes with an exception.

You nailed the three types:

**1. Syntax Error** — caught before running

```python
if x == 5    # SyntaxError: missing colon
```

**2. Runtime Error** — crashes during execution

```python
x = 10 / 0  # ZeroDivisionError (valid syntax, but fails at runtime)
```

**3. Logical Error** — runs without crashing, but gives wrong output

```python
# Finding average — wrong logic
avg = 10 + 20 / 2  # gives 20, not 15 (should be (10+20)/2)
```

### Runtime Errors vs. Other Errors

### Types of Runtime Errors

**ZeroDivisionError** — dividing by zero

```python
print(10 / 0)
```

**TypeError** — wrong type in an operation

```python
print("age: " + 25)  # can't add str and int
```

**NameError** — variable not defined

```python
print(salary)  # never defined
```

**IndexError** — list index out of range

```python
nums = [1, 2, 3]
print(nums[5])
```

**KeyError** — dictionary key doesn't exist

```python
d = {"name": "Alice"}
print(d["age"])
```

**ValueError** — right type, wrong value

```python
int("hello")
```

**AttributeError** — method doesn't exist on that object

```python
x = 5
x.append(10)
```

**FileNotFoundError** — file doesn't exist

```python
open("missing.txt")
```

**RecursionError** — function calls itself too many times

```python
def f(): return f()
f()
```

---

# Syntax Error in Python

A Syntax Error in Python occurs when the code violates the grammatical rules of the Python language. These errors are detected by the Python interpreter before the program starts running, which means the code cannot be executed until the mistake is corrected. Common causes of syntax errors include missing parentheses, quotation marks, colons, or incorrect indentation. For example, writing `print("Hello"` without a closing parenthesis will result in a syntax error. Similarly, an `if` statement without a colon at the end will also trigger this error.

## What is a Syntax Error?

A Syntax Error occurs when the code does not follow Python's grammatical rules (syntax). Python checks the syntax of the code before execution. If it finds a syntax mistake, it stops the program and displays an error message.

### Definition

A syntax error is an error that occurs when Python code violates the language's grammar rules, preventing the program from being compiled and executed.

### Why Does a Syntax Error Occur?

Python has a set of rules for writing code. When these rules are broken, Python cannot understand the instruction.

For example:

- Missing `:`
- Missing parentheses `()`
- Incorrect indentation
- Unclosed quotes
- Misspelled keywords

Since Python cannot interpret the code, the program never starts running.

### Characteristics of Syntax Errors

- Detected before execution starts.
- Prevents the program from running.
- Easy to identify because Python shows the line where the error occurred.
- Must be corrected before the program can execute.

## Common Types of Syntax Errors

### 1. Missing Colon (`:`)

```python
if True
    print("Hello")
```

Error:

```
SyntaxError: expected ':'
```

### 2. Missing Parenthesis

```python
print("Hello"
```

Error:

```
SyntaxError: '(' was never closed
```

### 3. Incorrect Indentation

```python
if True:
print("Hello")
```

Error:

```
IndentationError: expected an indented block
```

> `IndentationError` is a special type of syntax error.

### 4. Unclosed String

```python
name = "Python
```

Error:

```
SyntaxError: unterminated string literal
```

### 5. Misspelled Keyword

```python
whille True:
    print("Hello")
```

Error:

```
SyntaxError: invalid syntax
```

## Syntax Error vs Runtime Error

| Syntax Error | Runtime Error |
|---|---|
| Occurs before execution | Occurs during execution |
| Program does not start | Program starts and then stops |
| Caused by grammar mistakes | Caused by invalid operations |
| Example: Missing `:` | Example: Division by zero |

### Example of Syntax Error

```python
if True
    print("Hello")
```

Program never starts.

### Example of Runtime Error

```python
print(10 / 0)
```

Program starts but crashes with:

```
ZeroDivisionError
```

## Real-Life Analogy

Think of Python as a teacher checking an exam paper.

- **Syntax Error:** You wrote a sentence with broken grammar, so the teacher cannot understand it.
- **Runtime Error:** Your sentence is grammatically correct, but the information inside it is wrong.

Example:

- **Syntax Error:** "I am go school." — Grammar is wrong.
- **Runtime Error:** "There are 25 months in a year." — Grammar is correct, but the statement is invalid.

---

# Error Handling in Python

Error Handling in Python is the process of detecting and managing errors that occur during program execution so that the program does not terminate unexpectedly. Python provides a mechanism called exception handling, which allows programmers to handle runtime errors gracefully using `try`, `except`, `else`, and `finally` blocks.

The `try` block contains code that may cause an error. If an exception occurs, the `except` block is executed to handle it. The `else` block runs when no exception occurs, and the `finally` block executes regardless of whether an error occurs, making it useful for cleanup tasks such as closing files.

For example, when dividing a number by zero, Python raises a `ZeroDivisionError`. Instead of crashing, the program can catch and handle the error using an `except` block.

Effective error handling improves program reliability, prevents unexpected crashes, and provides meaningful feedback to users. It is an essential practice in Python programming, helping developers create robust, user-friendly, and maintainable applications.

## What is Error Handling?

Error Handling is the process of identifying, catching, and managing errors that occur during the execution of a program.

In Python, errors that occur while a program is running are called exceptions. Error handling provides a way to deal with these exceptions so that the program does not stop unexpectedly.

### Definition

Error handling is a programming technique used to detect and manage exceptions during program execution, allowing the program to continue running smoothly without crashing.

### Why is Error Handling Important?

Imagine a banking application where a customer enters invalid data. If the application crashes immediately, it can lead to a poor user experience and even loss of important information.

Error handling helps developers create applications that can handle unexpected situations gracefully.

## Benefits of Error Handling

### 1. Prevents Program Crashes

Without error handling, a single error can terminate the entire program. Error handling allows the program to continue executing.

### 2. Improves User Experience

Instead of displaying technical error messages, the program can show user-friendly messages.

### 3. Increases Reliability

Applications become more dependable because they can handle unexpected situations.

### 4. Simplifies Debugging

Error handling helps developers identify and understand problems more easily.

### 5. Maintains Program Flow

Even if an error occurs in one part of the program, other parts may continue to function normally.

## How Error Handling Works

Python follows a structured process for handling exceptions:

1. Python executes the code inside the `try` block.
2. If no exception occurs, execution continues normally.
3. If an exception occurs, Python immediately stops executing the remaining statements in the `try` block.
4. Python searches for a matching `except` block.
5. The matching `except` block executes.
6. The program continues execution after the exception has been handled.
7. If a `finally` block exists, it executes regardless of whether an exception occurred.

This mechanism ensures that errors can be handled in a controlled manner.

## Components of Error Handling

Python provides several keywords that work together to handle exceptions:

- `try`
- `except`
- `else`
- `finally`
- `raise`

Each keyword has a specific purpose.

### The `try` Block

The `try` block contains the code that may potentially generate an exception.

Whenever a developer believes that a particular piece of code may fail during execution, it should be placed inside a `try` block.

**Purpose of `try`:** The purpose of the `try` block is to monitor code for exceptions.

**Characteristics:**

- Contains risky code.
- Must be followed by at least one `except` or `finally` block.
- If an exception occurs, execution immediately transfers to an exception handler.

**Example:**

```python
try:
    number = int(input("Enter a number: "))
    print(number)
```

In this example, the conversion may fail if the user enters invalid data. Therefore, the code is placed inside a `try` block.

> The `try` block contains code that may generate exceptions and allows Python to monitor it for errors.

### The `except` Block

The `except` block handles exceptions generated inside the `try` block.

If an exception occurs, Python searches for a matching `except` block and executes it.

**Purpose of `except`:** The purpose of the `except` block is to catch and handle exceptions.

**Characteristics:**

- Executes only when an exception occurs.
- Prevents abrupt program termination.
- Can display custom error messages.
- Multiple `except` blocks can be used.

**Example:**

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input")
```

If the user enters text instead of a number, the exception is caught and handled.

> The `except` block catches exceptions raised in the `try` block and provides a mechanism to handle them gracefully.

### The `else` Block

The `else` block is optional. It executes only when no exception occurs in the `try` block.

**Purpose of `else`:** The purpose of the `else` block is to separate successful execution code from exception handling code.

**Characteristics:**

- Executes only when the `try` block succeeds.
- Skipped if an exception occurs.
- Improves code readability.

**Example:**

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input")
else:
    print("Input accepted")
```

If the user enters a valid number, the `else` block executes.

> The `else` block contains code that should execute only when no exceptions occur.

### The `finally` Block

The `finally` block is used for cleanup activities. It executes whether an exception occurs or not.

**Purpose of `finally`:** The purpose of the `finally` block is to ensure that important cleanup code always runs.

**Characteristics:**

- Always executes.
- Executes after `try`, `except`, and `else`.
- Commonly used for closing files, database connections, and releasing resources.

**Example:**

```python
try:
    print("Processing")
except:
    print("Error")
finally:
    print("Execution completed")
```

The `finally` block executes regardless of the outcome.

> The `finally` block contains code that must execute under all circumstances, regardless of whether an exception occurs.

### The `raise` Statement

Python allows programmers to create exceptions manually using the `raise` statement.

**Purpose of `raise`:** The purpose of `raise` is to generate exceptions intentionally when certain conditions are violated.

**Characteristics:**

- Creates custom exception conditions.
- Improves validation.
- Helps enforce business rules.

**Example:**

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative")
```

> The `raise` statement is used to explicitly generate an exception when a specified condition occurs.
