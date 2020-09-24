# Functions

A function is a block of code that performs one or more tasks. Functions make your code easier to read, edit, and debug. Functions also allow you to write a block of code and then reuse it. This results in cleaner code and stays consistent with the programming principle of "don't repeat yourself." Once you define a function, you can call it multiple times. Functions also let you generalize or "abstract away" your code that you can use it in other applications.

Here is a function.

```python
# example of a function definition
def this_is_a_function():
    print('This is a function!')
```

Commonly referred to as a function, the example above is really a function definition. The code defines what the function does. It is a step-by-step "blueprint" for what happens when you call the function. Notice that nothing happens in the terminal if you run your file with just the code above. It doesn't print `This is a function!`.

Defining a function doesn't cause the Python interpreter to execute the code it. To execute the code, you need to call the function. Call a function somewhere below the function definition by typing the funnction name followed by parenthesis. When you call a function, the Python interpreter executes the code inside the function definition. When done, the processor removes the function from the call stack (i.e., the processor's "to do" list), which means that the processor can move on to perform the next task in the call stack.

```python
# example of a function definition
def this_is_a_function():
    print('This is a function!')

# example of calling a function
this_is_a_function()

>>> 'This is a function!'
```

In the code above, `this_is_a_function()` results in the terminal printing `This is a function!`. Defining a function in your code but not calling it is analogous to creating blueprint for building a home but not ever building the home. Therefore, remember to call your functions.

One thing that confuses beginners is terminology surrounding functions. You can define your own functions and call them, like the example above. You also can call functions that you import into your code from third-party software and packages. Functions someone else defined in code that you are using. For instance, you will use many of Python's built-in functions and functions from third-party libraries. Furthermore, you can create classes or objects containing functions that you can call. If you don't know what classes and object are, think of them as blocks of code that can have functions in them.

Regardless of where the function is defined and by whom, all functions have a few defining characteristics for beginners to focus on. They perform one or more defined tasks, can accept one or more inputs, can return one or more outputs, and must be called for the function to perform the tasks.

## [How to write a Python function](#how-to-write-a-python-function)

The syntax for defining a function starts with a line containing `def`, a name, and a list of parameters containing zero or more inputs. 

```python
def my_custom_function(#optional inputs):
   . . .
```

In the example above, the first line consists of `def` and the function name of `my_custom_function`. The line also has a list`(#optional inputs)`.

The Python interpreter understands `def` to mean that a function definition is following. The function name can be whatever you want so long as it doesn't conflict with a Python keyword. I recommend choosing names that are short but also specific and description. I also recommend choosing names that start with verbs, like `def get_users():`. It'll make your code easier to understand, so long as the function name describes the tasks it performs. The parameters after the name are optional. To include no parameters, simply put nothing inside the `()`. If, however, you include inputs, put them in the `()` and separate them with a `,`. If you define your function to accept inputs and include those inputs when you call the function, you can perform tasks inside your function using those input values. More on inputs below.

After the first line follows the code responsible for the tasks. You'll have things like `if / else` blocks, `for` loops, API requests, calculations, and more. It's good practice to keep your functions simple by performing only one or a small group of related tasks per function. You have the option to choose whether to include a `return` statement. Discussed in more detail below, the `return` statement is what your function outputs upon completing its tasks. By default, it outputs `None`, but you can override it.

Here is an example of a function that receives zero inputs and has no return statement. It prints `'My custom function'`.

```python
# example of a function that receives zero inputs and has no return statement
def my_custom_function():
   print('My custom function')

my_custom_function()

>>> 'My custom function'
```
Although the function doesn't explicitly include a `return` statement, it still performs the tasks inside it. Here, that task is `print('My custom function')`. The function also returns `None`. So it's doing two things -- performing the tasks inside and returning a value. Here, you don't save the return value in the memory. So the function returns `None` but your application does nothing with that value. More on this later.

Here is an example of a function that receives one input and has a return statement. 

