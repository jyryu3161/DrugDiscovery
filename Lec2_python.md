# Python Programming Review

## 1. Introduction to Python
- Features: Simple syntax, high readability, broad applicability
- Example code:
```python
print("Hello, Python!")
```

## 2. Variables and Data Types
- Concept: Space for storing data
- Data Types: Integer(int), Float(float), String(str), Boolean(bool), List(list), Dictionary(dict)

### List Examples (selection and slicing)
```python
numbers = [10, 20, 30, 40, 50]
print(numbers[0])  # 10
print(numbers[-1])  # 50
print(numbers[1:4])  # [20, 30, 40]
print(numbers[:3])  # [10, 20, 30]
print(numbers[2:])  # [30, 40, 50]
numbers[2] = 35
print(numbers)
```

### Dictionary Examples
```python
person = {'name': 'John', 'age': 30, 'city': 'New York'}
print(person['name'])
person['age'] = 31
person['job'] = 'Developer'
print(person)
del person['city']
print(person)
```

### Practice Problems (Variables)
1. Swap two variable values.
```python
a, b = 5, 10
a, b = b, a
print(a, b)
```
2. Print the square of a user-input number.
```python
num = int(input("Enter a number: "))
print(num ** 2)
```
3. Create a self-introduction using name and age.
```python
name = input("Enter your name: ")
age = input("Enter your age: ")
print(f"Hello, I am {name}, and I am {age} years old.")
```

## 3. Operators
- Arithmetic: `+, -, *, /, %, **`
- Comparison: `==, !=, <, >, <=, >=`
- Logical: `and, or, not`

Example code:
```python
print(10 + 5, 10 - 5, 10 * 5, 10 / 5, 10 % 3)
print(10 == 5, 10 != 5, 10 > 5, 10 < 5)
print((10 > 5) and (5 < 3), (10 > 5) or (5 < 3), not (10 < 5))
```

## 4. Control Flow - Conditionals
- Structure: `if, elif, else`
- Logical operator usage (`and, or`)

Example code:
```python
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("Below C")

age = 15
if age < 13:
    print("Child")
elif 13 <= age < 20:
    print("Teenager")
else:
    print("Adult")

user_id = "user123"
password = "pass123"
if user_id == "user123" and password == "pass123":
    print("Login successful")
else:
    print("Login failed")
```

## 5. Control Flow - Loops
- Types: `for`, `while`

Example code:
```python
# Prints numbers from 0 to 4 (5 is excluded)
for i in range(5):
    print(i)

# Prints numbers from 1 to 5 (6 is excluded)
for i in range(1, 6):
    print(i)

# Prints even numbers from 0 to 10
for i in range(0, 11, 2):
    print(i)

count = 0
while count < 5:
    print("Count:", count)
    count += 1
```

### Loop Practice Problems
1. Print all odd numbers from 1 to 50.
2. Print multiplication table for a given number.
3. Check if a number is prime.

## 6. Functions and Modules
- Defining and calling functions

Example code:
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Python"))
```
- Module usage example
```python
# module.py
def add(a, b):
    return a + b

# main.py
import module
print(module.add(10, 20))
```

## 7. Classes and Object-Oriented Programming

Example code:
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"I am {self.name}, {self.age} years old.")

p = Person("John", 30)
p.introduce()
```

## 8. Using External Libraries - Biopython

- Biopython installation
```bash
pip install biopython
```

- PubMed data retrieval example
```python
from Bio import Entrez

Entrez.email = "your_email@example.com"
handle = Entrez.esearch(db="pubmed", term="AI drug discovery", retmax=5)
record = Entrez.read(handle)
ids = record['IdList']

handle = Entrez.efetch(db="pubmed", id=ids, rettype="abstract", retmode="text")
abstracts = handle.read()
print(abstracts)
```

## Conclusion
- Practice solving these problems independently.
- Enhance programming skills through hands-on problem-solving.

