# Functions

A function is a block of code that performs one or more tasks. Functions make your code easier to read, edit, and debug. Functions also allow you to write a block of code and then reuse it. The results in cleaner code and stays consistent with the programming principle of "don't repeat yourself." Once you define a function, you can call it multiple times. Functions also let you generalize or "abstract away" your code that you can use it in other applications

Here is a function.

```python
# example of a function definition
def this_is_a_function():
    print("This is a function!")
```

Commonly referred to as a function, the example above is really a function definition. The code defines what the function does. It is a step-by-step "blueprint" for what happens when you call the function. Notice that nothing happens in the terminal if you run your file with just the code above. It doesn't print `This is a function!`.

Defining a function doesn't cause the Python interpreter to execute the code it. To execute the code, you need to call the function. Call a function somewhere below the function definition by typing the funnction name followed by parenthesis.

```python
# example of a function definition
def this_is_a_function():
    print("This is a function!")

# example of calling a function
this_is_a_function()

>>> 'This is a function!'
```

In the code above, `this_is_a_function()` results in the terminal printing `This is a function!`. Defining a function in your code but not calling it is analogous to creating blueprint for building a home but not ever building the home. Therefore, remember to call your functions.

One thing that confuses beginners is terminology surrounding functions. You can define your own functions and call them, like the example above. You also can call functions that you import into your code from third-party software and packages. Functions someone else defined in code that you are using. For instance, you will use many of Python's built-in functions and functions from third-party libraries. Furthermore, you can create classes or objects containing functions that you can call. If you don't know what classes and object are, think of them as blocks of code that can have functions in them.

Regardless of where the function is defined and by whom, all functions have a few defining characteristics for beginners to focus on. They perform one or more defined tasks, can accept one or more inputs, can return one or more outputs, and must be called for the function to perform the tasks.

## How to write a Python function

The basic syntax for defining a function starts with a line containing `def`, a name, and a list of parameters containing zero or more inputs. The Python interpreter understands `def` to mean that a function definition is following. The function name can be whatever you want so long as it doesn't conflict with a Python keyword. I recommend going with names that are short but also specific and desription. The parameters are values that you pass into the funciton when calling it. By passing values into the function, you can perform tasks inside your function using those input values.

After the first line follows the code responsible for the tasks. You'll have things like `if / else` blocks, `for` loops, API requests, calculations, and more. It's good practice to keep your functions simple by performing only one or a small group of related tasks per function. You have the option to choose whether to include a return statement. Discussed in more detail below, the return statement is what your function outputs upon completing its tasks. By default, it outputs `None`, but you can override it.

```python
def my_custom_function(#optional inputs):
   # code to perform tasks
   # optional return
```

In the example above, the first line consists of `def` and the function name of `my_custom_function`. The line also has a list(#optional inputs). It's followed by two comments indicating where your function code and return statement belong.

my_custom_function()

example:

def print_my_info():
  	print(“My name is Joe Lecturer”)
print(“I am from the Mountains.”)
print(“But I love long walks on the beach.”)

		print_my_info()

>>>> My name is Joe Lecturer
>>>> I am from the mountains.
>>>> But I love long walks on the beach.

## Return
output: all functions return at least one value
output: the default return value is None
output: the way to customize the return values from a function is to use return
In functions.py, see 
basic function examples
example using return
returns None as the default return value

key points about using return: 
exits the function, which means that code below it will not run, so be thoughtful about where you put your return statement
outputs the value placed on the same line as return
removes the function from the call stack, which means that the processor can move on to perform the next task in the call stack
when you call the function, store the return value in the memory by setting it equal to a variable so that you can use it later 

## Arguments and Parameters
input: all functions can be defined to accept one or more inputs

“parameter” refers to the input variable in the function definition

“argument” refers to the actual value input for the parameter when you call the function

the default is no inputs, which is designated by any empty set of parentheses in the function definition

the way to require a function to accept inputs is to put named variables inside the parentheses in your function definition

by requiring inputs by including them in your function definition, when you call the function, you will need to input values for each named variable in the function definition

failing to include arguments in a function call for a function that requires them results in an error

TypeError: return_city_sentence() takes exactly 2 arguments (0 given)

practice reading error messages!
unless using keywords when calling a function, order of arguments must match order of parameters; this is how python maps arguments to parameters

In functions.py, see 
receives one input and returns it
receives two inputs (phrase and city) and returns them as a sentence
calling function without including arguments required by function definition
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
