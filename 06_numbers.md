# Numbers  

Many Python applications use numbers. It's one of the most commonly used data types and an inevitability that you'll work with numbers in your Python applications. The level of complexity with which you work with numbers will vary. On one end of the spectrum, you may be doing simple algebra. Like addition and subtraction. On the other end of the spectrum, you may be doing statistics, calculus, or other more advanced math. For basic math, Python has built-in functionality discussed below. For more advanced math, you should consider finding a Python library suitable for your specific needs.

In Python, numbers fall into two categories. Numbers can be integers or floats. An integer is a whole number and is called `int`. A float has one or more decimal places and is called a `float`. To demonstrate the difference, consider this. Two Python objects can have the same value but be of a different type. The number `10` is and int, but the number `10.0` is a float. Integers generally take less space in the memory than floats.

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

>>> print(type(x)) # <class 'int'>
>>> print(type(y)) # <class 'float'>
```

You can convert one number type to the other. This means you can turn an int into a float. Doing so adds one decimal place by default. You also can turn a float into an int. Doing so removes all decimal places and rounds down. One way to convert from one number type to the other is to cast using the Python built-in methods `int()` and `float()`. Each method accepts one argument as seen below.

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

Another way to change an `int` to a `float` is to perform an operation using the `int` with a `float` or another `int`. For instance, adding an int to a float returns a float. See below for a list of other operations. And see the operators chapter for more details about arithmetic operators.

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

# adding an int to a float returns a float
print(x + y)

>>> 10.9
```

## Arithmetic Operations

In Python, you can work with numbers similar to how you would on a calculator. Python comes with several built-in arithematic operators. Those operators allow you to do basic algebra, like add, subtract, multiply, and divide. Here are examples of the common basic math operations in Python.

- Add ( `+` )  
- Subtract (`-` )  
- Multiply ( `*` )  
- Divide ( `/` )  
- Modulo ( `%` )  
- Integer division ( `//`)  
- Raise to Power Of ( `**` )  

To learn more about arithmetic operators and other types of operators, review the operators chapter.

## Advanced Math

Advanced math is required for certain types of Python applications. Two categories of Python applications that typically require advanced math are those that incorporate data science and robotics technologies. Don't let the advanced math required deter you from learning how to work with data science and robotics technologies. The Python ecosystem has libraries that make advanced math much easier for non-experts. Although those Python libraries and technologies are outside the scope of this course, you should know that they exist. Those libraries include numpy, scipy, pandas, and matplotlib.

## Errors With Numbers

Adding a number to other data types results in an error. For instance, adding an integer to a string results in an error. 

You should practice reading error messages very carefully. At first it can seem daunting if you're new to programming. However, oftentimes the answer is in the error message. 

Look at the following example. It says `TypeError: unsupported operand type(s) for +: 'int' and 'str'`. It's saying you can't add an integer to a string. It's `TypeError`, which here means that you're improperly trying to combine two different types in an incompatible way.  

Practice reading error messages! If you can become fluent in `error messages`, you will be much better off for it.  

```python
# example of an int
x = 3    

# adding a number to other data types results in an error
print(x + "hello")

>>> Traceback (most recent call last):
>>>   File "numbers.py", line 21, in <module>
>>>     print(x + "hello")
>>> TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
