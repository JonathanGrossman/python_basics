# Lists

A list is an ordered collection of objects denoted by square brackets and commas separating the objects `pants_list = ['jeans', 'khakis', 'athletic']`. A list can contain a variety of object types. For instance, one list can have numbers, strings, objects, and even other lists. A list can contain as many items as the memory allows and uniquesness is not required (a value in a list can repeat itself). 

```python
# examples of lists arbitrary objects
def my_function():
    print("My function")

arbitrary_list = [10, "Welcome", my_function, 10, "Welcome"]
print(arbitrary_list)

>>> '[10, 'Welcome', <function my_function at 0x10c1638c0>, 10, 'Welcome']'

# example of nesting lists inside one another
nested_sample_list = ["First", "Second", "Third", "Fourth", "Last", ["Nested First", "Nested Second", "Nested Third", "Nested Fourth", "Nested Last"]]
print(nested_sample_list)

>>> '['First', 'Second', 'Third', 'Fourth', 'Last', ['Nested First', 'Nested Second', 'Nested Third', 'Nested Fourth', 'Nested Last']]'
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
check_length(inventory_one)
check_length(inventory_two)
check_length(inventory_three)

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

## [Combine lists concatenation and replication](#combine-lists-concatenation-and-replication)

You can concatenate `+` and replicate `*` lists. Combine multiple lists, whether the same list or different lists, using list concatenation `+`. Combine the same list to itself using replication `*`. 

List concatentation is combining lists using the `+` operator. For instance, declare three variables and set each equal to a list. Create a fourth variable whose value is equal to the sum of the first three variables.

```python
# examples of list concatenation
intro_list = ['we', 'sell']
pants_list = ['jeans', 'khakis', 'athletic pants']
shirts_list = ['casual shirts', 'dress shirts']

message_list = intro_list + pants_list + shirts_list
print(message_list)

>>> '['we', 'sell', 'jeans', 'khakis', 'athletic pants', 'casual shirts', 'dress shirts']'
```

The example above defines three variables `intro_list`, `pants_list`, and `shirts_list` and sets them each equal to lists of different values. The fourth variable `message_list` is the sum of the first three variables `message_list = intro_list + pants_list + shirts_list`. The result of the list concatentation is `'['we', 'sell', 'jeans', 'khakis', 'athletic pants', 'casual shirts', 'dress shirts']'`.

List concatenation works only when combining two or more lists. It does not work when trying to add a list to some other data type.

```python
# example of list list concatenation error
intro_list = ['we', 'sell']
pants_list = ['jeans', 'khakis', 'athletic pants']
shirts_list = ['casual shirts', 'dress shirts']

message_list = intro_list + pants_list + shirts_list + 3
print(message_list)

>>> 'TypeError: can only concatenate list (not "int") to list'
```
The example above is the same as the one before it, except it adds the integer `3` in the list concatenation `message_list = intro_list + pants_list + shirts_list + 3`. You get an error `TypeError: can only concatenate list (not "int") to list`. You can't add a list to a non-list.

List replication is replicating a list by multplying it by an integer using the `*` operator. For instance, declare a variable and set it equal to a list. Multiply the variable by the integer `5`. It returns a new list with the values from the original list appearing five times in the new list.

```python
# example of list replication
pants_list = ['jeans', 'khakis', 'athletic pants']

print(pants_list * 3)

>>> '['jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants']'
```

The above example defines the variable `pants_list` and sets it equal to a list with three items `['jeans', 'khakis', 'athletic pants']`. Multiplying `pants_list` by the integer `3` returns a new list with the items from the original list appearing three times each.

If you multiply the list by a non-integer, you get an error.

```python
# example of list replication error
pants_list = ['jeans', 'khakis', 'athletic pants']

print(pants_list * pants_list)

>>> 'TypeError: can't multiply sequence by non-int of type 'list''
```

The above example is the same as the one before it, except this one multiplies `pant_list` by `pant_list`. You get an error `TypeError: can't multiply sequence by non-int of type 'list'` because you can't multiply a list by a non-integer, and `pant_list` is a list, not an integer.

