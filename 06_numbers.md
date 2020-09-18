# Numbers  

Numbers can be integers or floats. An integer is a whole number and is called `int`. A float has one or more decimal places and is called a `float`. To demonstrated the difference, consider this. Two Python objects can have the same value but be of a different type. The number `10` is and int, but the number `10.0` is a float. Integers generally take less space in the memory than floats

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

>>> print(type(x)) # <class 'int'>
>>> print(type(y)) # <class 'float'>
```

You can convert one number type to the other. This means you can turn an int into a float. Doing so adds one decimal place by default.
You also can turn a float into an int. Doing so removes all decimal places and rounds down.

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

# convert from int to float
a = float(x)
print(a)

>>> 3.0

# convert from float to int
b = int(y)
print(b)

>>> 7
```

Another way to change an int to a float is to perform an operation using the int with a float. For instance, adding an int to a float returns a float. See below for a list of other operations.

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

# adding an int to a float returns a float
print(x + y)

>>> 10.9
```

## List of Operations

- Add ( + )
```python
print(4 + 8)

>>> 12
```

- Subtract( - )
```python
print(9 - 5)

>>> 4
```

- Multiply ( * )
```python
print(9 * 5)

>>> 45
```

- Divide ( / )
```python
print(9 / 5)

>>> 1.8
```

- Modulo ( % ) 
```python
# returns remainder
print(9 % 5)

>>> 4
```

- Integer division
```python
# returns int and rounds down
print(4 // 8) 

>>> 0
```

- Raise to Power Of ( ** )
```python
print(4 ** 8)

>>> 65536
```

# Python follows the same order of operations as algebra

# you can use some shorthand, like +=, -=, and *=, to make your code more efficient

In numbers.py, see
# examples of math in Python
# you can use += or -+ or *= as shorthand

# Python has libraries that make math easier; although those are outside the scope of this course, be aware that they exist (e.g., numpy, scipy, pandas, and matplotlib)

# adding a number to other data types results in an error
# practice reading error messages!
In numbers.py, see
# adding a number to other data types results in an error
