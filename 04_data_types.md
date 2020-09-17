# Data Types

Like many other programming languages, Python categorizes the information in your code by its data type. The Python data types include numbers, string, Boolean, sequence, mapping, set, binary, and None. For instance, an example of a number is `10`. An example of a string is `"Programming with Python."`

The data type determines what kind of operations you can do with that data. For instance, a string is iterable but numbers are not. Because a string is iterable, you can loop through it to access each character in the string (e.g., each letter in a phrase). You can't do that with numbers.

When writing Python code, you oftentimes will use variables to represent the information in your code. Unlike some other programming languages, when defining a variable in Python, you don't have to explicitly declare what data type the variable represents. Rather, the Python intepreter will check the type of each variable in your code when the interpreter runs.

Let's look at each data type in more detail. By the way, this section is just an introduction to each data type. Later chapters go into more detail for each data type.

## Numeric

Python's numeric data type is split into three subtypes: integer, float, and complex. Integers and floats are the most common. It's likely you may never even use the complex number, which is used for advanced math calculations.  

You write numbers by just typing the number -- no quotes or apostrophes or other symbols required.  

Integers are whole numbers, meaning no decimal places. Integers can be positive or negative.  
```python
# example of a positive integer
v = 100  

# example of a negative integer
w = -101  
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

# example of a string representation of a number
z = '12'  
```

## Boolean

Booleans can have one of two values, `True` or `False`. Notice that both Boolean values start with a capital letter or else Python won't recognize it as a Boolean. Developers use Booleans to control the flow of their application and to compare values. Most values are inherently `True`. For instance, if `True` then do something. If `False`, do something else.

Not only can you set variables equal to `True` or `False`, you can evaluate whether a value is `True` or `False`. Most values are `True`. For instance, numbers other than `0`, strings that have text in them, and other data types that have non-empty values. Some values, however, are inherently `False`. For instance, empty values (i.e., other data types that have no value, like `""`, `()`, and `{}`), the number `0`, and `None` are inherently `False`.

```python
# example of a variable set equal to a Boolean
x = False

# example of a values that evaluates to True
7
"Python is fun"
["Python," "programming", "basics"]
("Python," "programming", "basics")
{
    "first": "Python," 
    "second": programming", 
    "third": basics"
}

# example of a values that evaluates to False
0
""
[]
()
{}

# example of an expression that evaluates to True
7 > 3

# example of an expression that evaluates to False
7 < 3
```

## Sequence

The sequence data type splits into three main subtypes: list, tuple, and range. Lists and tuples are used to group data together. Range is used to return a sequence of numbers. 

A list is a collection of data that is ordered, changeable, and indexed by position. You declare that something is a list by wrapping it in square brackets and separating the values using commas.

```python
# example of a list (ignore the \)
x = \["this", "is", "a", "list", "of", "strings"]
```

A tuple is a collection of data that is ordered, unchangeable, and indexed by position. You declare that something is a tuple by wrapping it in parenthesis and separating the values using commas.

```python
# example of a tuple
y = ("this", "is", "a", "tuple", "of", "strings") 
```

Python's range is used to return a sequence of numbers. It is a method that accepts one or more arguments. If you include only one number in the range declaration, by default, it starts from zero and counts by one until the number you declare inside the the range method. You can, however, declare a starting point other than zero and a count interval other than zero.

If you include two numbers in the range declaration, the range starts at the first number and ends at the second number, counting by one. If you include three numbers in the range declaration, the range starts at the first number, ends at the second number, and counts counting by increments equal to the third number.

Use range with a loop to access each number in the range.

```python
# example of range seequence from 0 to 50 counting by 1
range(0, 50)

# example of range seequence from 5 to 25 counting by 1
range(5, 25)

# example of range seequence from 10 to 50 counting by 2
range(10, 50, 2)

# example of range with a loop
r = range(5)
for number in r:
    print(number)
    
>>> 0
>>> 1
>>> 2
>>> 3
>>> 4
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
y = frozenset({"This", "is", "a", "frozenset"})
```

## Binary

Python's binary data types are not so commonly used by the everyday beginning Python developer. They are, however, nice to know of in case you encounter them. The binary types are bytes, bytearray, and memoryview. A byte represents a Python object as an immutable sequence of small integers between 0 and 256. A bytearray is the same as a byte except that it is mutable. A memoryview is used to access the internal byte-oriented data of a Python object.

```python
# example of byte
x = b"Hello"

# example of bytearray
y = bytearray(5)  

# example of memoryview
z = memoryview(bytes(5))
```

## None

The `None` type in Python represents an empty value. Sometimes you'll want a variable to exist but you won't want it to have a value. For those situations, you can use Python's `None`. If you have experience with JavaScript, `None` is equivalent to `null`.


# Using type() to debug

You can use Python's built-in `type()` method to find out a value's data type. To prevent errors, you may want to validate incoming data before trying certain operations on it.  For instance, before adding a number to a variable, you may want to make sure the variable is also a number. Another example. Before trying to loop through a variable, you may want to confirm it is iterable.

In addition to preventing errors, using `type()` can help you find errors. When debugging or trying to understand your application's behavior, you may need to check what data type something is. Printing the type can help (`print(type(my_data))`). See below for more examples.
 
## Examples of using type()  

```python  
a = int(100)  
print(a, type(a))  
>>> 100 <class 'int'>

b = float(100.1)  
print(b, type(b))  
>>> 100.1 <class 'float'>

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

i = bool(100)
print(i, type(i))  
>>> True <class 'bool'>

j = bytes(100) 
print(j, type(j))  
>>> b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00' <class 'bytes'>
```





