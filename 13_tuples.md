# Tuples

# a tuple is an immutable ordered collection of objects
# tuples are defined by using parenthesis (instead of square brackets)
# aside from being immutable, tuples are identical to lists and you can do all the same things regarding indexing, slicing, and nesting
# trying to add or remove a value to a tuple will result in an error
TypeError: 'tuple' object does not support item assignment
In lists.py, see comments:
# examples of tuples

# reasons for using a tuple instead of a list include:
# for large collections of objects, your program will execute faster using a tuple instead of a list
# using a tuple prevent the application from modifying the collection, whether on purpose or accident
# dictionaries (which we learn later) require a value that is immutable; accordingly, tuples are a good use for this
