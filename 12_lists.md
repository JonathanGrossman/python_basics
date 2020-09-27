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

## [Get-list-length](#get-list-length)

You can get the length of a list, which tells you how many items are in the list.

You can get the length of a list, which tells you how many items are in the list. A list can be empty `[]` or have one or more items. Regardless, you can get its length using Python's built-in `len()` function. By printing `len.__doc__`, you can see in the terminal the description of this function

```python
# print string message for len() built-in function
print(len.__doc__)

>>> 'Return the number of items in a container.'
```

Same as what you saw in the strings chapter. The `len()` function returns the number of items in a container. The container is the list. The number of items is the number of items in the list. The `len()` function accepts one argument and returns an integer.

```python
# define variable
inventory_list = ['pants', 'shirts', 'hats']

# print length of list
print(len(inventory_list))

>>> 3
```

The example above prints the length of `inventory_list`, which is `3`. As explained in the strings chapter, the type returned by `len()` is an integer `<class 'int'>` and `len()` takes exactly one argument.

Use `len()` with other code to help dictate flow. For instance, here is an example of using `len()` in an `if / elif / else` block.

```python
# define variables
inventory_one = ['we', 'have', 'female', 'pants', 'in', 'our', 'store']
inventory_two = ['pants']
inventory_three = ['we', 'have', 'pants']


# define function that checks list length
def check_length(input):
    if len(input) > 5:
        print('Too long.')
    elif len(input) < 3: 
        print('Too short.')
    else:
        print('Nice.')


# call functions once for each variable as argument
check_string(inventory_one)
check_string(inventory_two)
check_string(inventory_three)

>>> 'Too long.'
>>> 'Too short.'
>>> 'Nice.'
```

The example above defines three variables `inventory_one`, `inventory_two`, and `inventory_three`. It then defines a function `check_length` that has one parameter `input`. The function checks the length of `input`. If greater than `5` the function prints `'Too long.'` If less than `3`, it prints `'Too short.'`. Otherwise, it prints `'Nice.'` You call the function three times, each time with one of the three variables in the order of `inventory_one`, `inventory_two`, and `inventory_three`. The outcome in the terminal is `'Too long.'`, `'Too short.'`, and `'Nice.'`

## [Get list min and max](#get-list-min-and-max)

You can get the minimum and maximum values of a list. Use Python's built-in functions `min()` and `max()` methods. The `min()` method returns the smallest item in the list. The `max()` method returns the largest item in the list. When using `min()` and `max()`, you need to compare values of the same type or else you get an error. The smallest string appear earliest in the alphabet and the largest appears latest in the alphabet.

```python
# example min and max on list of strings
alpha_list = ['A', 'C', 'B', 'E', 'D']
print(min(alpha_list))
print(max(alpha_list))

>>> A
>>> E

# example min and max on list of numbers
number_list = [1, 3, 2, 5, 4, 6, 7, 9, 8]
print(min(number_list))
print(max(number_list))

>>> 1
>>> 9

# example min and max on mixed list
mixed_list = [1, 3, 2, 5, 4, 6, 7, 9, 8, 'A', 'C', 'B', 'E', 'D']
print(min(mixed_list))
print(max(mixed_list))

>>> 'TypeError: '<' not supported between instances of 'str' and 'int''
```

The examples above each declare a list and print the `min()` and `max()` of the list. The first is a list of strings `['A', 'C', 'B', 'E', 'D']`. The `min()` is `'A'` because it appears earliest in the alphabet (the smallest) and the `max()` is `'E'` because it appears latest (the largest).

The second example is a list of integers `number_list = [1, 3, 2, 5, 4, 6, 7, 9, 8]`. The `min()` is `1` because it is the smallest and the `max()` is `9` because it is the largest.

The third exmple is a list of integers and strings. It returns an error `'TypeError: '<' not supported between instances of 'str' and 'int''`. The `min()` and `max()` methods cannot operate on mixed lists.

Print the docstring `__doc__` attribute for `min()` and `max()` to learn more.