## [Access list item using index position](#access-list-item-using-index-position)

Access a specific item in a list using its index position. Every item in a list has a positive index position. From left to right, the first index position is `0` and the last index position is the list length minus one `len(a) - 1`. 

Every item in a list also has a negative index position. Negative indexing allows you to access items using the end of the list as the reference point. From right to left, the last item in the list has a negative index position of `-1` and moving left the index decreases by `1` (e.g., `-2`, `-3`, `-4`,  . . .). 

To use the index position, first save the list to a variable. Then append to the variable square brackets wrapping the index position of the item you want to access `pants_male[1]`.

```python
# example of using index position with string
pants_list = ['jeans', 'khakis', 'athletic pants']

print(pants_list[1])
print(pants_list[-3])

>>> 'khakis'
>>> 'jeans'
```

In the example above, you declare a variable named `pants_list` and set it equal to a list `['jeans', 'khakis', 'athletic pants']`. Then you print the item in index position `1` in the line `print(pants_list[1])`. The item with an index position of `1` in `pants_list` is `'khakis'`. You also print the item in index position `-3` in the line `print(pants_list[-3])`. The item with an index position of `-3` in `pants_list` list is `'jeans'`.

Here is a list of the index positions for each character.

```python
Character           Index           Negative Index

'jeans'                 0             -3           
'khakis'                1             -2
'athletic pants'        2             -1
```

Trying to print an index position that doesn't exist results in an error. 

```python
# define variable
pants_list = ['jeans', 'khakis', 'athletic pants']

# try to print index position out of range
print(pants_list[10])

>>> 'IndexError: list index out of range'
```

The example above defines the same `pants_list` variable as before having a list as its value `['jeans', 'khakis', 'athletic pants']`. The list has a length of `3`, which means its items occupy index position `0`, `1`, and `2`. After defining the variable, you print the `pants_list` item in index position `10`. You get an error `IndexError: list index out of range` because `pants_list` doesn't have an index position `10`.


## [Check for item in list](#check-for-item-in-list)

Check whether an item is in a list using the `in` and `not in` operators. Expressions using `in` and `not in` return a Boolean `True` or `False`. Using `in`, if an item is in the list, the expression returns `True`. If the item is not in the list, the expression returns `False`. Using `not in`, if an item is in the list, the expression returns `False`. If the item is not in the list, the expression returns `True`.

```python
# examples of lists using in and not in
pants_list = ['jeans', 'khakis', 'athletic pants']

print('jeans' in pants_list)
print('jeans' not in pants_list)
print('shirt' in pants_list)

>>> True
>>> False
>>> False
```

The example above defines the same `pants_list` variable as in the other examples set equal to the list `['jeans', 'khakis', 'athletic pants']`. You then print the outcome of three expressions. The first checks whether `'jeans'` is `in` the `pants_list`. It returns `True`. The second checks whether `'jeans'` is `not in` the `pants_list`. It returns `False`. The third checks whether `'shirt'` is `in` the `pants_list`. It returns `False`.

Use the `in` and `not in` operators in combination with functions and `if / elif /else` blocks to control the flow.

```python
# define variables
pants_list = ['jeans', 'khakis', 'athletic pants']

# check if item is in the list
def check_item(input):
    if input in pants_list:
        return input + ' ' + 'is in the pants list'
    else:
        return 'The pants list does not contain' + ' ' + input


print(check_item('jeans'))
print(check_item('shirt'))

>>> 'jeans is in the pants list'
>>> 'The pants list does not contain shirt'
```

The exmple above defines the `pants_list` variable equal to `['jeans', 'khakis', 'athletic pants']`. Then you define a variable named `check_item`. It has one parameter named `input`. The function checks if `input` is `in` the `pants_list`. If so, it returns a message saying the input is in the pants list. If not, it returns a message saying the pants list does not contain the input. Here you call the function twice, first with `'jeans'` as the input and then with `'shirt'`. The terminal prints first `'jeans is in the pants list'` and then `'The pants list does not contain shirt'`.

## [Access range of list items using slice](#access-range-of-list-items-using-slice)

