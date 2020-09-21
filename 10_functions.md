# Functions

what: block of code that performs one or more tasks; this block of code can accept one or more inputs and return one or more outputs
what: in the code, a function needs a definition, which is the step-by-step “blueprint” for performing the tasks
what: in the code, after defining a function, for it to perform the tasks within the function, we need to call the function
note: defining a function in your code but not calling it is analogous to planning how to build a home but not actually ever building the home

self-defined functions: ones that we write the “blueprint” for in our own code
built-in functions: functions that come with whatever third-party software or packages that we are using in our applications
methods: functions that belong to classes/objects; we will discuss classes and objects later; for now, just know that methods are functions that belong to a specific block of code
note: the point is that functions come in a variety of contexts but that they all have in common that they perform tasks; the differences between them are more subtle and will be revealed as we continue . . .

why: avoid repetition -- allows developers a powerful way to write reusable code
DRY: Don’t Repeat Yourself
why: easier to maintain your code base
why: cleaner and more organized code
why: generalize or “abstract away” your code that you can use it in other applications

how: the basic syntax for defining a function (the “blueprint”)

def my_custom_function(#optional inputs):
   code to perform tasks
   optional return

how: the basic syntax for calling a function

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

at the top of each function use three sets of quotes to write a brief message about what the function does; 

then use __doc__ to retrieve the message; this is good for communicating with other developers and yourself



In functions.py, see 
example using triple quotes and __doc__


try on Python’s built-in functions!
