# Lists

# a list is an ordered collection of objects denoted by square brackets and commas separating the objects
# to a list you can add and remove items, plus you can sort and manipulate the list in other ways
# the order in which you specify the elements in a list is a characteristic of the list that is stored in memory
# lists that have the same elements but in a different order are not equal to one another 
In lists.py, see comments:
# examples of lists order matters


# a single list can contain one or more types of Python object
# for instance, one list can contain a number, string, function, and built-in method
# a list can contain as many elements as the memory allows
# a value in a list can repeat itself (uniqueness not required)
In lists.py, see comments:
# examples of lists arbitrary objects


# like strings, lists allow for accessing elements by index and are iterable
# lists use zero-based indexing, meaning the first item in the list has an index position of zero
# lists can be sliced using positive and negative index values
In lists.py, see comments:
# examples of lists indexing
# slicing a list by index and negative index
# slicing a list using a stride
# slicing a list without specifying a start or end
# slicing a list to reverse it


# you can use in and not in to determine whether a list contains a value
# you can concatenate (+) and replicate (*) lists
# you can use built-in functions to get the length, min, and max
# you can nest lists inside one another
In lists.py, see comments:
# examples of lists using in and not in
# examples of list concatenation and replication
# examples of list common functions
# examples of lists nesting


# lists are mutable, meaning you can add elements, delete elements, and move them around
# lists are dynamic, meaning that grow and shrink as modified
# Python has many built-in methods that modify lists (e.g., .append(), .extend(), .insert(), .remove(), .pop())
In lists.py, see comments:
# modify single list value
# modify multiple list values
# methods that modify lists


 Method
What it does
.append()
adds one item to end of list
.extend()
adds one or more items from one list to end of other list
.insert()
adds one item to list in specified index position
.clear()
removes all items from list
.pop()
removes one item from list in specified index position; 
removes last item if no position specified
can save the removed item in a variable
.remove()
removes first item from list that is of the specified value 
throws error if not in list
does not return removed item (can’t save it in variable)


 Method
What it does
.index()
returns the index of the specified value
can specify index followed by starting index position
.count()
returns number of times specified value appears in list
.reverse()
reverses elements of list (does not create new list)
.sort()
sorts items in list (default is ascending order, does not create new list) 
.join()
converts lists to string (separates elements with what is to the left of method)