Slicing allows you to access a range of items in a list using index positions. To slice a variable named `pants_list` having a value of `['jeans', 'khakis', 'athletic pants']`, you declare the starting and ending values of the range you want to access. You declare the starting and ending values at the end of the list within square brackets `[]` separated by a colon `:`, with the ending value being not included. So choose a number one more than what you want included. 

You also can specify the stepper, which is the value by which the slicing increments within in your range. The default value for the stepper is `1` (every item within the range). Declare it using a colon `:` after the ending number and then the stepper.

```python
# define string
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']

# example of slicing
print(inventory_list[3:6])

>>> '['shirts', 'hats', 'jackets']'
```

The example above prints index positions `3 - 5` (`6` not included) of `inventory_list`, which corresponds to `['shirts', 'hats', 'jackets']`. No stepper declared. If, however, you declare a separator greater than `1`, then the output changes.

Negative slicing allows you to access items using the end of the list as the reference point. As mentioned above, each item in a list has a negative index position. The last item in the list is index position `-1` and as you move left across the list, the index position decreases by `1` (e.g., . . ., `-2`, `-3`, `-4`, `-5` . . . beginning of list).

```python
# define string
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']

# example of slicing
print(inventory_list[-7:-2])

>>> '['athletic pants', 'shirts', 'hats', 'jackets', 'gloves']'
```

The example above is the same as the one before it, except this one has a slicing range of index positions `-7` to `-2`. This time the output is `['athletic pants', 'shirts', 'hats', 'jackets', 'gloves']`. The item at index position `-7` is `'athletic pants'` and at index position `-3` is `'gloves'`. Remember the ending value of `-2` for slicing is not included, so the value at index position `-3` is the last value in the sliced list.

You can slice a list without declaring starting and ending position. If you want the slicing to start at the first item, don't declare a starting position. If you want the slicing to include the last item, don't declare an ending position. 

To omit the starting position, in the square brackets write a colon followed by the ending position `inventory_list[:5]`. To omit the ending position, in the square brackets write a colon followed by the ending position `inventory_list[3:]`.

```python
# define variable
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']


# slicing a list without specifying a start
print(inventory_list[:5])

>>> '['jeans', 'khakis', 'athletic pants', 'shirts', 'hats']'


# slicing a list without specifying an end
print(inventory_list[3:])

>>> '['shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']'
```

In the examples above, first you print from the beginning of the list to item `5` in the list `inventory_list[:5]`. This returns `['jeans', 'khakis', 'athletic pants', 'shirts', 'hats']`. Next you print from index position `3` until the end of the list `inventory_list[3:]`. This returns a different list `['shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']`. 

In addition to declaring a starting and ending position, you can also declare a stepper. A stepper the integer value that the slicing uses to increment through your list. For instance, a stepper value of `3` gets every third item in the range.

```python
# define variable
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']

# example of slicing
print(inventory_list[1:6:2])

>> '['khakis', 'shirts', 'jackets']'
```

The example above is the same as the one before it, except this one has a starting index position of `1`, and ending index position of `6`, and a stepper of `2` when slicing `inventory_list[1:6:2]`. This time the output is `['khakis', 'shirts', 'jackets']` because the stepper is `2`, so it skips every other character in the range of `1 - 6`.

Instead of declaring a positive stepper, you can declare a negative stepper. When you declare a negative stepper, the starting index position must be greater than the ending index position or else you receive an empty list.

```python
# define variable
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']


# example of slicing negative stepper wrong starting / ending order
print(inventory_list[1:6:-2])

>>> '[]'


# example of slicing negative stepper correct starting / ending order
print(inventory_list[6:1:-2])

>>> '['gloves', 'hats', 'athletic pants']'
```

In the examples above, the first one is the same as the one before it, except this one has a starting stepper of `-2`. It has a starting index position of `1`, an ending index position of `6`, and a stepper of `-2` when slicing `inventory_list[1:6:-2]`. This time the output is an empty list`[]` because the stepper counts down from `1` but the ending position is up at `6`.

