# Lists

A list is an ordered collection of objects denoted by square brackets and commas separating the objects `pants_list = ['jeans', 'khakis', 'athletic']`. A list can contain a variety of object types. For instance, one list can have numbers, strings, objects, and even other lists. A list can contain as many items as the memory allows and uniquesness is not required (a value in a list can repeat itself). 

```python
# examples of lists order matters
```



```python
# examples of lists arbitrary objects

# example of nesting lists inside one another

```

You can work with lists in many ways. Some of those ways are discussed in this chapter.

# insert list of h2 headings

A list is a Python object and has many attributes that belong to it, many of which are methods that allow you to work with lists in powerful ways. You will read about some in this chapter. To see the attributes available for lists, `print(dir([]))`.

```python
# printing list attributes
print(dir([]))

>>> '['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']'
```

## [Compare lists](#compare-lists)

The order in which you specify the elements in a list is a characteristic of the list that is stored in memory. Lists that have the same elements but in a different order are not equal to one another 

```python
# examples of comparing lists
```

## [Get length of list](#get-length-of-list)

you can use built-in functions to get the length, min, and max

## [Combine lists using list concatenation](#combine-lists-using-list-concatenation)

you can concatenate (`+`) and replicate (`*`) lists

```python
# examples of list concatenation and replication
```

## [Access list item using index position](#access-list-item-using-index-position)

Like strings, you access elements in a list using index position. Also like strings,  lists use zero-based indexing. The first item in the list has an index position of zero.

```python
# examples of lists indexing
```

## [Check for item in list](#check-for-item-in-list)

you can use in and not in to determine whether a list contains a value

```python
# examples of lists using in and not in
```

## [Access range of list items using slice](#access-range-of-list-items-using-slice)

slicing a list by index and negative index
slicing a list using a stride
slicing a list without specifying a start or end
slicing a list to reverse it

lists can be sliced using positive and negative index values

## [Lists are mutable and dynamic](#lists-are-mutable-and-dynamic)

Lists are mutable, meaning you can add elements, delete elements, and move them around.

```python
# examples of mutable lists
```

Lists are dynamic, meaning that grow and shrink as modified.

```python
# examples of dynamic lists
```

## [Examples of list methods](#examples-of-list-methods)

# examples of list common functions
Python has many built-in methods that modify lists (e.g., .append(), .extend(), .insert(), .remove(), .pop()).

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
