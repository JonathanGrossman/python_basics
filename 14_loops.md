# Loops

A loop is a block of code that executes itself repeatedly until a certain condition is met. You will work with `for` loops and `while` loops. A `for` loop executes a block of code a definite number of times. Usually, your `for` loops cycle through an array, string or other iterable, so the number of times it runs the code depends on the length of the object you're iterating through. A `while` loop executes a block of code an indefinite number of times until a predefined condition is met.

You can only loop over data that is "iterable". Something is iterable if it is made up of a sequence of data. Strings, lists, tuples, sets, and dictionaries are iterable. Integers, floats, and functions are not.

You can check whether a value is iterable using Python's built-in `iter()` function. This function converts a Python object into an iterable collection. The Python object, however, must be a sequence or else have its own iterator. Review the docstring with `print(iter.__doc__)`. For now, ignore the discussion in the docstring about callable and sentinel.


```python
iter(collection) -> iterator
iter(callable, sentinel) -> iterator

Get an iterator from an object.  In the first form, the argument must
supply its own iterator, or be a sequence.
In the second form, the callable is called until it returns the sentinel.
```

One way to check whether a Python object is a sequence is to pass it in as an argument when calling `iter()`. If the object is a sequence, the terminal should print the iterator, which looks something like `<iterator object at 0x10bb0db90>`. If the object is not a sequence, the terminal returns an error.


```python
# define variables
some_string = "We sell pants and shirts."
some_number = 12

# an example of an iterable object
some_string_iterator = iter(some_string)
print(some_string_iterator)

>>> '<iterator object at 0x10bb0db90>'

# an example of a non-iterable object
# some_number_iterator = iter(some_number)  

>>> 'TypeError: 'int' object is not iterable'
```

In the example above, `some_string` is a variable that has a string for its value and `some_number` is a variable the has an interger as its value. Using the `iter()` function to check whether `some_string` is a sequence (`iter(some_string)`) results in the terminal printing the iterator for the `some_string` object `<iterator object at 0x10bb0db90>`. In contrast, Using the `iter()` function to check whether `some_number` is a sequence (`iter(some_number)`) results in the terminal printing an error message `TypeError: 'int' object is not iterable`.

## [While loops](#while-loops)

A `while` loop executes a block of code so long as the condition set forth in the definition is `True`. `while` loops are indefinite, meaning that the number of times it will run the block of code is not explicitly stated in the loop definition (though can be deduced if you know enough information). 

A `while` loop is easy to write. It consists of the word `while` followed by the condition and a colon `:`. On the following line, you need to indent the block of code that you want to run so long as the condition is `True.` 

Many ways of working with `while` loops exist. A few examples will help show the possibilities. 

One way to work with `while` loops is to run a block of code using a counter. So long as the counter is above or below a certain number, run the block of code and change the counter's value after each loop.

```python
# define variable to use as counter
counter = 5

# while loop using counter in condition
while counter > 0:
    print(counter)
    counter -= 1
    
>>> 5
>>> 4
>>> 3
>>> 2
>>> 1
```

The example above defines a variable called `counter` and sets it equal to the integer `5`. You then define a `while` loop that checks whether `counter` is greater than the integer `0`. If so, then the `while` loop prints `counter` and then subtracts `1` from `counter`. The output is `5`, `4`, `3`, `2`, `1`. The terminal stops printing at `1` because the condition in the loop is to stop when `counter` is no longer greater than `0`.

Another way to work with `while` loops is to run a block of code on each item in an iterable (e.g., string, list, etc.) and then remove that item from the iterable so long as the iterable has items in it.

```python
the_list = ['pants', 'shirts', 'hats']

while the_list:
    print(the_list[0])
    the_list.pop(0)

>>> pants
>>> shirts
>>> hats
```

The example above defines a varaible named `the_list`. It is set equal to a list containing three items `['pants', 'shirts', 'hats']`. Then you define a `while` loop that runs so long as `the_list` has an item in it (in other words, it's truthy). If `the_list` does not have items in it, `the_list` is falsy and therefore the `while` loop won't run the code. The `while` loop prints `the_list` item at index position zero `the_list[0]` and the removes that item from the list `the_list.pop(0)`. 

By removing the item from the list, all the items shift one index position lower. For instance, after the first time through the loop, the item in index position `0` is gone, the item in index position `1` moves to `0` and the item in index position `2` moves to `1` so that the list looks like `['shirts', 'hats']`. After the second time through the loop, the item in index position `0` is gone and the item in index position `1` moves to `0` so that the list looks like `['hats']`. After the third time through the loop, the list no longer has any items and looks like `[]`, so the `while` loop stops. It doesn't print anything. That's because an empty list is falsy and a while loop stops when the condition is no longer truthy (or `True`).




# like while loops, for loops execute the block of code based on a conditions set for in the loop definition
# in contrast to while loops, for loops are definite, meaning that the number of times it will run the block of code is explicitly stated in the loop definition
In loops.py, see comments:
# examples of for loops


# you can use Python’s built-in range function in a for loop to cycle through a sequence of numbers
# the range function takes three integers as arguments -- the first argument represents the starting position; the second argument represents the end position (but is not itself included); the third argument represents the step (i,e., whether to count up or down and by how much to increment after each loop)
# if you provide the range function only one argument, it will treat it as the end position and default the starting position at zero
In loops.py, see comments:
# examples of for loops with range


# break and continue are controlled ways to terminate a loop
# break immediately ends a loop such that your program will move to the code that comes after the loop body
# in contrast, continue immediately terminates only the current iteration (not the loop entirely) such that the loop’s controlling expression is re-evaluated to see if the loop will run again
# you can conditionally terminate loops using these keywords
In loops.py, see:
# examples of break and continue


# beware of infinite loops (those that have no termination condition or an impossible termination condition); use command / (on a Mac) or control / (on Windows) to end infinite
# to learn more about Python loops:
https://realpython.com/python-while-loop/
https://realpython.com/python-for-loop/