The second example is the same as the first, except it swaps the starting and ending positions. It has a starting index position of `6`, an ending index position of `1`, and a stepper of `-2` when slicing `inventory_list[6:1:-2]`. This time the output is not an empty list `['gloves', 'hats', 'athletic pants']` because the stepper counts down from `6` to `1`.

To omit the ending position and also use a stepper, in the square brackets write a colon followed by the starting position, two colons, and the stepper value `inventory_list[3::2]`. To omit the starting position, you write it like normal.

```python
# define variable
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']


# slicing a list without specifying an end but with stepper
print(inventory_list[3::2])

>>> '['shirts', 'jackets', 'dresses']'
```

The example above defines a list `inventory_list` and prints from the list index position `3` until the end of the list every other item `inventory_list[3::2]`. This returns another different list `['shirts', 'jackets', 'dresses']`.

You can use slicing to reverse the order of a list. In the square brackets, declare only a stepper of `-1`. Don't include a starting or ending position.

```python

# define variable
inventory_list = ['jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts']

# example of reversing a list
print(inventory_list[::-1])

>>> '['skirts', 'dresses', 'gloves', 'jackets', 'hats', 'shirts', 'athletic pants', 'khakis', 'jeans']'
```

The example above reverses the order of the list by starting at the last item, ending at the first item, and counting backwards by 1 `inventory_list[::-1]`. This returns the list in reverse order `['skirts', 'dresses', 'gloves', 'jackets', 'hats', 'shirts', 'athletic pants', 'khakis', 'jeans']`.

## [Mutate and modify lists](#mutate-and-modify-lists)

Lists are mutable and dynamic, meaning you can add elements, delete elements, and move them around.

The `.append()` method appends an object to the end of a list. If you `print([].append.__doc__)`, the terminnal prints the docstring for `.append()`, and it is `Append object to the end of the list.`.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']


# appending item to a list
sample_list.append('Sixth')
print(sample_list)

>>> '['First', 'Second', 'Third', 'Fourth', 'Fifth', 'Sixth']'
```

The `.extend()` method appends mulitple objects to the end of a list. If you `print([].extend.__doc__)`, the terminnal prints the docstring for `.extend()`, and it is `Extend list by appending elements from the iterable.`.


```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# extend list with multiple items
sample_list.extend(['Sixth', 'Seventh'])
print(sample_list)

>>> ['First', 'Second', 'Third', 'Fourth', 'Fifth', 'Sixth', 'Seventh']
```

Use the `del` keyword to delete one or more items from a list. Use the `del` keyword with index positions to declare which item or items to delete. To delete a single item, specify only one index position.


```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# delete list value
del sample_list[2]
print(sample_list)
>>> ['First', 'Second', 'Fourth', 'Fifth']
```

To delete multiple consecutive items, specify a range of index positions.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# delete list value
del sample_list[1:4]
print(sample_list)

>>> '['First', 'Fifth']'
```

To clear the contents of a list, use the `.clear()` method. If you `print([].clear.__doc__)`, the terminnal prints the docstring for `.clear()`, and it is `Remove all items from list.`.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# clear a list
print(sample_list.clear())

>>> None
```

To modify a single item in a list, use the index position of the item and set the value equal to a new value.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# modify single list value
sample_list[2] = 3
print(sample_list)

>>> '['First', 'Second', 3, 'Fourth', 'Fifth']'
```

To modify multiple items in a list, use the index positions of the item and set the value equal to the new values.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# modify multiple list values
# replaces exact number of elements
sample_list[1:4] = (2, 3, 4)
print(sample_list)

>>> '['First', 2, 3, 4, 'Fifth']'
```

To replace and add multiple values, use the index positions of the item and set the value equal to the new values.


```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# replaces and adds more
sample_list[3:6] = [4, 5, 6, 7]
print(sample_list)

>>> '['First', 'Second', 'Third', 4, 5, 6, 7]'
```

To insert a list as an item, use the index position of an item in the list and set the value equal to a list. This is a similar but different syntax compared to adding multiple values to a list. Here, you specify a single index position to be replaced, and then set it equal to a list. In constrast, when adding multiple values, you declare a range of index positions to replace or add and then set it equal to a list with the same number of values as in the range of index positions.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']


# inserts a list
sample_list[1] = [2.1, 2.2, 2.3]
print(sample_list)

>>> '['First', [2.1, 2.2, 2.3], 'Third', 'Fourth', 'Fifth']'
```

