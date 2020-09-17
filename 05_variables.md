# Variables

A variable in Python is how you store data in your computer's memory. By storing data in memory, your application can access that data while running your application. You can store almost anything as a variable. For instance, you can store numbers, strings, dictionaries, lists, tuples, functions, and more.

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
- **should** start with __ (a double underscore, e.g., __private_variable) to represent private variables (indicating to other developers to read but not set its value)


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

## Casting

You can set a variable's type using one of the built-in Python constructor functions. The Python data types each have their own constructor function. The constructor function you use will convert the value into the corresponding data type. For instance, using Python's built-in float constructor function `float()` will turn into a float whatever value you pass into it (assuming it's a valid value for that function).

```python
a = float(17)     # x's value is 17.0
b = float(17.3)   # y's value is 17.3
c = float("17")   # z will be 17.0
```

Here is a list of Python constructor functions:

- int(100)
- float(100.1)
- str("Israel Tech Challenge")
- bool(100) # True x = bool(0) # False
- list(("Israel Tech Challenge"))
- tuple(("Israel Tech Challenge"))
- dict(name="ITC", success=True)
- set(("Israel Tech Challenge"))
- bytes(100)

## None

At times you may want a variable to exist but to have an empty value. In those situations, you can assign a variable to be equal to `None`. That variable will represent an empty value. For those of you with JavaScript experience, `None` is equivalent to `null`. 


```python
# example of printing None
print(None, type(None))  
>>> None, <class 'NoneType'>
```

