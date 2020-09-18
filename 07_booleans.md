# Booleans

The Boolean data type in Python is the `True` or `False` data type. In other words, the only two Boolean values are `True` and `False`. Although simple in terms of possible values, Booleans play an very important role for nearly every Python application because Booleans are critical for decision-making by your application.

Capitalization matters. In Python, you must capitalize `True` and `False` for the Python intepreter to recognize it as a Boolean. If you want to use the word True or False as a string, you need to wrap it in quotes.

If you want to check Boolean value of a Python object, use the built-in bool() function. It represents Boolean type and is a subset of int(). Most values are inherently True. For instance, numbers other than 0, strings that have text in them, and other data types that have non-empty values. Some values, however, are inherently False. For instance, empty values (i.e., other data types that have no value, like "", (), and {}), the number 0, and None are inherently False. 

```python
# example of a values that evaluates to True
print(bool(7))
print(bool("Python is fun"))
print(bool(["Python," "programming", "basics"]))
print(bool(("Python," "programming", "basics")))
print(bool({
    "first": "Python", 
    "second": "programming", 
    "third": "basics"
}))

>>> True
>>> True
>>> True
>>> True
>>> True

# example of a values that evaluates to False
print(bool(0))
print(bool(""))
print(bool([]))
print(bool(()))
print(bool({}))

>>> False
>>> False
>>> False
>>> False
>>> False
```

In addition to checking the Boolean value of an **object**, you can check the Boolean value of a Boolean **expression**. A Boolean expression is an expression that evaluates to True or False. As for objects, use the same built-in bool() function for expressions. Whether it returns `True` or `False` depends on the details of the expression.

```python
# example of an expression that evaluates to True
print(7 > 3)
print(bool(7 > 3))

>>> True
>>> True

# example of an expression that evaluates to False
print(7 < 3)
print(bool(7 < 3))

>>> False
>>> False
```

You will see Booleans in action in examples from other sections, like operators, expressions, and conditionals.
