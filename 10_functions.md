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

## How to write a Python function

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


## Return

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

## Arguments and Parameters

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
pants_female = (2, "Female Pants")

# example of a parameter named pants in function definition
def get_pants(pants):
    print(pants)
    return 

# example of calling function with an argument pants_female
get_pants()

>>> TypeError: get_pants() missing 1 required positional argument: 'pants'
```

The code above is the same as the example before it, except here you call `get_pants()`. Notice that it is missing an argument. The Python interpreter has an error `TypeError: get_pants() missing 1 required positional argument: 'pants'`. The answer to your bug is right there in the error message. It says the function `get_pants()` has one missing argument named `pants`. At first, error messages can be confusing and easy to skip over. However, you need to practice reading error messages! Oftentimes, reading an error message can save you time and frustration, pointing you right to the problem.


You can define a function to have more than one parameter. Unless using keywords when calling a function, order of arguments must match order of parameters because that is how python maps arguments in the function call to parameters in the function definition.

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
```

In the code above, you define two variables `pants_female` and `shirts_female`. You set each of them equal to a tuple, `(2, 'Female Pants')` and `(3, 'Female Shirts')`. Then you define a function named `get_inventory` that has two parameters `pants` and `shirts`. The function tasks are to print `pants` and `shirts` and to form a sentence `'We have' + ' ' + str(pants[0]) + ' ' + pants[1]  + ' ' + 'and' + ' ' + str(shirts[0]) + ' ' + shirts[1]` saved to a variable named `sentence`. The sentence is a string build using the values from the tuples. Then you print `sentence`.  Next you call `get_inventory(pants_female, shirts_female)`. The terminal prints `(2, 'Female Pants')` and then `(3, 'Female Shirts')`, which corresponds to the order from left to right of the parameters `pants` and `shirts`. It then prints `We have 2 Female Pants and 3 Female Shirts`.



unless using keywords, order of arguments matters

set default values for your custom parameters in your function definitions

default values can help prevent bugs

calling a function that has a default value set for parameters allows you to call the function without inputting arguments

In functions.py, see 
default values for custom parameters


use keywords when calling a function to specify the argument values in whatever order you want
using keywords can make code easier to read
the keywords used for arguments must have a corresponding parameter with the same name
if your function has multiple parameters but not all have default values, put parameters that have default values at the end of the list of parameters in your function definition

In functions.py, see 
using keywords when passing in arguments

## Scope

scope is the block of code (environment) in which a value is accessible to other code
your code has a global scope, which is the level of code where values are accessible to all other blocks / lines of code
you can create additional scopes using functions, conditionals, and classes
scope can prevent conflicts between your code because a variable created within a certain scope is accessible only within that block of code (unless you make it available somehow)
using special syntax, access to a value within a scope can be overcome by making that value accessible to other scopes

In functions.py, see 
this is the global scope
this is the destination_tel_aviv_scope
this is the global scope
this is what happens when you are out of scope

NameError: name 'coding_language' is not defined


practice reading error messages!

inside of a function, before you are able to manipulate a global variable, you need to specify that the variable is from the global scope by using the word global before the variable within the function

to do so, use the global keyword inside the new scope

or else you get an error

UnboundLocalError: local variable 'total' referenced before assignment

practice reading error messages!
In functions.py, see 
examples using global keyword

## __doc__
at the top of each function use three sets of quotes to write a brief message about what the function does; 

then use __doc__ to retrieve the message; this is good for communicating with other developers and yourself



In functions.py, see 
example using triple quotes and __doc__


try on Python’s built-in functions!
