# Operators and Expressions

Operators and expressions are critical for allowing your application to “make decisions” as it runs. **Operators** are symbols that perform some sort of function. **Operands** are the values on which the operator performs its function (the value can be a literal value or a variable). An **expression** is a sequence of operators and operands. Operators and expressions are used with conditionals and Booleans to write decision-making code.

Your Python code will will no doubt contain operators and expressions. This chapter discusses in detail arithmetic operators, comparison operators, logical operators, and identity operators.

## Arithmetic Operators

One type of operator that we discussed somewhat in the numbers chapter are arithmetic operators. Algebra operators allow for performing arithmetic operations on literal values and variables. You can add, subtrat, divide, multiply, and perform other algebraic operations. Order of operations are like in algebra. 

A few details to refresh some of what the numbers chapter covers. The result of division (/) is a float regardless of whether operands are both integers. The result of floor division (//) is rounded down. If positive this means the decimal is truncated. If negative, this means the absolute value of the number is rounded up resulting in a more negative number → - 2.7 is rounded to 3).

A few examples to refresh some of what the numbers chapter covers.

```python
# variable definitions
a = 9
b = 7
c = 3 

# examples of arithmetic operators
print(a + b - c) # this is an expression where a, b, and c are operands and +, - are the operators
print(+a)
print(-b)
print(c - b)
print(a * b)
print(a / c)
print(b % c)
print(b ** c)

>>> 3
>>> 9
>>> -7
>>> -4
>>> 63
>>> 3.0
>>> 1
>>> 343
```

## Comparison Operators

comparison operators check whether an expression is True or False
used to direct program flow, discussed more later
see Comparison Operators here for a list of operators

In operators_and_experessions.py, see
examples of comparison operators

be careful when comparing floats because the stored value of the float might be more precise than you realize
best practice for comparing floats is to check whether they are close in value
see Equality Comparison on Floating-Point Values here for more information

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