```python
# print min docstring
print(min.__doc__)


>>> 'min(iterable, *[, default=obj, key=func]) -> value'
>>> 'min(arg1, arg2, *args, *[, key=func]) -> value'
>>> 
>>> 'With a single iterable argument, return its smallest item. The'
>>> 'default keyword-only argument specifies an object to return if'
>>> 'the provided iterable is empty.'
>>> 'With two or more arguments, return the smallest argument.'


# print max docstring
print(max.__doc__)


>>> 'max(iterable, *[, default=obj, key=func]) -> value'
>>> 'max(arg1, arg2, *args, *[, key=func]) -> value'
>>> 
>>> 'With a single iterable argument, return its biggest item. The'
>>> 'default keyword-only argument specifies an object to return if'
>>> 'the provided iterable is empty.'
>>> 'With two or more arguments, return the largest argument.'
```

## [Compare lists](#compare-lists)

You can compare lists to see if they are equal `==` to one another. When you compare the equality of two lists, you are comparing whether they have the same items listed in the same order. In contrast, you can compare lists to see whether they contain the same items regardless of their order. 

Check whether two lists are equal using the equal to operator `==`. The `==` operator checks whether two lists have the same items in the same order. The order in which you specify the elements in a list is a characteristic of the list that is stored in memory. Lists that have the same elements in the same order are equal to one another. Lists that have the same elements but in a different order are not equal to one another.

```python
# examples of comparing lists
list_one = ['we', 'sell', 'pants', 'and', 'shirts']
list_one_copy = ['we', 'sell', 'pants', 'and', 'shirts']
list_two = ['sell', 'we', 'pants', 'shirts', 'and']
list_three = ['shirts', 'and', 'pants', 'we', 'sell']

print(list_one == list_one_copy)
print(list_one == list_two)
print(list_two == list_three)

>>> True
>>> False
>>> False
```

The example above defines four variables all of which are set equal to lists containing identical values. Two of the lists have the items listed in the same order `list_one` and `list_one_copy`. The other two lists have the items ordered in a unique way `list_two` and `list_three`. Comparing `list_one` to `list_one_copy` using the equal to operator `==` returns `True`. Comparing `list_one` to each of `list_two` and `list_three` using the equal to operator `==` returns `False`. Although `list_one` has the same items as `list_two` and `list_three`, the items are listed in a different order.

Check whether two lists have the same items regardless of the order they are listed. Although two lists may not be equal to one another, the still may have all the same items. You may want to check for that. Multiple ways may exist for this. One way is to first check the length of each list. Only ff the lengths are equal, then sort each list using Python's `sorted()` method and compare the sorted lists. 

```python
# find whether two lists contain same items even if in different order
list_one = ['we', 'sell', 'pants', 'and', 'shirts']
list_two = ['sell', 'we', 'pants', 'shirts', 'and']

if list_one != list_two:
    print(len(list_one) == len(list_two) and sorted(list_one) == sorted(list_two))

>>> True
```

In the example above, the variables `list_one` and `list_two` have the same items listed in a different order. You first check whether `list_one` is not equal to `list_two`. If that's `True`, you compare the length of the two lists. 

By comparing the length of those two lists, you can quickly determine whether they might be the same `len(list_one) == len(list_two)`. If they have different lengths, then they can't have the same items listed in a different order and you don't have to run the more resource-intensive `sorted()` method. If the lists have the same length, it's possible they have the same items but in a different order (you know they're not in the same order because `list_one != list_two`). 

To check the `sorted` lists only if the list lengths are equal, chain the length comparison expression to the sorted list comparison expression using `and`-- `len(list_one) == len(list_two) and sorted(list_one) == sorted(list_two)`. If the length comparison is `False` (they don't have the same number of items), then the Python interpreter doesn't read the expression after the `and` because both expressions are not `True`. If the length comparison is `True` then Python reads the `and` part of the expression. 

If the lists have the same length, by comparing equality for the `sorted` lists, you know whether they have the same items and now in the same order `sorted(list_one) == sorted(list_two)`. Here it's `True`.

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

## [Mutate and modify lists](#mutate-and-modify-lists)

Lists are mutable, meaning you can add elements, delete elements, and move them around.

```python
# examples of mutable lists
```

Lists are dynamic, meaning that grow and shrink as modified.

```python
# examples of dynamic lists
```

## [Use list methods](#use-list-methods)

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
