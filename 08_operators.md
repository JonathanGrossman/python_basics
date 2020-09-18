# Operators and Expressions

Operators and expressions are critical for allowing your application to “make decisions” as it runs. **Operators** are symbols that perform some sort of function. **Operands** are the values on which the operator performs its function (the value can be a literal value or a variable). An **expression** is a sequence of operators and operands. Operators and expressions are used with conditionals and Booleans to write decision-making code.


```python
# variable definitions
a = 9
b = 7
c = 3 

# a + b - c is an expression where a, b, and c are operands and + and - are the operators
print(a + b - c) 

>>> 3
```

Your Python code will will no doubt contain operators and expressions. This chapter discusses in detail 

- arithmetic operators   
- comparison operators  
- logical operators  
- identity operators  

## Arithmetic Operators

One category of operator is arithmetic. Arithmetic operators allow for performing algebra with values and variables. Using arithmetic operators, you can add, subtract, divide, multiply, and perform other algebraic operations. In Python, you can work with numbers similar to how you would on a calculator. One thing that makes math with Python easier is that you don't have to learn special "Python math". Arithmetic operators are very similar to regular algebra. 

Here are examples of the common basic arithmetic operators in Python.

Add ( `+` )
```python
print(4 + 8)

>>> 12
```

Subtract ( `-` )
```python
print(9 - 5)

>>> 4
```

Multiply ( `*` )
```python
print(9 * 5)

>>> 45
```

Divide ( `/` )
```python
print(9 / 5)

>>> 1.8
```

Modulo ( `%` ) 
```python
# returns remainder
print(9 % 5)

>>> 4
```

Integer division (`//`)
```python
# returns int and rounds down
print(4 // 8) 

>>> 0
```

Raise to Power Of ( `**` )
```python
print(4 ** 8)

>>> 65536
```

For expressions that have more than one arithmetic operator, the order of operations in Python are the same as in algebra. 

```python
# variable definitions
a = 9
b = 7
c = 3 

# examples of order of operations
print(a + b * c)

>>> 30


print((a + b) * c)

>>> 48
```

The result of division (`/`) is a float regardless of whether operands are both integers.  

```python
# examples of numbers
x = 3    # int
y = 7.9  # float

# adding an int to a float returns a float
print(x + y)

>>> 10.9
```

The result of floor division (`//`) is rounded down. If positive this means the decimal is truncated. If negative, this means the absolute value of the number is rounded up resulting in a more negative number → `- 2.7` is rounded to `3`).  

```python
# examples of numbers
x = 3    # int
y = 7.9  # float
z = -7.9 # float

# examples of floor division
print(y / x)
print(y // x)

>>> 2.6333333333333333
>>> 2.0

print(z / x)
print(z // x)

>>> -2.6333333333333333
>>> -3.0
```

Python has syntax shortcuts you can use to make your code more efficient. For instance, you can use `+=` or `-+` or `*=` as shorthand in expressions. Writing `x += 10` is the same as writing `x = x + 10`. Get used to seeing this shorthand in other people's code becuase it is common for developers to use this shorthand.

```python
# example using += as shorthand
starting_number = 1
starting_number += 10
print(starting_number)

>>> 11
```

## Comparison Operators

Comparison operators check whether an expression is True or False. Comparison operators are used to direct the flow of your Python application.

```python
# variable definitions
a = 9
b = 7
c = 3
```

Equal To ( `==` )
```python
print(a == c)

>>> False
```


Not Equal To ( `!=` )
```python
print(c != b)

>>> True
```


Greater Than ( `>` )
```python
print(c > b)

>>> False
```

Less Than ( `<` )
```python
print(c < b)

>>> True
```

Greater Than or Equal To ( `>=` )
```python
print(c >= b)

>>> False
```

Less Than or Equal To ( `<=` )
```python
print(c <= b)

>>> True
```
Complex Expression
```python
print(b <= c + 4)

>>> True
```

Be careful when comparing floats because the stored value of the float might be more precise than you realize. A good practice for comparing floats is to check whether they are close in value. See this [Real Python article](https://realpython.com/python-operators-expressions/#equality-comparison-on-floating-point-values) for more information.

## Logical Operators

logical operators are not, or, and and
can be used to check whether an expression is True or False
a simple yet powerful way to chain expressions to make complicated conditionals
see Logical Operators here for a list of operators

In operators_and_experessions.py, see
examples of logical operators

in addition to comparing Boolean values, you can use logical operators to compare non-Boolean objects and expressions, such as numbers, strings, lists, tuples, dicts, sets, expressions, and functions
the result of such non-Boolean comparisons is “truthy” or “falsy”
falsy:
The False Boolean value; Number with a value of zero; Empty string, list, tuple, dict, and set objects; Python’s None value

truthy: everything else

when using logical operators to compare non-Boolean operands, the truthiness determines the outcome and the type of the result varies depending upon the operator
for not, “truthy” objects and expressions are True and “falsy” objects and expressions are False
for or and and, the result is the value of one of the operands, evaluated from left to right
For or, it returns the first operand that is “truthy” or, if none are “truthy”, returns the last operand 
For and, if all operands are truthy, it returns the last operand; if none are truthy, it returns the first operand

use operators to avoid exceptions (prevent your program from having an error)
use operators to set a default value

In operators_and_experessions.py, see
examples of logical operators for avoiding exceptions
examples of logical operators for setting default values

# Identity Operators

the identity operators are is and is not 
in contrast to other operators, which compare the operand data value, identity operators evaluate whether two or more operands are the same Python object stored in memory

In operators_and_experessions.py, see
examples of identity operators