```python
# define variable
type_of_pants = 'Jeans'

# example of a function that receives one input and has no return statement
def my_custom_function(pants_today):
   print(pants_today)

my_custom_function(type_of_pants)

>>> 'Jeans'
```

First, you define `type_of_pants` and set it equal to "Jeans". Comparing the function immediately above to the one above it, notice the difference in the first line: `def my_custom_function()` versus `def my_custom_function(pants_today)`. The second one receives an input named `pants_today`, whereas the first one receives no input. Now when you call the second function, you need to input a value in the function call. Here, you input `type_of_pants` when calling the function. Inside of the function, the value for `pants_today` equals that of `type_of_pants`. The function prints `pants_today`.


## [What is the Python return keyword](#what-is-the-python-return-keyword)

All functions return at least one value. As mentioned above, the default return value of a function is `None`. Accordingly, if you define a function that does not explicitly declare a `return` value, then the function returns `None`.

```python
# example of a function that receives zero inputs and has no return statement
def my_custom_function():
   print("My custom function")

custom_value = my_custom_function()

print(custom_value)

>>> 'My custom function'
>>> None
```

When you call the function, store the `return` value in the memory by setting it equal to a variable so that you can use it later. In the code above, you save the `return` value of my_custom_function() to `custom_value`. You know the function returns `None` because the value of `custom_value` when we print it is `None`.
In addition to returning `None`, the function also prints `'My custom function'`.

To customize what a function returns, explicitly declare it usng the keyword `return` at the end of your function. The `return` keyword exits a function, which means that any code in the same block appearing after the `return` statement will not run. Therefore, be thoughtful about where you put your `return` statement relative to the code you want to run. 

```python
def return_my_name_nothing_more():
    return 'My Name'
    print('did this print?')

nothing_more = return_my_name_nothing_more()
print(nothing_more)

>>> 'My Name'
```

In the code above, notice that after the line `return 'My Name'` is a line `print('did this print?')`. The Python interpreter does not execute the line `print('did this print?')` because that line appears after the `return` statement in the same block of code. Saving the `return` value of `return_my_name_nothing_more()` to the variable `nothing_more` and the printing `nothing_more` results in the terminal printing only `'My Name'`. It does not print `print('did this print?')`. 

`return` returns only the value placed on the same line as return. The value can span multiple lines, but it must at least start on the same line as the `return` keyword.

```python
# example of multi-line return value
def return_a_list_of_dicts():
    return [{
        "pants": 'Jeans',
        "shirt": 'Black t-shirt' 
    }, 
    {
        "pants": 'Khakis',
        "shirt": 'White t-shirt' 
    },{
        "pants": 'Shorts',
        "shirt": 'Gray t-shirt' 
    }]

list_of_dicts = return_a_list_of_dicts()
print(list_of_dicts)

>>> [{'pants': 'Jeans', 'shirt': 'Black t-shirt'}, {'pants': 'Khakis', 'shirt': 'White t-shirt'}, {'pants': 'Shorts', 'shirt': 'Gray t-shirt'}]

```

In the code above, the `return` value for `return_a_list_of_dicts` is a list of dictionaries. That list starts on the same line as `return` and ends several lines below. Calling `return_a_list_of_dicts()`, saving it to `list_of_dicts`, and printing `list_of_dicts` like above shows that your `return` value can span multiple lines. The example below shows that the `return` value must start on the same line as `value`

```python
# example of return value not starting on same line as return
def return_a_list_of_dicts():
    return 
    [{
        "pants": 'Jeans',
        "shirt": 'Black t-shirt' 
    }, 
    {
        "pants": 'Khakis',
        "shirt": 'White t-shirt' 
    },{
        "pants": 'Shorts',
        "shirt": 'Gray t-shirt' 
    }]

list_of_dicts = return_a_list_of_dicts()
print(list_of_dicts)

>>> None
```

