# Loops

A loop is a block of code that executes itself repeatedly until a certain condition is met. You will work with `while` loops and `for` loops. A `while` loop executes a block of code an indefinite number of times until a predefined condition is met. A `for` loop executes a block of code a definite number of times. Usually, your `for` loops cycle through an array, string or other iterable, so the number of times it runs the code depends on the length of the object you're iterating through.

## [While loops](#while-loops)

A `while` loop executes a block of code so long as the condition set forth in the definition is `True`. `while` loops are indefinite, meaning that the number of times it will run the block of code is not explicitly stated in the loop definition (though can be deduced if you know enough information). 

A `while` loop consists of the word `while` followed by the condition and a colon `:`. On the following line, you need to indent the block of code that you want to run so long as the condition is `True.` 

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


## [For loops](#for-loops)

Like `while` loops, `for` loops execute a block of code repeatedly so long as a condition set for in the loop definition is `True`. In contrast to `while` loops, `for` loops are definite, meaning that the number of times it will run the block of code is explicitly stated in the loop definition.

A `for` loop consists of several parts. The first line of a `for` loop starts with the word `for` followed by a variable for the current item in the iteration (you can name this whatever you want), followed by the word `in`, followed by the name of the iterable, and ending with colon `:`. On the following line, you need to indent the block of code that you want to run each time the loop iterates through the iterable.

```python
# define variable
message = 'We sell pants'

# example of for loops with string
for i in message:
    print(i)

>>> 'W'
>>> 'e'
>>> 
>>> 's'
>>> 'e'
>>> 'l'
>>> 'l'
>>>  
>>> 'p'
>>> 'a'
>>> 'n'
>>> 't'
>>> 's'
```

The example above defines a variable named `message` and sets it equal to a string `'We sell pants'`. Then you loop through `message`. The controlling statement in the `for` loops names the variable that represents each character `i`. Each time you loop through `message`, you print a character in the string `print(i)`. Because the `for` loop proceeds from left to right, it prints `'We sell pants'` one letter at a time from the `W` at index position `0` to the `s` in `pants` in the last index position.

```python
# define variable
inventory_list = ['pants', 'shirts', 'hats']

# example of for loops with list
for item in inventory_list:
    print(item)

>>> 'pants'
>>> 'shirts'
>>> 'hats'
```

The example above is the same as before except instead of defining a string variable, it defines a variable named `inventory_list` and sets it equal to a list `['pants', 'shirts', 'hats']`. Then you loop through `inventory_list`. The controlling statement in the `for` loops names the variable that represents each list item `item`. Each time you loop through `inventory_list`, you print a an item from `inventory_list`. Because the `for` loop proceeds from left to right, it prints one item at a time from index position `0`, which is `'pants'`, to the last index position, which is `hats`.


When working with `for` loops, you oftentimes need to know whether what you are looping through is iterable because the controlling expression is looking for whether someting is `in` something else. An object is iterable if it is made up of a sequence of data. Strings, lists, tuples, sets, and dictionaries are iterable. Integers, floats, and functions are not.

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


## [Range function](#range-function)

Although you can't iterate through a number itself, you can iterate through a range of numbers using Python's built-in `range()` function. That function sequentially iterates through a range of numbers. You can use `range()` to progress sequentially through a range of numbers. Print the docstring to learn more `print(range.__doc__)`. 

```python
range(stop) -> list of integers
range(start, stop[, step]) -> list of integers

Return a list containing an arithmetic progression of integers.
range(i, j) returns [i, i+1, i+2, ..., j-1]; start (!) defaults to 0.
When step is given, it specifies the increment (or decrement).
For example, range(4) returns [0, 1, 2, 3].  The end point is omitted!
These are exactly the valid indices for a list of 4 elements.
```

Use Python’s built-in range function in a for loop to cycle through a sequence of numbers. The range function takes three integers as arguments. The first argument represents the starting position of the range. The second argument represents the ending position (but is not itself included). The third argument represents the step (i.e., whether to count up or down and by how much to increment after each loop). If you provide the range function only one argument, it will treat it as the ending position and default the starting position at zero. 


Although `range()` returns a list of integers that it cycles through, you won't use that feature in a `for` loop.

```python
# example using range
for item in range(1, 5):
    print(item * 3)
    
>>> 3
>>> 6
>>> 9
>>> 12
```

The example above is a `for` loop using the `range()` function with a starting value of `1` and ending value of `5` and a default stepper of `1`. Therefore, it cycles through the numbers `1`, `2`, `3`, `4`. Each time the `for` loop cycles through the range, it prints the current number times three `print(item * 3)`. The output therefore is `3`, `6`, `9`, `12`.

If you want to skip over items in the range, declare a stepper having a integer value greater than `1`.

```python
# example using range with stepper
for item in range(1, 9, 3):
    print(item)
    
>>> 1
>>> 4
>>> 7
```

The example above is a `for` loop using the `range()` function with a starting value of `1`, an ending value of `9` and a stepper of `3`. Therefore, the range of numbers is `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8` but the function will only operate on every third number in the range. 

Each time the `for` loop cycles through the range, it prints the current number `print(item)`. In the first cycle through the loop, the `for` loop starts with number `1`. It prints the number `1`. That's the end of the first cycle. Then the loop skips three numbers in the range to `4` because the stepper is `3`. It prints the number `4`. That's the end of the second cycle. Then the loop skips three numbers in the range to `7` because the stepper is `3`. That's the end of the thir cycle. There is no fourth cycle because skipping ahead `3` from `7` takes you to `10`, which is outside of the range `1 - 9`. The output therefore is `1`, `4`, `7`.

You can use the `range()` function to count backwards. To do so, your starting integer should be greater in value than your ending integer, and you need to use a stepper having a negative integer value.

```python
# example using range with negative stepper to count down
for item in range(9, 1, -1):
    print(item)
    
>>> 9
>>> 8
>>> 7
>>> 6
>>> 5
>>> 4
>>> 3
>>> 2
```

The example above is a `for` loop using the `range()` function to count down within a range. Its starting value is `9`, ending value is `1`, and the stepper is `-1`. Therefore, the range of numbers is `9`, `8`, `7`, `6`, `5`, `4`, `3`, `2`. Each time the `for` loop cycles through the range, it prints the current number `print(item)`. Because the stepper is `-1`, the `range()` function subtracts one from the current number at the end of each cycle so that the function counts down by `1` from `9` . The output therefore is `9`, `8`, `7`, `6`, `5`, `4`, `3`, `2`.

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

