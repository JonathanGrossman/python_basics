# Data Types

Like many other programming languages, Python categorizes data into several different data types. For instance, numbers, string, Boolean, sequence, mapping, set, and binary are Python data types. Essentially, data types are categories for data. 

Each piece of data falls into one of the Python categroeis, and the category that the data is in determines what kind of operations you can do with that data. For instance, text is iterable but numbers are not. Because text is iterable, you can loop through it to access each letter in the text. You can't do that with numbers.

When writing Python code, you don't have to explicitly declare what type a variable represents. Rather, the Python intepreter will check the type of a variable when the interpreter runs.

Let's look at some examples.

## Numeric

Python's numeric data type is split into three subtypes: integer, float, and complex. Integers and floats are the most common. It's likely you may never even use the complex number, which is used for advanced math calculations.  

We write numbers by just typing the number -- no quotes or apostrophes or other symbols required.  

Integers are whole numbers, meaning no decimal places. Integers can be positive or negative.  
```python
# example of a positive integer
w = 100  
```

Floats are numbers with decimals or scientific numbers containing an `e`. Floats can be positive or negative.

```python
# example of a decimal float
x = 100.1  

# example of a scientific float
y = 37e8
```

Complex numbers have a real part and an imaginary part. The real part is an actual number. The imaginary part is represented by the letter `j`. Remember, you probably won't use complex numbers unless you're doing certain kinds of advanced math in Python. They're included here for the sake of completeness and also so that if you see them in the wild, you know what they are.

```python
# example of a complex number
z = 10j  
 ```
 
## String

A string is text. Examples of strings include a letter, word, phrase, and sentence. To declare data as a string, you need to put it in quotation marks. Single or double quotations marks work.

```python
# example of a string using double quotes
x = "Double quotation marks work."

# example of a string using single quotes
y = 'Single quotation marks also work.'  
```

## Boolean

Booleans can have one of two values, True or False. Developers use Booleans to control the flow of their application and to compare values. Most values are inherently `True`. Some values, however, are inherently `False`. For instance, empty values (i.e., other data types that have no value, like "", {}, ()), the number `0`, and `None` are inherently `False`.

```python
# example of a variable set equal to a Boolean
x = False

# example of an expression that returns True
7 > 3
```

## Sequence

The sequence data types splits into three main subtypes: list, tuple, and range. Lists and tuples are used to group data together. Range is used to return a sequence of numbers.

A list is a collection of data that is ordered, changeable, and indexed by position. You declare that something is a list by wrapping it in square brackets and separating the values using commas.

```python
# example of a list
x = \["this", "is", "a", "list", "of", "strings"]
```

A tuple is a collection of data that is ordered, unchangeable, and indexed by position. You declare that something is a tuple by wrapping it in parenthesis and separating the values using commas.

```python
# example of a tuple
y = ("this", "is", "a", "tuple", "of", "strings") 
```

Python's range is used to return a sequence of numbers. It is a method that accepts one or more arguments. If you include only one number in the range declaration, by default, it starts from zero and counts by one until the number you declare inside the the range method. You can, however, declare a starting point other than zero and a count interval other than zero.

If you include two numbers in the range declaration, the range starts at the first number and ends at the second number, counting by one. If you include three numbers in the range declaration, the range starts at the first number, ends at the second number, and counts counting by increments equal to the third number.

```python
# example of range seequence from 0 to 50 counting by 1
range(0, 50)

# example of range seequence from 5 to 25 counting by 1
range(5, 25)

# example of range seequence from 10 to 50 counting by 2
range(10, 50, 2)
```

## Mapping

The mapping data type is known as a dictionary. Dictionaries contain key-value pairs that are unordered, changeable, and indexed by key. You declare that something is a dictionary by wrapping it in curly braces and separating the key-value pairs using commas.

```python
# example of a tuple
x = {
     "name" : "Python", 
     "success" : True
    }  
```

## Set

A set is a collection of data that is unordered and unindexed. Each item in the set must be unique, meaning that the same value cannot appear twice in a single set. You declare that something is a set by wrapping it in curly braces and separating the values using commas. Note that a set resembles a dictionary in the sense that both are wrapped with curly braces. They differ, however, in that a dictionary is filled with key-value pairs, whereas a set is filled with values.

A frozenset is the same as a set, except that a frozenset is unchangeable.

```python
# example of a set
x = {"This", "is", "a", "set"}  

# example of a frozenset
frozenset: x = frozenset({"This", "is", "a", "frozenset"})
```

## Binary

Python's binary data types are not so commonly used by the everyday Python developer. They are, however, nice to know of in case you encounter them. The binary types are bytes, bytearray, and memoryview. A byte represents a Python object as an immutable sequence of small integers between 0 and 256. A bytearray is the same as a byte except that it is mutable. A memoryview is used to access the internal byte-oriented data of a Python object.

```python
# example of byte
bytes: x = b"Hello"

# example of bytearray
bytearray: x = bytearray(5)  

# example of memoryview
memoryview: x = memoryview(bytes(5))  
```

# Using type() to debug

Sometimes it is helpful to know what type a value is when debugging or trying to understand your application's behavior. For instance, before adding a number to a variable, you may want to make sure the variable is also a number. For instance, before trying to loop through a variable, you may want to confirm it is iterable. You can use Python's built-in `type()` method to find out a value's data type. 
 
## Examples of using type()  

```python  
a = int(100)  
print(a, type(a))  
>>> 100 <class 'int'>

b = float(100.1)  
print(b, type(b))  
>>> 100.1 <class 'float'

c = str("Python") 
print(c, type(c))  
>>> Python <class 'str'>

d = list(("Python")) 
print(d, type(d))  
>>> 'P', 'y', 't', 'h', 'o', 'n'] <class 'list'>

e = tuple(("Python"))
print(e, type(e))  
>>> ('P', 'y', 't', 'h', 'o', 'n') <class 'tuple'>

f = range(100) 
print(f, type(f))  
>>> range(0, 100) <class 'range'>

g = dict(name="Python", success=True) 
print(g, type(g))  
>>> {'name': 'Python', 'success': True} <class 'dict'>

h = set(("Python"))  
print(h, type(h))  
>>> {'y', 't', 'o', 'P', 'h', 'n'} <class 'set'>

i = bool(100) # True; x = bool(0) => False  
print(i, type(i))  
>>> True <class 'bool'>

j = bytes(100) 
print(j, type(j))  
>>> b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00' <class 'bytes'>
```