To insert a list as individual elements in a specific location in the list, use a range of index positions that start and end at the same index position.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# inserts a list as individual elements
sample_list[1:1] = [2.1, 2.2, 2.3]
print(sample_list)

>>> '['First', 2.1, 2.2, 2.3, 'Second', 'Third', 'Fourth', 'Fifth']'
```

To remove an item from a list, use the `.pop()` instance method for lists. This method removes an item, and you can save that item to a variable so that it's saved in memory for use later in your script. Entering in your terminal `print([].pop.__doc__)` prints the docstring for `.pop()`, which is `Remove and return item at index (default last). Raises IndexError if list is empty or index is out of range.`

To remove the last item in a list, do not pass any argument into `.pop()`. The default is the item in the last index position.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# remove and save last item from list
removed_item = sample_list.pop()
print("removed item:", removed_item)
print("sample list:", sample_list)

>>> 'removed item: Fifth'
>>> 'sample list: ['First', 'Second', 'Third', 'Fourth']'
```

To remove something other than the last item in a list, pass as an argument into `.pop()` the index position of the item you want to remove. 

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# remove and save item at index 2 from list
removed_item = sample_list.pop(2)
print("removed item:", removed_item)
print("sample list:", sample_list)

>>> 'removed item: Third'
>>> 'sample list: ['First', 'Second', 'Fourth', 'Fifth']'
```

You can pass only one argument into `.pop()` or else it returns an error.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# remove and save item at index 2 from list
removed_item = sample_list.pop(2, 3)
print("removed item:", removed_item)
print("sample list:", sample_list)

>>> 'TypeError: pop() takes at most 1 argument (2 given)'
```

The argument you pass into `.pop()` must be an integer or else it returns an error.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# remove and save item at index 2 from list
removed_item = sample_list.pop([2, 3])
print("removed item:", removed_item)
print("sample list:", sample_list)

>>> 'TypeError: 'list' object cannot be interpreted as an integer'
```

To get the index position of an item in a list, use the `.index()` instance method for lists. Entering in your terminal `print([].index.__doc__)` prints the docstring for `.index()`, which is `Return first index of value. Raises ValueError if the value is not present.`

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_list.index("Second")
print(index_of_second)

>>> 1
```

The `.index()` instance method returns an error if the argument passed into `.index()` is not in the list.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_list.index("1")
print(index_of_second)

>>> 'ValueError: '1' is not in list'
```

The `.index()` instance method accepts one argument or else it returns an error.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_list.index("Second", "Third")
print(index_of_second)

>>> 'TypeError: slice indices must be integers or have an __index__ method'
```

To count the number of times a value appears in a list, use the `.count()` instance method for lists. Entering in your terminal `print([].count.__doc__)` prints the docstring for `.count()`, which is `Return number of occurrences of value.`

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of count
number_of_thirds = sample_list.count("Third")
print(number_of_thirds)
sample_list.append("Third")
number_of_thirds = sample_list.count("Third")
print(number_of_thirds)

>>> 1
>>> 2
```

The `.count()` instance method returns `0` if the argument passed into `.count()` is not in the list.


```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of count
number_of_thirds = sample_list.count("three")
print(number_of_thirds)
sample_list.append("three")
number_of_thirds = sample_list.count("three")
print(number_of_thirds)

>>> 0
>>> 1
```

The `.count()` instance method accepts one argument or else it returns an error.

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of count
number_of_thirds = sample_list.count("three", "four")
print(number_of_thirds)
>>> 'TypeError: count() takes exactly one argument (2 given)'
```

To reverse the order of items in a list, use the `.reverse()` instance method for lists. It takes `0` arguments. This does not create a new list. It changes the order of the list itself. Saving it to a variable does not work. Entering in your terminal `print([].reverse.__doc__)` prints the docstring for `.reverse()`, which is `Reverse *IN PLACE*.`

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of reverse
reversed_list = sample_list.reverse()
print("sample list:", sample_list)
print("reversed list:", reversed_list)

