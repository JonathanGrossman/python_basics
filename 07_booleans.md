# Booleans

The Boolean data type in Python is the `True` or `False` data type. In other words, the only two Boolean values are `True` and `False`. Although simple in terms of possible values, don't let their simplicitly suggest to you that they are not important. Booleans play an very important role for nearly every Python application because Booleans are critical for decision-making by your application.

Capitalization matters. In Python, you must capitalize `True` and `False` for the Python intepreter to recognize it as a Boolean. On the flip side, if you use `True` or `False` without quotes but mean for it to be a string, Python will interpret it as a Boolean. Therefore, if you want to use the word True or False as a string, you need to wrap it in quotes.

Sometimes you will want to check if a value is `True` or `False`. A common scenario is having a variable that starts off as empty or `0`, which makes it inherently `False`. For the sake of example, you call that variable `number_of_users` and give it a value of `0`. Therefore, when your application starts, `number_of_users = 0` and therefore evaluates to `False`.

After the program starts, something happens that changes the value of `number_of_users`. Let's say the something that happened is that your application requested from your database the number of users for your application. Upon receiving the response from your database, your applicatoin set the value of `number_of_users` to `119`. Now that `number_of_users` no longer equals `0`, `number_of_users` evaluates to `True`. 

One way to check Boolean value of a Python object is to use the built-in bool() function. It represents Boolean type and is a subset of int(). Most values are inherently `True`. For instance, numbers other than 0, strings that have text in them, and other data types that have non-empty values. 

Some values, however, are inherently `False`. For instance, empty values (i.e., other data types that have no value, like `""`, `()`, and `{}`), the number `0`, and `None` are inherently `False`. 

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

You don't have to use the `bool()` function in an expression to control the flow of your application. For instance, instead of writing `if bool(7)`, you can simply write ` if 7`. You may, however, find that at times using `bool()` makes your code more expressive and therefore easier for others to understand.

In addition to checking the Boolean value of an **object**, you can check the Boolean value of a Boolean **expression**. A Boolean expression is an expression that evaluates to `True` or `False`. As for objects, you can use the same built-in `bool()` function for expressions or you can evalute the expression directly (without using `bool()`). Whether it returns `True` or `False` depends on the details of the expression.

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