Notice in the code above that the list of dictionaries starts on the line below `return`. Otherwise, it's the same code as the example above it. When you save the `return` value of `return_a_list_of_dicts()` to the variable `list_of_dicts` and then print `list_of_dicts`, the terminal prints `None`. 

## [What are Python parameters and arguments](#what-are-python-parameters-and-arguments)

Functions can be defined to accept one or more inputs. You define a function to accept inputs by putting named variables inside the parentheses in your function definition. In `def get_pants(pants)`, `pants` is the parameter. To define a function with no parameters, define it using an empty set of parentheses in the function definition. In `def get_pants()`, the function is defined to have no parameters. 

The term "parameter" refers to the input variable in the function definition. If your function definition has parameters, you need to either input values for each named variable in the function definition or define your function to have default values for those parameters.

Here is an example of a function definition for `get_pants` that accepts one parameter.

```python
# example of a parameter named pants in function definition
def get_pants(pants):
    print(pants)
    return 
```

In the `get_pants` function definition, `pants` is the parameter. In the example above, `print(pants)` prints the parameter `pants`.

The term "argument" refers to the actual value input for the parameter when you call the function. When calling `get_pants(pants_female)`, the argument is `pants_female` and therefore `pants` has the same value as `pants_female`. 

```python
# define variable
pants_female = (2, "Female Pants")

# example of a parameter named pants in function definition
def get_pants(pants):
    print(pants)
    return 

# example of calling function with an argument pants_female
get_pants(pants_female)

>>> (2, 'Female Pants')
```

In the code above, first you define a variable named `pants_female`. Then you define the `get_pants` function. Next you call the `get_pants` function while passing into it as an argument `pants_female`. The function prints the value for `pants`. Here, the value for `pants` is `pants_female`, and the value for `pants_female` is `(0, 'Female Pants')`. Therefore, running this script causes the terminal to print `(0, 'Female Pants')`.

Failing to include arguments in a function call for a function that requires them results in an error


```python
# define variable
pants_female = (2, "Female Pants"). 

# example of a parameter named pants in function definition
def get_pants(pants):
    print(pants)
    return 

# example of calling function with an argument pants_female
get_pants()

>>> 'TypeError: get_pants() missing 1 required positional argument: 'pants''
```

The code above is the same as the example before it, except here you call `get_pants()`. Notice that it is missing an argument. The Python interpreter has an error `TypeError: get_pants() missing 1 required positional argument: 'pants'`. The answer to your bug is right there in the error message. It says the function `get_pants()` has one missing argument named `pants`. At first, error messages can be confusing and easy to skip over. However, you need to practice reading error messages! Oftentimes, reading an error message can save you time and frustration, pointing you right to the problem.


You can define a function to have more than one parameter. Inside the `()` after the function name, in each parameter name separating them with commas `,`. Unless using keywords, more on that below, the order of arguments in your function call must match the order of parameters in the function definition. That is how python maps arguments in the function call to parameters in the function definition.

Here is an example of a function with two parameters, no keywords. The example shows how the function maps the arguments to parameters.

```python
# define variable
pants_female = (2, 'Female Pants')
shirts_female = (3, 'Female Shirts')

# example of a two parameters in function definition
def get_inventory(pants, shirts):
    print(pants)
    print(shirts)
    sentence = 'We have' + ' ' + str(pants[0]) + ' ' + pants[1]  + ' ' + 'and' + ' ' + str(shirts[0]) + ' ' + shirts[1]
    print(sentence)
    return

# example of calling function with an argument pants_female
get_inventory(pants_female, shirts_female)

>>> (2, 'Female Pants')
>>> (3, 'Female Shirts')
>>> 'We have 2 Female Pants and 3 Female Shirts'

# example of swapping the order of arguments
get_inventory(shirts_female, pants_female)

>>> (3, 'Female Shirts')
>>> (2, 'Female Pants')
>>> 'We have 3 Female Shirts and 2 Female Pants'
```