>>> 'sample list: ['Fifth', 'Fourth', 'Third', 'Second', 'First']'
>>> 'reversed list: None'

# reverse in place; saving to variable results in None for variable
sample_list.reverse(0)
print("sample list:", sample_list)

>>> 'TypeError: reverse() takes no arguments (1 given)'
```

To sort the order of items in a list, use the `.sort()` instance method for lists. It takes `0` positional arguments. It does, however, take the arguments `reverse` or `key`. Setting `reverse` to `True` sorts the list in reverse (descending) order. Otherwise, the list is sorted in ascending order. The `key` argument lets you set a value by which to sort by and is beyond the scope of this chapter. 

The `.sort()` method does not create a new list. Rather, it changes the order of the list itself. Saving it to a variable does not work. 

Entering in your terminal `print([].sort.__doc__)` prints the docstring for `.sort()`, which is `Stable sort *IN PLACE*.`

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of reverse
sample_list.sort()
print("sample list:", sample_list)

>>> 'sample list: ['Fifth', 'First', 'Fourth', 'Second', 'Third']'

# reverse sort
sample_list.sort(reverse=True)
print("reversed list:", sample_list)

>>> 'reversed list: ['Third', 'Second', 'Fourth', 'First', 'Fifth']'

# sorted in place; saving to variable results in None for variable
sorted_list = sample_list.sort()
print("sorted list:", sorted_list)

>>> 'sorted list: None'

# sort takes no positional arguments
sample_list.reverse(0)
print("sample list:", sample_list)

>>> 'TypeError: sort() takes no positional arguments'
```

To insert an item into a list, use the `.insert()` instance method for lists. It takes two arguments, an index position followed by the item. The item is inserted right before the index position. Entering in your terminal `print([].index.__doc__)` prints the docstring for `.index()`, which is `Insert object before index.`

```python
# define variable
sample_list = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

sample_list.insert(0, "Zero")
print(sample_list)

>>> '['Zero', 'First', 'Second', 'Third', 'Fourth', 'Fifth']'

# example takes two arguments
sample_list.insert(0)
print(sample_list)

>>> 'TypeError: insert() takes exactly 2 arguments (1 given)'
```


## [Use list methods](#use-list-methods)

Python has many built-in methods that modify lists (e.g., .append(), .extend(), .insert(), .remove(), .pop()). Here is a list of methods, their docstrings, and a few notes about each.

Method: `.append()`  
Docstring: Append object to the end of the list.  
What it does: Adds one item to end of the list.

Method: `.clear()`  
Docstring: Remove all items from list.  
What it does: Self-explanatory. Removes all items from list  

Method: `.copy()`  
Docstring: Return a shallow copy of the list.  
What it does: Copies the list into a new list containing the same values  

Method: `.count()`  
Docstring: Return number of occurrences of value.  
What it does: Returns number of times specified value appears in list  

Method: `.extend()`  
Docstring: Extend list by appending elements from the iterable.  
What it does: Adds one or more items from one list to end of other list  

Method: `.index()`  
Docstring: Return first index of value. Raises ValueError if the value is not present.  
What it does: Returns the index of the specified value; can specify index followed by starting index position

Method: `.insert()`  
Docstring: Insert object before index.  
What it does: Adds one item to list in specified index position  

Method: `.pop()`  
Docstring: Remove and return item at index (default last). Raises IndexError if list is empty or index is out of range.  
What it does: Removes one item from list in specified index position; removes last item if no position specified; can save the removed item in a variable  

Method: `.remove()`  
Docstring: Remove first occurrence of value. Raises ValueError if the value is not present.  
What it does: Removes first item from list that is of the specified value, throws error if not in list; does not return removed item (can’t save it in variable)  

Method: `.reverse()`  
Docstring: Reverse *IN PLACE*.  
What it does: Reverses elements of list (does not create new list)  

Method: `.sort()`  
Docstring: Stable sort *IN PLACE*.  
What it does: Sorts items in list (default is ascending order, does not create new list)  


