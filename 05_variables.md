# Variables

In Python, you use variables to store data in your computer's memory. By storing data in memory, your application can access that data while running your application. If you have a number, for instance, in your Python code, but you don't save it to a variable, the Python interpreter will not remember that number as it continues reading the remainder of your. If, however, you save that number to a variable (e.g., `x = 10`), Python stores `x` in memory and assigns it a value of `10`. With the value stored in memory, you can use it later in your code.

```python
# example of storing a value in a variable and using it later
y = 20
print(10 + y)

>>> 30
```

You can store almost anything as a variable. You can store numbers, strings, dictionaries, lists, tuples, functions, and more. When storing data in memory, the syntax requires the variable on the left, followed by an equals sign, followed by the value to the right of the equals sign:

```python
# example of variable where g is the variable and the string is the value
g = "Programming in Python is fun."
```

Variables are, well, variable. In Python, you can change the value of variables. For instance, if you initially declare a variable named `x` and set it equal to `10` (`x = 10`), you later can change the value of `x` to something else, like `x = 21`. 

Because Python allows for dynamic typing, in addition to changing the the value, you can also change the type. Accordingly, instead of changing the value of `x` to another integer like `21`, you can change it to some other data type, like a string. For instance, you can change it to `x= "Ten"`. 

Variables aren't always meant to be varied. Variables are much more complex than most beginners realize. Here is a short list of advice that can help you write better Python code and also to become better at reading Python code.

Variables: 

- **must** be assigned a value before you can use the variable
- **must** start with _ or lowercase letter
- **are** case sensitive
- **can** include letters, _, or numbers
- **can** have their value changed
- **can** be set to any data type
- **can** be assigned to another variable
- **can** be set along with more than one other variable in a single expression
- **should** generally be snake_case
- **should** be IN_ALL_UPPERCASE to represent a constant (to indicate to other developers that the variable should not be changed, only read)
- **should** be in UpperCamelCase to represent a class
- **should** start with a double underscore to represent private variables (indicating to other developers to read but not set its value)


## [Examples of variables](#examples-of-variables)

You must assign a variable a value before you can use the variable  
```python
# example of assigning a value to a variable before using the variable
j = 10  
print(j)
>>> 10
```


You can change the value of a variable (hence the meaning of “variable”)  
```python
# example of changing a variable's value
j = 10 
print(j)
>>> 10

j = 20    
print(j)  
>>> 20
```

You can set variables equal to any data type  
```python
# example of setting a variable to a string
g = "this is a letter"   
print(g) 
>>> "this is a letter" 
```

You can assign a variable to a variable  
```python
# example of assigning a variable to a variable
g = 18
j = g    
print(j)
>>> 18
```

You can set multiple variables in one expression  
```python
# example of setting multiple variables in one expression
a, b, c = 1, 2, 3    
print(a)  
print(b)  
print(c)  
>>> 1
>>> 2
>>> 3
```

If a variable is assigned a value, you can use it
```python
# example of usnig a variable after assigning it a value
k = 12  
print(k)
>>> 12
print(k + 1)  
>>> 13
```

If you have not assigned a value to a variable, you can't use it  
```python
# example of trying to use a variable before assigning it a value
k = k + 1  
print(k)  

>>> Traceback (most recent call last):
>>>   File "variables_data_types.py", line 62, in <module>
>>>     k = k + 1
>>> NameError: name 'k' is not defined
```

## [Casting](#casting)

You can set a variable's type using one of the built-in Python constructor functions. The Python data types each have their own constructor function. The constructor function you use will convert the value into the corresponding data type. For instance, using Python's built-in float constructor function `float()` will turn into a float whatever value you pass into it (assuming it's a valid value for that function).

```python
# example of using the float() constructor function
a = float(17)     # x's value is 17.0
b = float(17.3)   # y's value is 17.3
c = float("17")   # z will be 17.0
```

Here is a list of Python constructor functions:
```python
# example of constructor function for integer
int(100)

# example of constructor function for float
float(100.1)

# example of constructor function for string
str("Python")

# example of constructor function for bool
bool(100) # True 
bool(0) # False

# example of constructor function for list
list(("Python"))

# example of constructor function for tuple
tuple(("Python"))

# example of constructor function for dict
dict(name="Python", success=True)

# example of constructor function for set
set(("Python"))

# example of constructor function for bytes
bytes(100)
```

## [None](#none)

At times you may want a variable to exist but to have an empty value. In those situations, you can assign a variable to be equal to `None`. That variable will represent an empty value. For those of you with JavaScript experience, `None` is equivalent to `null`. 


```python
# example of printing None
print(None, type(None))  
>>> None, <class 'NoneType'>
```