In the code above, you define two variables `pants_female` and `shirts_female`. You set each of them equal to a tuple, `(2, 'Female Pants')` and `(3, 'Female Shirts')`. Then you define a function named `get_inventory` that has two parameters `pants` and `shirts`. The function tasks are to print `pants` and `shirts` and to form a sentence `'We have' + ' ' + str(pants[0]) + ' ' + pants[1]  + ' ' + 'and' + ' ' + str(shirts[0]) + ' ' + shirts[1]` saved to a variable named `sentence`. The sentence is a string you built using `'We have'`, `'and'`, several `' '` for spaces, and the values from the tuples. Then you print `sentence`.  

Next you call `get_inventory(pants_female, shirts_female)`. The terminal prints `(2, 'Female Pants')` and then `(3, 'Female Shirts')`, which corresponds to the order from left to right of the parameters `pants` and `shirts`. It then prints `We have 2 Female Pants and 3 Female Shirts`, which also corresponds to the order from left to right of the parameters `pants` and `shirts`.

Next you swap the order of the arguments when you call `get_inventory(shirt_female, pants_female)`. The terminal prints `(3, 'Female Shirts')` and then `(2, 'Female Pants')`, which corresponds to the order from left to right of the swapped parameters `shirts` and `pants`. It then prints `We have 3 Female Shirts and 2 Female Pants`, which also corresponds to the order from left to right of the swapped parameters `shirts` and `pants`.

Those examples show how the order of arguments matters when not using keywords for parameters in the function call.

The example below is the same code as the example above, except this time the arguments in the function call are assigned to keywords that match the parameter names `get_inventory(pants=pants_female, shirts=shirts_female)`.

```python
# define variable
pants_female = (2, 'Female Pants')
shirts_female = (3, 'Female Shirts')

# example of a two parameters in function definition
def get_inventory(pants, shirts):
    print(pants)
    print(shirts)
    sentence = 'We have' + ' ' + str(pants[0]) + ' ' + pants[1]  + ' ' + 'and' + ' ' + str(shirts[0]) + ' ' + shirts[1]
    print(sentence)
    return

# example of calling function with an argument pants_female
get_inventory(pants=pants_female, shirts=shirts_female)

>>> (2, 'Female Pants')
>>> (3, 'Female Shirts')
>>> 'We have 2 Female Pants and 3 Female Shirts'
```

By setting in the function call `pants=pants_female` and `shirts=shirts_female`, you explicitly declare which argument belongs to which parameter.

You can use keywords when calling a function to specify the argument values in whatever order you want. The keywords used for arguments must have a corresponding parameter with the same name. 

The example below swaps the order of the arguments in the function call so that `shirts` comes before `pants`. The print statements, however, print `pants` before `shirts`. So it works like how it did with no keywords when `pants` came before `shirts`. That's because you mapped the arguments to parameters using keywords.

```python
# define variable
pants_female = (2, 'Female Pants')
shirts_female = (3, 'Female Shirts')

# example of a two parameters in function definition
def get_inventory(pants, shirts):
    print(pants)
    print(shirts)
    sentence = 'We have' + ' ' + str(pants[0]) + ' ' + pants[1]  + ' ' + 'and' + ' ' + str(shirts[0]) + ' ' + shirts[1]
    print(sentence)
    return

# example of calling function with an argument pants_female
get_inventory(shirts=shirts_female, pants=pants_female)

>>> (2, 'Female Pants')
>>> (3, 'Female Shirts')
>>> 'We have 2 Female Pants and 3 Female Shirts'
```

In the code above, you swapped the order of `shirts=shirts_female` and `pants=pants_female` in the function call. Although you swapped the order, the print statements in the terminal are the same as the examples before it. That's because you explicitly declared using keywords which argument belongs to which parameter. So first it prints `pants` having a value of `(2, 'Female Pants')` and then `shirts` having a value of `(3, 'Female Shirts')` and finally `sentence` having a value of `'We have 2 Female Pants and 3 Female Shirts'`. 

