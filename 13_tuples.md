# Tuples

A tuple is an immutable ordered collection of objects denoted by parenthesis and commas separating the objects `pants_tuple = ('jeans', 'khakis', 'athletic')`. Aside from being immutable, tuples are identical to lists and you can do all the same things regarding indexing, slicing, and nesting. 

Oftentimes, it doesn't matter whether you use a tuple or a list. However, some situations may be better suited for a tuple. For large collections of objects, your program will execute faster using a tuple instead of a list. For data that you don't want modified, using a tuple prevents modifying the collection (it's immutable). For when you use a dictionary (which you learn about in an upcoming chapter), it requires a value that is immutable. Accordingly, tuples are a good use for this.

A tuple can contain a variety of object types. For instance, one tuple can have numbers, strings, objects, and even other tuples. A tuple can contain as many items as the memory allows and uniquesness is not required (a value in a tuple can repeat itself).

```python
# examples of tuples arbitrary objects
def my_function():
    print("My function")

arbitrary_list = (10, "Welcome", my_function, 10, "Welcome")
print(arbitrary_list)

# example of nesting tuples inside one another
nested_sample_list = ("First", "Second", "Third", "Fourth", "Last", ("Nested First", "Nested Second", "Nested Third", "Nested Fourth", "Nested Last"))
print(nested_sample_list)
```

You can work with tuples in many ways. Some of those ways are discussed in this chapter.

# insert list of h2 headings

A tuple is a Python object and has several attributes that belong to it. Although tuples doesn't have nearly as many methods as lists, tuples do have some methods that help you to work with tuples. You will read about some in this chapter. To see the attributes available for tuples, `print(dir(()))`.

```python
# printing list attributes
print(dir([]))

>>> '['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']'
```

## [Get tuple length](#get-tuple-length)

You can get the length of a tuple, which tells you how many items are in the tuple. A tuple can be empty `()` or have one or more items. Regardless, you can get its length using Python's built-in `len()` function. By printing `len.__doc__`, you can see in the terminal the description of this function

```python
# print string message for len() built-in function
print(len.__doc__)

>>> 'Return the number of items in a container.'
```

Same as what you saw in the strings and list chapters. The `len()` function returns the number of items in a container. The container is the tuple. The number of items is the number of items in the tuple. The `len()` function accepts one argument and returns an integer.

```python
# define variable
inventory_tuple = ('pants', 'shirts', 'hats')

# print length of tuple
print(len(inventory_tuple))

>>> 3
```

The example above prints the length of `inventory_tuple`, which is `3`. As explained in the strings and lists chapters, the type returned by `len()` is an integer `<class 'int'>` and `len()` takes exactly one argument.

Use `len()` with other code to help dictate flow. In the lists chapter, the example was using `len()` in an `if / elif / else` block. Here is an example of using `len()` with `in`.

```python
# define variables
inventory_pants = ('jeans', 'khakis', 'athletic')
inventory_shirts = ('long sleeves', 'short sleeve', 'collar', 'button up', 't-shirt')
inventory_counts = (3, 6, 9)


# define function that checks tuple length
def check_length(input):
    if len(input) in inventory_counts:
        print('Alert admin')
    else:
        print('No alert required')


# call functions once for each variable as argument
check_length(inventory_pants)
check_length(inventory_shirts)

>>> 'Alert admin'
>>> 'No alert required'
```

The example above defines three variables `inventory_pants`, `inventory_shirts`, and `inventory_counts`. The tuple `inventory_pants` has three items and the tuple `inventory_shirts` has five items. The tuple `inventory_counts` has three items `(3, 6, 9)`. You then define a function `check_length` that has one parameter `input`. The function checks the length of `input`. If the input length is in the tuple `inventory_counts`, then the function prints `'Alert admin'`. Otherwise, the function prints `'No alert requiredd'`. 

You call the function twice. First with the input being `inventory_pants`, which has a length of `3`, and then `inventory_shirts`, which has a length of `5`. The outcome in the terminal for the first function is `'Alert admin'` and for the second function is `'No alert required'`.

## [Get tuple min and max](#get-tuple-min-and-max)

You can get the minimum and maximum values of a tuple. Use Python's built-in functions `min()` and `max()` methods. The `min()` method returns the smallest item in the tuple. The `max()` method returns the largest item in the tuple. When using `min()` and `max()`, you need to compare values of the same type or else you get an error. The smallest string appears earliest in the alphabet and the largest appears latest in the alphabet.

```python
# example min and max on tuple of strings
alpha_tuple = ('A', 'C', 'B', 'E', 'D')
print(min(alpha_tuple))
print(max(alpha_tuple))

>>> A
>>> E

# example min and max on tuple of numbers
number_tuple = (1, 3, 2, 5, 4, 6, 7, 9, 8)
print(min(number_tuple))
print(max(number_tuple))

>>> 1
>>> 9

# example min and max on mixed tuple
mixed_tuple = (1, 3, 2, 5, 4, 6, 7, 9, 8, 'A', 'C', 'B', 'E', 'D')
print(min(mixed_tuple))
print(max(mixed_tuple))

>>> 'TypeError: '<' not supported between instances of 'str' and 'int''
```

The examples above each declare a tuple and print the `min()` and `max()` of the tuple. The first is a tuple of strings `['A', 'C', 'B', 'E', 'D']`. The `min()` is `'A'` because it appears earliest in the alphabet (the smallest) and the `max()` is `'E'` because it appears latest (the largest).

The second example is a tuple of integers `number_tuple = [1, 3, 2, 5, 4, 6, 7, 9, 8]`. The `min()` is `1` because it is the smallest and the `max()` is `9` because it is the largest.

The third exmple is a tuple of integers and strings. It returns an error `'TypeError: '<' not supported between instances of 'str' and 'int''`. The `min()` and `max()` methods cannot operate on mixed tuples.

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

## [Compare tuples](#compare-tuples)

You can compare tuples to see if they are equal `==` to one another. When you compare the equality of two tuples, you are comparing whether they have the same items listed in the same order. In contrast, you can compare tuples to see whether they contain the same items regardless of their order. 

Check whether two tuples are equal using the equal to operator `==`. The `==` operator checks whether two tuples have the same items in the same order. The order in which you specify the elements in a tuple is a characteristic of the tuple that is stored in memory. Tuples that have the same elements in the same order are equal to one another. Tuples that have the same elements but in a different order are not equal to one another.

```python
# examples of comparing tuples
tuple_one = ('we', 'sell', 'pants', 'and', 'shirts')
tuple_one_copy = ('we', 'sell', 'pants', 'and', 'shirts')
tuple_two = ('sell', 'we', 'pants', 'shirts', 'and')
tuple_three = ('shirts', 'and', 'pants', 'we', 'sell')

print(tuple_one == tuple_one_copy)
print(tuple_one == tuple_two)
print(tuple_two == tuple_three)

>>> True
>>> False
>>> False
```

The example above defines four variables all of which are set equal to tuples containing identical values. Two of the tuples have the items listed in the same order `tuple_one` and `tuple_one_copy`. The other two tuples have the items ordered in a unique way `tuple_two` and `tuple_three`. Comparing `tuple_one` to `tuple_one_copy` using the equal to operator `==` returns `True`. Comparing `tuple_one` to each of `tuple_two` and `tuple_three` using the equal to operator `==` returns `False`. Although `tuple_one` has the same items as `tuple_two` and `tuple_three`, the items are listed in a different order.

Check whether two tuples have the same items regardless of the order they are listed. Although two tuples may not be equal to one another, they still may have all the same items. You may want to check for that. Multiple ways may exist for this. One way is to first check the length of each tuple. Only if the lengths are equal, then sort each list using Python's `sorted()` method and compare the sorted lists. 

```python
# find whether two tuples contain same items even if in different order
tuple_one = ('we', 'sell', 'pants', 'and', 'shirts')
tuple_two = ('sell', 'we', 'pants', 'shirts', 'and')

if tuple_one != tuple_two:
    print(len(tuple_one) == len(tuple_two) and sorted(tuple_one) == sorted(tuple_two))

>>> True
```

In the example above, the variables `tuple_one` and `tuple_two` have the same items listed in a different order. You first check whether `tuple_one` is not equal to `tuple_two`. If that's `True`, you compare the length of the two tuples. 

By comparing the length of those two tuples, you can quickly determine whether they might be the same `len(tuple_one) == len(tuple_two)`. If they have different lengths, then they can't have the same items listed in a different order and you don't have to run the more resource-intensive `sorted()` method. If the tuples have the same length, it's possible they have the same items but in a different order (you know they're not in the same order because `tuple_one != tuple_two`). 

