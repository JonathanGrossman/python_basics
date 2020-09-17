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

The sequence data types splits into two main subtypes: list and tuple. Lists and tuples are used to group data together.

A list is a collection of data that is ordered and changeable. You declare that something is a list by wrapping it in square brackets and separating the values using commas.

```python
# an example of a list
x = \["this", "is", "a", "list", "of", "strings"]  
```

A tuple is a collection of data that is ordered and unchangeable. You declare that something is a tuple by wrapping it in parenthesis and separating the values using commas.

```python
# an example of a tuple
tuple: x = ("this", "is", "a", "tuple", "of", "strings")  
```

## Mapping
dict: x = {"name" : "ITC", "success" : True}  

## Set
set: x = {"Israel", "Tech", "Challenge"}  
frozenset: x = frozenset({"Israel", "Tech", "Challenge"})  

## Binary
bytes: x = b"Hello"  
bytearray: x = bytearray(5)  
memoryview: x = memoryview(bytes(5))  


If you want to determine what type a value is, you can use type()  
For instance, before adding a number to a variable, you may want to make sure the variable is also a number  
For instance, before trying to loop through a variable, you may want to confirm it is iterable  

## Examples of data types  

```python
a = int(100)  
b = float(100.1)  
c = str("Israel Tech Challenge")  
d = list(("Israel Tech Challenge"))  
e = tuple(("Israel Tech Challenge"))  
f = (100)  
g = dict(name="ITC", success=True)  
h = set(("Israel Tech Challenge"))  
i = bool(100) # True; x = bool(0) => False  
j = bytes(100)  
```

```python
print(a, type(a))  
print(b, type(b))  
print(c, type(c))  
print(d, type(d))  
print(e, type(e))  
print(f, type(f))  
print(g, type(g))  
print(h, type(h))  
print(i, type(i))  
print(j, type(j))  
```

## Examples of variables

You must assign a variable a value before you can use the variable  
```python
j = 10  
print(j)
```


You can change the value of a variable (hence the meaning of “variable”)  
```python
j = 20    
print(j)  
```

You can set variables equal to any data type  
```python
g = "this is a letter"   
print(g)  
```

You can assign a variable to a variable  
```python
j = g    
print(j)
```


You can set multiple variables in one expression  
```python
a, b, c = 1, 2, 3    
print(a)  
print(b)  
print(c)  
```

If a variable is assigned a value, you can use it
```python
k = 12  
print(k + 1)  
print(k)  
```

If you have not assigned a value to a variable, you can't use it  
```python
k = k + 1  
print(k)  
```

None is a value  
```python
print(type(None))  
```