## [What are Python default values for functions](#what-are-python-default-values-for-functions)

So far you've seen examples of function definitions with paramters but without setting any default values for those parameters. Using default values can help prevent bugs. If a parameter has a default value, then calling the function without including an argument for the parameter will not cause an error. Rather, it'll just run the function with the parameter's default value.

Here is an example of a function named `get_socks` that has a parameter named `socks`. The only thing the function does is `return socks`. The parameter has no default value.

```python
# define variable
socks_large = (2, "Large socks")

#define functiont that gets socks
def get_socks(socks):
   return socks

large_socks = get_socks(socks_large)

print(large_socks)

>>> (2, 'Large socks')
```

When you call the function and pass into an argument of `socks_large`, it returns the value of `socks_large`, which is `(2, 'Large socks')`.

If you call that same funciton without passing it an argument, you get an error. The code below is the same as in the example above except `large_socks = get_socks(socks_large)` is changed to have no argument `large_socks = get_socks()`.

```python
# define variable
socks_large = (2, "Large socks")

#define functiont that gets socks
def get_socks(socks):
   return socks

large_socks = get_socks()

print(large_socks)

>>> 'TypeError: get_socks() missing 1 required positional argument: 'socks''
```

This results in an error `TypeError: get_socks() missing 1 required positional argument: 'socks'`. This is telling you that `get_socks()` is missing one argument called `socks`.

By setting a default value for `socks` in the function definition, you can avoid that error. You can call the function without inputting an argument and also without causing an error. See the example below, which is the same code as in the example above except it has a default value set for the parameter. Hence, the only change is from `def get_socks(socks)` to `def get_socks(socks=(0, "No socks")).`

```python
# define variable
socks_large = (2, "Large socks")

#define functiont that gets socks
def get_socks(socks=(0, "No socks")):
   return socks

default_socks = get_socks()
large_socks = get_socks(socks_large)

print(default_socks)
print(large_socks)

>>> (0, 'No socks')
>>> (2, 'Large socks')
```

In the code above, you called `default_socks = get_socks()`. Although the function definition has a parameter and although you didn't pass an argument into the function call, the function ran error-free because you defined the parameter as having a default value. That's why the example prints `(0, 'No socks')`. It's the default value for `socks`.

In the code above, you also called `large_socks = get_socks(socks_large)`. Although the function definition has a parameter with a default value, the function ran error-free and returned the value of socks_large because you called the function with an argument in the call. That argument overrides the default. That's why for the line `print(large_socks)` the example prints `(2, 'Large socks')`.

If your function has multiple parameters but not all have default values, put parameters that have default values at the end of the list of parameters in your function definition

```python
# define variable
socks_large = (2, "Large socks")

#define functiont that gets socks
def get_socks(small_socks=(0, "No small socks"), medium_socks=(0, "No medium socks"), large_socks):
   return small_socks, medium_socks, large_socks

large_socks = get_socks(socks_large)

print(large_socks)

>>> 'SyntaxError: non-default argument follows default argument'
```
In the example above, the parameters that have default values come before the one that doesn't. The one that doesn't is at the end of the list of parameters. This results in an error `SyntaxError: non-default argument follows default argument`.

If, however, we put at the beginning of the parameter list the parameter that does not have a default value, the function runs without error.

```python
# define variable
socks_large = (2, "Large socks")

#define functiont that gets socks
def get_socks(large_socks, small_socks=(0, "No small socks"), medium_socks=(0, "No medium socks")):
   return small_socks, medium_socks, large_socks

large_socks = get_socks(socks_large)

print(large_socks)

>>> ((0, 'No small socks'), (0, 'No medium socks'), (2, 'Large socks'))
```

