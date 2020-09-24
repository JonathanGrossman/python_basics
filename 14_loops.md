# Loops

# a loop is a block of code that executes itself repeatedly until a certain condition is met
# you can only loop over data that is “iterable” (i.e., comprised of more than one piece of data)
# strings, lists, tuples, sets, and dicts are iterable 
# integers, floats, and functions are not
# you can check whether a value is iterable

In loops.py, see comment:
# an example of an iterable object
# an example of a non-iterable object


# while loops execute the block of code so long as the condition set forth in the definition is True
# while loops are indefinite, meaning that the number of times it will run the block of code is not explicitly stated in the loop definition (though can be deduced if you know enough information)
In loops.py, see comments:
# examples of a while loops


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