To check the `sorted` tuples only if the tuple lengths are equal, chain the length comparison expression to the sorted tuple comparison expression using `and`-- `len(tuple_one) == len(tuple_two) and sorted(tuple_one) == sorted(tuple_two)`. If the length comparison is `False` (they don't have the same number of items), then the Python interpreter doesn't read the expression after the `and` because both expressions are not `True`. If the length comparison is `True` then Python reads the `and` part of the expression. 

If the tuples have the same length, by comparing equality for the `sorted` tuples, you know whether they have the same items and now in the same order `sorted(tuple_one) == sorted(tuple_two)`. Here it's `True`.

## [Combine tuples concatenation and replication](#combine-tuples-concatenation-and-replication)

You can concatenate `+` and replicate `*` tuples. Combine multiple tuples, whether the same tuple or different tuples, using tuple concatenation `+`. Combine the same tuple to itself using replication `*`. 

Tuple concatentation is combining tuples using the `+` operator. For instance, declare three variables and set each equal to a tuple. Create a fourth variable whose value is equal to the sum of the first three variables.

```python
# example of tuple concatenation 
intro_tuple = ('we', 'sell')
pants_tuple = ('jeans', 'khakis', 'athletic pants')
shirts_tuple = ('casual shirts', 'dress shirts')

message_tuple = intro_tuple + pants_tuple + shirts_tuple
print(message_tuple)

>>> '('we', 'sell', 'jeans', 'khakis', 'athletic pants', 'casual shirts', 'dress shirts')'
```

The example above defines three variables `intro_tuple`, `pants_tuple`, and `shirts_tuple` and sets them each equal to tuples of different values. The fourth variable `message_tuple` is the sum of the first three variables `message_tuple = intro_tuple + pants_tuple + shirts_tuple`. The result of the tuple concatentation is `'('we', 'sell', 'jeans', 'khakis', 'athletic pants', 'casual shirts', 'dress shirts')'`.

Tuple concatenation works only when combining two or more tuples. It does not work when trying to add a tuple to some other data type.

```python
# example of tuple concatenation error
intro_tuple = ('we', 'sell')
pants_tuple = ('jeans', 'khakis', 'athletic pants')
shirts_list = ['casual shirts', 'dress shirts']

message_tuple = intro_tuple + pants_tuple + shirts_list
print(message_tuple)

>>> 'TypeError: can only concatenate tuple (not "list") to tuple'
```
The example above is the same as the one before it, except it changed `shirts_tuple` to `shirts_list` whose value is a list. The tuple concatenation for `message_tuple` attempts to add a list to tuples `message_tuple = intro_tuple + pants_tuple + shirts_tuple`. You get an error `TypeError: can only concatenate tuple (not "list") to tuple`. You can't add a tuple to a non-tuple.

Tuple replication is replicating a tuple by multplying it by an integer using the `*` operator. For instance, declare a variable and set it equal to a tuple. Multiply the variable by an integer of `5`. It returns a new tuple with the values from the original tuple appearing five times in the new list.

```python
# example of tuple replication
pants_tuple = ('jeans', 'khakis', 'athletic pants')

print(pants_tuple * 3)

>>> '('jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants')'
```

The above example defines the variable `pants_tuple` and sets it equal to a tuple with three items `('jeans', 'khakis', 'athletic pants')`. Multiplying `pants_tuple` by the integer `3` returns a new tuple with the items from the original tuple appearing three times each `('jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants', 'jeans', 'khakis', 'athletic pants')`.

If you multiply the tuple by a non-integer, you get an error.

```python
# example of tuple replication error
pants_tuple = ('jeans', 'khakis', 'athletic pants')

print(pants_tuple * pants_tuple)

>>> 'TypeError: can't multiply sequence by non-int of type 'tuple''
```

The above example is the same as the one before it, except this one multiplies `pant_tuple` by `pant_tuple`. You get an error `TypeError: can't multiply sequence by non-int of type 'tuple'` because you can't multiply a tuple by a non-integer, and `pant_tuple` is a tuple, not an integer.

## [Access tuple item using index position](#access-tuple-item-using-index-position)

Access a specific item in a tuple using its index position. Every item in a tuple has a positive index position. From left to right, the first index position is `0` and the last index position in the tuple is the tuple length minus one `len(a) - 1`. 

Every item in a tuple also has a negative index position. Negative indexing allows you to access items using the end of the tuple as the reference point. From right to left, the last item in the tuple has a negative index position of `-1` and moving left the index decreases by `1` (e.g., `-2`, `-3`, `-4`,  . . .). 

To use the index position, first save the tuple to a variable. Then append to the variable square brackets wrapping the index position of the item you want to access `pants_male[1]`.

```python
# example of using index position with tuple
pants_tuple = ('jeans', 'khakis', 'athletic pants')

print(pants_tuple[1])
print(pants_tuple[-3])

>>> 'khakis'
>>> 'jeans'
```

In the example above, you declare a variable named `pants_tuple` and set it equal to a tuple `('jeans', 'khakis', 'athletic pants')`. Then you print the item in index position `1` in the line `print(pants_tuple[1])`. The item with an index position of `1` in `pants_tuple` is `'khakis'`. You also print the item in index position `-3` in the line `print(pants_tuple[-3])`. The item with an index position of `-3` in `pants_tuple` is `'jeans'`.

Here are the index positions for each character.

```python
Character           Index           Negative Index

'jeans'                 0             -3           
'khakis'                1             -2
'athletic pants'        2             -1
```

Trying to print an index position that doesn't exist results in an error. 

```python
# define variable
pants_tuple = ('jeans', 'khakis', 'athletic pants')

# try to print index position out of range
print(pants_tuple[10])

>>> 'IndexError: tuple index out of range'
```

The example above defines the same `pants_tuple` variable as before having a tuple as its value `('jeans', 'khakis', 'athletic pants')`. The list has a length of `3`, which means its items occupy index position `0`, `1`, and `2`. After defining the variable, you print the `pants_tuple` item in index position `10`. You get an error `IndexError: tuple index out of range` because `pants_tuple` doesn't have an index position `10`.


## [Check for item in tuple](#check-for-item-in-tuple)

Check whether an item is in a tuple using the `in` and `not in` operators. Expressions using `in` and `not in` return a Boolean `True` or `False`. Using `in`, if an item is in the tuple, the expression returns `True`. If the item is not in the tuple, the expression returns `False`. Using `not in`, if an item is in the tuple, the expression returns `False`. If the item is not in the tuple, the expression returns `True`.

```python
# examples of tuples using in and not in
pants_tuple = ('jeans', 'khakis', 'athletic pants')

print('jeans' in pants_tuple)
print('jeans' not in pants_tuple)
print('shirt' in pants_tuple)

>>> True
>>> False
>>> False
```

The example above defines the same `pants_tuple` variable as in the other examples and sets it equal to the list `('jeans', 'khakis', 'athletic pants')`. You then print the outcome of three expressions. The first checks whether `'jeans'` is `in` the `pants_tuple`. It returns `True`. The second checks whether `'jeans'` is `not in` the `pants_tuple`. It returns `False`. The third checks whether `'shirt'` is `in` the `pants_tuple`. It returns `False`.

Use the `in` and `not in` operators in combination with functions and `if / elif /else` blocks to control the flow.

```python
# define variables
pants_tuple = ('jeans', 'khakis', 'athletic pants')

# check if item is in the tuple
def check_item(input):
    if input in pants_tuple:
        return input + ' ' + 'is in the pants tuple'
    else:
        return 'The pants tuple does not contain' + ' ' + input


print(check_item('jeans'))
print(check_item('shirt'))

>>> 'jeans is in the pants tuple'
>>> 'The pants tuple does not contain shirt'
```

The exmple above defines the `pants_tuple` variable equal to `('jeans', 'khakis', 'athletic pants')`. Then you define a function named `check_item`. It has one parameter named `input`. The function checks if `input` is `in` the `pants_tuple`. If so, it returns a message saying the input is in the pants tuple. If not, it returns a message saying the pants tuple does not contain the input. Here you call the function twice, first with `'jeans'` as the input and then with `'shirt'`. The terminal prints first `'jeans is in the pants tuple'` and then `'The pants tuple does not contain shirt'`.

## [Access range of tuple items using slice](#access-range-of-tuple-items-using-slice)

Slicing allows you to access a range of items in a tuple using index positions. To slice a variable named `pants_tuple` having a value of `('jeans', 'khakis', 'athletic pants')`, you declare the starting and ending values of the range you want to access. You declare the starting and ending values at the end of the tuple within square brackets `[]` separated by a colon `:`, with the ending value being not included. So choose a number one more than what you want included. 

You also can specify the stepper, which is the value by which the slicing increments within in your range. The default value for the stepper is `1` (every item within the range). Declare it using a colon `:` after the ending number and then the stepper.

```python
# define tuple
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')

# example of slicing range
print(inventory_tuple[3:6])

>>> '('shirts', 'hats', 'jackets')'
```

The example above prints index positions `3 - 5` (`6` not included) of `inventory_tuple`, which corresponds to `('shirts', 'hats', 'jackets')`. No stepper declared, so it includes all the items within the specified (other than the last item, `6`). If, however, you declare a separator greater than `1`, then the output changes.

Negative slicing allows you to access items using the end of the tuple as the reference point. As mentioned above, each item in a tuple has a negative index position. The last item in the tuple is index position `-1` and as you move left across the list, the index position decreases by `1` (e.g., . . ., `-2`, `-3`, `-4`, `-5` . . . beginning of tuple).

```python
# define tuple
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')

# example of negative slicing range
print(inventory_tuple[-7:-2])

>>> '('athletic pants', 'shirts', 'hats', 'jackets', 'gloves')'
```

The example above is the same as the one before it, except this one has a slicing range of index positions `-7` to `-2`. This time the output is `('athletic pants', 'shirts', 'hats', 'jackets', 'gloves')`. The item at index position `-7` is `'athletic pants'` and at index position `-3` is `'gloves'`. Remember the ending value of `-2` for slicing is not included, so the value at index position `-3` is the last value in the sliced tuple.

You can slice a tuple without declaring starting and ending position. If you want the slicing to start at the first item, don't declare a starting position. If you want the slicing to include the last item, don't declare an ending position. 

To omit the starting position, in the square brackets write a colon followed by the ending position `inventory_tuple[:5]`. To omit the ending position, in the square brackets write a colon followed by the ending position `inventory_tuple[3:]`.

```python
# define variable
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')


# slicing a tuple without specifying a start
print(inventory_tuple[:5])

>>> '('jeans', 'khakis', 'athletic pants', 'shirts', 'hats')'


# slicing a tuple without specifying an end
print(inventory_tuple[3:])

>>> '('shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')'
```

In the examples above, first you print from the beginning of the tuple to item `5` in the tuple `inventory_tuple[:5]`. This returns `('jeans', 'khakis', 'athletic pants', 'shirts', 'hats')`. Next you print from index position `3` until the end of the tuple `inventory_tuple[3:]`. This returns a different tuple `('shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')`. 

In addition to declaring a starting and ending position, you can also declare a stepper. A stepper the integer value that the slicing uses to increment through your tuple. For instance, a stepper value of `3` gets every third item in the range.

```python
# define variable
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')

# example of slicing
print(inventory_tuple[1:6:2])

>> '('khakis', 'shirts', 'jackets')'
```

The example above is the same as the one before it, except this one has a starting index position of `1`, and ending index position of `6`, and a stepper of `2` when slicing `inventory_tuple[1:6:2]`. This time the output is `('khakis', 'shirts', 'jackets')` because the stepper is `2`, so it skips every other character in the range of `1 - 6`.

Instead of declaring a positive stepper, you can declare a negative stepper. When you declare a negative stepper, the starting index position must be greater than the ending index position or else you receive an empty tuple.

```python
# define variable
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')


# example of slicing negative stepper wrong starting / ending order
print(inventory_tuple[1:6:-2])

>>> '()'


# example of slicing negative stepper correct starting / ending order
print(inventory_tuple[6:1:-2])

>>> '('gloves', 'hats', 'athletic pants')'
```

In the examples above, the first one is the same as the one before it, except this one has a starting stepper of `-2`. It has a starting index position of `1`, an ending index position of `6`, and a stepper of `-2` when slicing `inventory_tuple[1:6:-2]`. This time the output is an empty tuple`()` because the stepper counts down from `1` but the ending position is up at `6`.

The second example is the same as the first, except it swaps the starting and ending positions. It has a starting index position of `6`, an ending index position of `1`, and a stepper of `-2` when slicing `inventory_tuple[6:1:-2]`. This time the output is not an empty tuple `('gloves', 'hats', 'athletic pants')` because the stepper counts down from `6` to `1`.

To omit the ending position and also use a stepper, in the square brackets write a colon followed by the starting position, two colons, and the stepper value `inventory_tuple[3::2]`. To omit the starting position, you write it like normal.

```python
# define variable
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')


# slicing a tuple without specifying an end but with stepper
print(inventory_tuple[3::2])

>>> '('shirts', 'jackets', 'dresses')'
```

The example above defines a tuple `inventory_tuple` and prints from the tuple index position `3` until the end of the tuple every other item `inventory_tuple[3::2]`. This returns another different tuple `('shirts', 'jackets', 'dresses')`.

You can use slicing to reverse the order of a tuple. In the square brackets, declare only a stepper of `-1`. Don't include a starting or ending position.

```python
# define variable
inventory_tuple = ('jeans', 'khakis', 'athletic pants', 'shirts', 'hats', 'jackets', 'gloves', 'dresses', 'skirts')

# example of reversing a tuple
print(inventory_tuple[::-1])

>>> '('skirts', 'dresses', 'gloves', 'jackets', 'hats', 'shirts', 'athletic pants', 'khakis', 'jeans')'
```

The example above reverses the order of the tuple by starting at the last item, ending at the first item, and counting backwards by 1 `inventory_tuple[::-1]`. This returns the tuple in reverse order `('skirts', 'dresses', 'gloves', 'jackets', 'hats', 'shirts', 'athletic pants', 'khakis', 'jeans')`.

## [Mutate and modify tuples](#mutate-and-modify-tuples)

Unlike lists, tuples are not mutable and dynamic. This means that you cannot add, delete, modify, and move them around. Therefore, you cannot `.append()`, `.extend()`, `del`, `.clear()`, modify values, `.pop()`, `.reverse()`, `.sort()`, and `.insert()` like you can with lists.

You can, however, get the index position of an item in a tuple and also get the count of the number of times an value appears in a tuple. 

To get the index position of an item in a tuple, use the `.index()` instance method for tuples. Entering in your terminal `print(().index.__doc__)` prints the docstring for `.index()`, which is `Return first index of value. Raises ValueError if the value is not present.`

```python
# define variable
sample_tuple = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_tuple.index("Second")
print(index_of_second)

>>> 1
```

The `.index()` instance method returns an error if the argument passed into `.index()` is not in the tuple.

```python
# define variable
sample_tuple = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_tuple.index("1")
print(index_of_second)

>>> 'ValueError: tuple.index(x): x not in tuple'
```

The `.index()` instance method accepts one argument or else it returns an error.

```python
# define variable
sample_tuple = ['First', 'Second', 'Third', 'Fourth', 'Fifth']

# example of index
index_of_second = sample_tuple.index("Second", "Third")
print(index_of_second)

>>> 'TypeError: slice indices must be integers or have an __index__ method'
```

To count the number of times a value appears in a tuple, use the `.count()` instance method for tuples. Entering in your terminal `print(().count.__doc__)` prints the docstring for `.count()`, which is `Return number of occurrences of value.`

```python
# define variable
sample_tuple = ('First', 'Second', 'Third', 'Fourth', 'Fifth')

# example of count
number_of_thirds = sample_tuple.count("Third")
print(number_of_thirds)

>>> 1
```

The `.count()` instance method returns `0` if the argument passed into `.count()` is not in the tuple.


```python
# define variable
sample_tuple = ('First', 'Second', 'Third', 'Fourth', 'Fifth')

# example of count
number_of_thirds = sample_tuple.count("8")
print(number_of_thirds)

>>> 0
```

The `.count()` instance method accepts one argument or else it returns an error.

```python
# define variable
sample_tuple = ('First', 'Second', 'Third', 'Fourth', 'Fifth')

# example of count
number_of_thirds = sample_tuple.count("8", "9")
print(number_of_thirds)

>>> 'TypeError: count() takes exactly one argument (2 given)'
```

## [Use tuple methods](#use-tuple-methods)

Python has only a few built-in methods for tuples (e.g., .index() and .count()).

Method: `.count()`  
Docstring: Return number of occurrences of value.  
What it does: Returns number of times specified value appears in tuple  


Method: `.index()`  
Docstring: Return first index of value. Raises ValueError if the value is not present.  
What it does: Returns the index of the specified value