In the example above, the parameters are in the proper order having the parameters with default values appear at the end of the parameter list `def get_socks(large_socks, small_socks=(0, "No small socks"), medium_socks=(0, "No medium socks")):`. `large_socks` is at the front of the list and the other two with default values appear after. Then when you call the function and pass it only one argument `large_socks = get_socks(socks_large)`, the Python interpreter maps the argument `socks_large` to the first parameter `large_socks`. For the other two parameters, the Python interpreter uses the default values. Hence, the example prints `((0, 'No small socks'), (0, 'No medium socks'), (2, 'Large socks'))`.


## [What is scope](#what-is-scope)

Scope means the parts of your code that a Python object has access to. For instance, you have the global scope. A block of code is in the global scope if it is not indented. All other scopes are considered local. Local scopes are those that have some indentation. Local scopes therefore belong to things like functions, expressions, loops and classes. Although local scopes are within the global scope, you need to import global variables into local scopes to use them in the local scope.

```python
# example of variable in global scope
pants_male = (2, "Male Pants")
print(pants_male)

# example of variable in local scope of a function
def get_inventory():
    pants_female = (3, "Female Pants")
    print(pants_female)
    return

get_inventory()

>>> (2, 'Male Pants')
>>> (3, 'Female Pants')
```

In the code above, you define the variable `pants_male` in the global scope and print it. Then, you define the variable `pants_female` in the local scope of `get_inventory()`, which has one task -- to print `pants_female`. The code prints in the terminal `(2, 'Male Pants')` followed by `(3, 'Female Pants')`.

If you move `print(pants_male)` from the global scope into the `get_inventory` local scope, you need to import the `pants_male` variable into the scope of `get_inventory` or else you get an error.

```python
# example of variable in global scope
pants_male = "Male Pants"

# example of variable in local scope of a function
def get_inventory():
    pants_female = 'Female Pants'
    pants_male = pants_male + ' In Stock'
    print(pants_male)
    print(pants_female)
    return

get_inventory()

>>> 'UnboundLocalError: local variable 'pants_male' referenced before assignment'
```

In the code above, `print(pants_male)` is no longer in the global scope. It is in the local scope of `get_inventory` despite it being defined in the global scope. In the function, you set `pants_male = pants_male + ' In Stock'`. The Python interpreter, however, can't perform that operation. Instead, it returns the error `'UnboundLocalError: local variable 'pants_male' referenced before assignment'` because inside the scope of `get_inventory` the Python interpreter doesn't know what `pants_male` is. Because it doesn't know what what `pants_male` is, the interpreter can't add anything to it. You can't operate on a variable before defining it. Because we didn't import the definition of `pants_male` from the global and also didn't provide a new definition inside the local scope for `pants_male`, the local scope can't operate on `pants_male` to add `' In Stock'`.

To fix that, simply import the `pants_male` variable from the global scope into the scope for `get_inventory`. Now the local scope has access to `pants_male` in the `global` scope.

```python 
# example of variable in global scope
pants_male = 'Male Pants'

# example of variable in local scope of a function
def get_inventory():
    global pants_male
    pants_female = 'Female Pants'
    pants_male = pants_male + ' In Stock'
    print(pants_male)
    print(pants_female)
    return

get_inventory()

>>> 'Male Pants In Stock'
>>> 'Female Pants'
```

The code above is the same as the example before it, except this example has as the first line of the `get_inventory` function the line `global pants_male`. The keyword `global` is Python's way of identifying something in the global scope. By writing `global pants_male`, you tell the interpreter to get `pants_male` from the global scope and use it inside this local scope. Now the function knows what `pants_male` is and can operate on it. The code prints `Male Pants In Stock` and `Female Pants`.

If in the `global` scope you try to print a variable defined in the local scope, you get an error. See below where you try to print in the `global` scope the variable `pants_female` in the `global` scope.

```python 
# example of variable in global scope
pants_male = 'Male Pants'

# example of variable in local scope of a function
def get_inventory():
    global pants_male
    pants_female = 'Female Pants'
    pants_male = pants_male + ' In Stock'
    print(pants_male)
    return

print(pants_female)
get_inventory()

>>> 'NameError: name 'pants_female' is not defined'
```

The example above is the same as before it, except this example has deleted `print(pants_female)` from the function and has also added toward the bottom in the `global` scope the line `print(pants_female)`. Because `pants_female` is defined in the local scope of `get_inventory`, the Python interpreter doesn't know in the `global` scope what `pants_female` is when reading `print(pants_female)` and therefore returns an error `'NameError: name 'pants_female' is not defined'`.

You can define a variable in a local scope and make it available in the `global` scope by returning the value from the function and saving it to a variable. 

```python
# example of variable in global scope
pants_male = 'Male Pants'

# example of variable in local scope of a function
def get_inventory():
    global pants_male
    pants_female = 'Female Pants'
    pants_male = pants_male + ' In Stock'
    print(pants_male)
    return pants_female

female_pants = get_inventory()
print(female_pants)

>>> Male Pants In Stock
>>> Female Pants
```

The example above is the same as the one before it, except this example returns `pants_female` instead of nothing and also replaces `print(pants_female)` and `get_inventory()` at the bottom in the `global` scope with `female_pants = get_inventory()` and `print(female_pants)`. What you've done is make `pants_female` available in the `global` scope by returning it from `get_inventory`. The output in the terminal is `Male Pants In Stock` and `Female Pants`.

One benefit of having different scopes for different parts of your code is that it prevents conflicts between variables. Conflicts occur when you have two or more variables with the same name in the same scope. So you may define `pants_male = 10` in one place and then later define `pants_male = 20`. Even if the Python intepreter is able to run error free despite multiple same names, your application may not behave as you expect. You may think, for instance, that `pants_male` should equal `10` not realizing that you accidentally overrode that value with `pants_male = 20`. 

Creating local scope and being thoughtful with your names will prevfent conflicts. Unless you make a variable available outside of its scope of origin, a variable created within a certain scope is accessible only within that block of code. Therefore its name is not going to conflict with a variable of the same name in a different scope.


## [What is a docstring](#what-is-a-docstring)
The first line of every function is a docstring. A docstring is a string and is supposed to describe what the function does. Functions aren't the only Python objects that have docstring. So do modules, classes, and methods 

The default value for a docstring is `None`. You can customize the docstring by putting at the top of the function three single quotes followed by your description followed by three more single quotes `''' . . . '''`.

To access the messag, chain `__doc__` to the function name `get_inventory.__doc__`. 

```python
# example of the default docstring None
def get_inventory():
    pants_female = 'Female Pants'
    return pants_female

print(get_inventory.__doc__)

>>> None
```

In the example above, the function does not declare a docstring. Accordingly, printing `get_inventory.__doc__` returns `None`. If you declare a docstring at the top of the function definition, for instance `'''returns pants_female'''`, printing `get_inventory.__doc__` returns the docstring `returns pants_female`.

```python
# example of overriding the default docstring
def get_inventory():
    '''returns pants_female'''
    pants_female = 'Female Pants'
    return pants_female

print(get_inventory.__doc__)

>>> 'returns pants_female'
```
This is good for communicating with other developers and yourself. You should write short but descriptive docstrings for your functions. You also should use them on functions from third-party libararies to help understand what they do.

Here is an example of printing the docstring for Python's `print` method.

```python
# example of printing print.__doc__
print(print.__doc__)

>>> print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

>>> Prints the values to a stream, or to sys.stdout by default.
>>> Optional keyword arguments:
>>> file:  a file-like object (stream); defaults to the current sys.stdout.
>>> sep:   string inserted between values, default a space.
>>> end:   string appended after the last value, default a newline.
>>> flush: whether to forcibly flush the stream.
```

Wow! Way more complex than `'returns pants_female'` and also too complex for this lesson. However, now you see how you can get information about a function, method, class, or module. Regardless of whether you understand it now, it's good practice to read it and try to understand it. Also, you should try playing around with it or Google search what it means. 
