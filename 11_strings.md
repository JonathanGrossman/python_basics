# Strings

You've seen strings in previous chapters. Stings are text. Letters, words, phrases, sentences, and paragraphs are examples of strings. You've printed them and added them to one another. Now are going to take a deeper look into how you can work with strings in Python.

Although strings are easy to think of as just text, technically a string is an immutable sequence of bytes. Each byte represents a unicode character. Unicode is the standard for representing in code the letters, numbers, and other characters in human languages. Immutable means that you can't directly alter the string object in memory. It's okay to think of it as text.

Write strings in your code by wrapping text with either double `""` or single `''` quotes. A string can have from zero to an unlimited number of characters (so long as the memory allows). Characters include letters, numbers, symbols, emojis, and more. For instance, `"Female Pants"`, `'Pants'`, `"0"`, and `u'\u2713'` (represents a checkmark `✓`) are valid strings.

You can do many things with strings in Python, such as 

- get the length of a string 
- access a specific character in a string using index position.   
- check for substring   
- combine multiple strings using string concatenation   
- convert other data types into strings  

Read below to learn more about working with strings in Python. 

## [Get the length of a string](#get-the-length-of-a-string)

A string can be empty `""` or have one or more characters. Regardless, you can get its length using Python's built-in `len()` function. By printing `len.__doc__`, you can see in the terminal the description of this function

```python
# print string message for len() built-in function
print(len.__doc__)

>>> 'Return the number of items in a container.'
```

The `len()` function returns the number of items in a container. The container is the string. The number of items is the number of characters in the string. The `len()` function accepts one argument and returns an integer.

```python
# print length of string
print(len('pants'))

>>> 5

# print type for length return
print(type(len('pants')))

>>> <class 'int'>

# print length with more than one input
print(len('pants', 'shirts'))

>>> 'TypeError: len() takes exactly one argument (2 given)'
```

The first example above prints the length of `'pants'`, which is `5`. The second example prints the data type `type()` of `len()`, which is an integer `<class 'int'>`. The third example attempts to print the length of two strings in the same `len()` call. It returns an error because `len()` takes exactly one argument but you gave it 2 `'TypeError: len() takes exactly one argument (2 given)'`.

Use `len()` with other code to help dictate flow. For instance, here is an example of using `len()` in an `if / elif / else` block.

```python
pants_female = "We have female pants in our store."
pants_male = "Pant"
pants = "We have pants"

def check_string(input):
    if len(input) > 15:
        print('Too long.')
    elif len(input) < 5: 
        print('Too short.')
    else:
        print('Nice.')

check_string(pants_female)
check_string(pants_male)
check_string(pants)

>>> 'Too long.'
>>> 'Too short.'
>>> 'Nice.'
```

The example above defines three variables `pants_female`, `pants_male`, and `pants`. It then defines a function `check_string` that has one parameter `input`. The function checks the length of `input`. If greater than `15` the function prints `'Too long.'` If less than `5`, it prints `'Too short.'`. Otherwise, it prints `'Nice.'` You call the function three times, each time with one of the three variables in the order of `pants_female`, `pants_male`, and `pants`. The outcome in the terminal is `'Too long.'`, `'Too short.'`, and `'Nice.'`

## [Combine strings using string concatenation](#combine-strings-using-string-concatenation)

Combine multiple strings using string concatentation, which is to combine strings using the `+` operator. For instance, declare three variables and set each equal to a string. Create a fourth variable whose value is equal to the sum of the first three variables.

```python
# define variables
intro = 'We sell'
space = ' '
items = 'pants and shirts.'


# example of string concatenation
message = intro + space + items

print(message)

>>> 'We sell pants and shirts.'
```

The example above defines three variables `intro`, `space`, and `items` and sets them equal to the srings `'We sell'`, `' '`, and `'pants and shirts'`, respectively. You then save the sum of the variables to the variable `message` and print it. The result is `'We sell pants and shirts.'`

The string `' '` represents a space. Although its value is not a letter, it is still a string. It's a string length of `1`.

```python
# print length of space
print(len(' '))

>>> 1
```

String concatenation works only when combining two or more strings. It does not work when try to add a string to some other data type.

```python
#define variables
intro = "We sell"
space = " "
number = 100
items = "pants and shirts."


# example of string concatenation
message = intro + space + number + space + items

print(message)

>>> 'TypeError: can only concatenate str (not "int") to str'
```

The example above is the same as the one before it, except this example has an additional variable named `number` having an integer value of `100`. Including number in the string concatenation causes an error `'TypeError: can only concatenate str (not "int") to str'`. The error says that you cannot add a string to an integer.

The same is true for other data types. Here is an example of trying to include a list in string concatenation.

```python
#define variables
intro = "We sell"
space = " "
items = ['pants', 'shirts']

# example of string concatenation
message = intro + space + items

print(message)

>>> 'TypeError: can only concatenate str (not "list") to str'
```

The example above is the same as the one before it, except this one removed the `number` variable and changed the items variable to be a list having two items inside `['pants', 'shirts']`. Including the list in the string concatenation causes an error `'TypeError: can only concatenate str (not "list") to str'`. The error says that you cannot add a string to a list.

## [Convert other data types into strings using str](#convert-other-data-types-into-strings-using-str)

Convert other data types into strings using Python's built-in `str()` function. 

The `str()` function accepts one argument -- an object of any data type.

```python
# example of converting an int to a string
print(type(9), 9, type(str(9)), str('9'))

>>> '<class 'int'> 9 <class 'str'> 9'

# example of converting a list to a string
print(type(['pants', 'shirts']), ['pants', 'shirts'], type(str(['pants', 'shirts'])), str(['pants', 'shirts']))

>>> '<class 'list'> ['pants', 'shirts'] <class 'str'> ['pants', 'shirts']'
```

The examples above use `str()` to convert an integer to a string and a list to a string. The first example prints the type of `9`, `9`, type of `str(9)`, and `str(9)`. The result is `'<class 'int'> 9 <class 'str'> 9'`, an integer to a string. The second example prints the type of `['pants', 'shirts']`, `['pants', 'shirts']`, type of `str(['pants', 'shirts'])`, and `str(['pants', 'shirts'])`. The result is `'<class 'list'> ['pants', 'shirts'] <class 'str'> ['pants', 'shirts']'`, a list to a string.

A few examples above, you tried to use string concatentation to add a number to a string but encountered an error. You can overcome that error by using in the string concatentation `str()` with the number as the argument.

```python
#define variables
intro = "We sell"
space = " "
number = 100
items = "pants and shirts."


# example of string concatenation
message = intro + space + str(number) + space + items

print(message)

>>> 'We sell 100 pants and shirts.'
```

This example is the same as before except now instead of `number` in the string concatenation, it contains `str(number)`. The new expression is `message = intro + space + str(number) + space + items`. Instead of an error, the result is `'We sell 100 pants and shirts.'`.

Print `str.__doc__` to get the docstring and learn more. The line `Create a new string object from the given object.` is the most important for now. The rest you can probably ignore.

```python
# print docstring for str()
print(str.__doc__)

>>> 'str(object='') -> str'
>>> 'str(bytes_or_buffer[, encoding[, errors]]) -> str'

>>> 'Create a new string object from the given object. If encoding or'
>>> 'errors is specified, then the object must expose a data buffer'
>>> 'that will be decoded using the given encoding and error handler.'
>>> 'Otherwise, returns the result of object.__str__() (if defined)'
>>> 'or repr(object).'
>>> 'encoding defaults to sys.getd'
>>> 'errors defaults to 'strict'.'
```

## [Convert into a string using join](#convert-into-a-string-using-join)

Convert other data types (except for numbers and Booleans) into a string using an instance method for strings named `join()`. Use the `join()` method on a list, tuple, string, dictionary or set. The result is different than converting those to a string using `str()`. Using `str()`, the result that data type inside quotes. For instance, a list inside of quotes with square brackets and commas `'['pants', 'shirts', 'hats']'`. In contrast, the result of using `join()` is more like string concatenation of all the items in the object. You choose which value to separate them with. 

The syntax is as follows: a string for the value you want to use as the separator, then add `.join(the_object)` to it, where `the_object` is the Python object (e.g., list, tuple, set, etc.) containing the items you want to join. Common separator values are a space `' '` or comma + space `', '`. Empty quotes as a separator `''` results in no separation between items. Here are examples using a list.

```python
# define list and space connector
inventory_list = ['pants', 'shirts', 'hats']
connector = ' '

# turn list into string using join()
inventory_string = connector.join(inventory_list)

print(inventory_string)

>>> pants shirts hats

# define list and comma connector
inventory_list = ['pants', 'shirts', 'hats']
connector = ' '

# turn list into string using join()
inventory_string = connector.join(inventory_list)

print(inventory_string)

>>> pants, shirts, hats

# define list and no connector
inventory_list = ['pants', 'shirts', 'hats']
connector = ''

# turn list into string using join()
inventory_string = connector.join(inventory_list)

print(inventory_string)

>>> pantsshirtshats
```

The examples above are the same as one another except for the value for `connector`. The all define `inventory_list` as equal to `['pants', 'shirts', 'hats']`, they all have a variable `connector`, and they all define the variable `inventory_string` as equal to `connector.join(inventory_list)` and print `inventory_string`.

The value of `connector` in the first example is a space `' '`, in the second example is a comma and space `', '`, and in the third example is an empty string `''`. The result of printing `inventory_string` in that order are `pants shirts hats`, `pants, shirts, hats`, and `pantsshirtshats`.

Print `''.join.__doc__` to get the docstring for `join()`. Notice that the syntax is different for the others functions you've printing the docstring for. For those, you did `print(str._doc__)` because they are functions of Python, not functions of a Python object (functions of objects are called a method). Instead of `print(join.__doc__)`, you need to chain join to a string because join is a method of string objects. Therefore you need to have string object that you can use to access the `join()` method.

```python
# example of printing docstring for join()
print(''.join.__doc__)

>>> 'Concatenate any number of strings.'

>>> 'The string whose method is called is inserted in between each given string.'
>>> 'The result is returned as a new string.'

>>> 'Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs''
```

The output explains that the `join()` method concatenates any number of strings. Explore what other data types you can use this method for!

## [Convert a string into a list](#convert-a-string-into-a-list)

Convert a string into a list using an instance method for strings named `split()`. Using `split()`, you separate a string into an array of characters where each item in the array is one or more characters in the string. 

The syntax is as follows: a string for the value you want to use as the separator, then add `.split(the_object)` to it, where `the_object` is the string you want to split. The separator value . . . For instance, set no separator value and Python will use whitespaces as a separator by default and also will remove leading, trailing, and consecutive whitespace.

```python
# define string
string = "male  pants and shirt  female  pants and shirts"

# split string into list using different separators
string_list_none = string.split()
string_list_space = string.split(' ')

print(string_list_none)
print(string_list_space)


>>> '['male', 'pants', 'and', 'shirt', 'female', 'pants', 'and', 'shirts']'
>>> '['male', '', 'pants', 'and', 'shirt', '', 'female', '', 'pants', 'and', 'shirts']'
```

The example above defines a string named `string`. Its value has text with a few extra white spaces. You split the string twice. First using no separator and then using a space `' '` as a separator. You print the results of each and, respectively, get `['male', 'pants', 'and', 'shirt', 'female', 'pants', 'and', 'shirts']` and `['male', '', 'pants', 'and', 'shirt', '', 'female', '', 'pants', 'and', 'shirts']`. Using no separator returns just the words with no extra whitespace, whereas using a space `' '` as a separator includes in the list the extra spaces because it uses as the separator the first `' '` in a series of them, and then includes the rest in the list.

Print the docstring for `split()` to learn more about using it. Like for `join()` and other instance methods, you have to chain `.split.__doc__` to a Python string object. You can use `''`. 

```python
# print docstring for split string instance method
print(''.split.__doc__)

>>> 'Return a list of the words in the string, using sep as the delimiter string.'
>>> 
>>>   'sep'
>>>     'The delimiter according which to split the string.'
>>>     'None (the default value) means split according to any whitespace,'
>>>     'and discard empty strings from the result.'
>>>   'maxsplit'
>>>     'Maximum number of splits to do.'
>>>     '-1 (the default value) means no limit.'
 ```
 
The docstring says the function returns a list of the words in a string and uses sep as the delimiter string (the place where the splits happen). The default sep value is `None`, which splits any whitespace and discards emptry strings. 
 
In addition to using a separator, use the optional `maxsplit` value. Its default value of `-1` means split at every occurrence of the separator value. If, however, you set the `maxsplit` value, the split will happen only that number of times -- the `maxsplit` number of times.

```python
# define string
string = "pants and shirts, hats, coats, and gloves"

# split string with separator and maxsplit
string_list = string.split('and')

print(string_list)

>>> '['pants ', ' shirts, hats, coats, ', ' gloves']'


# define string
string = "pants and shirts, hats, coats, and gloves"

# split string with separator and maxsplit
string_list = string.split('and', maxsplit=1)

print(string_list)

>>>  '['pants ', ' shirts, hats, coats, and gloves']'
```
 
The examples above are identical except the first doesn't declare a `maxsplit` value and the second one declares a `maxsplit` value of `1`. Both examples define a variable `string` of text with the word `and` appearing twice. First, you split `string` using `and` as the separator with no `maxsplit`. It prints `['pants ', ' shirts, hats, coats, ', ' gloves']`. Both appearances of `and` are gone.

In the second example, you split `string` using `and` but this time you set a `maxsplit` value of `1`. It prints `['pants ', ' shirts, hats, coats, and gloves']`. Only the first `and` is gone. 

## [Access character in string using index position](#access-character-in-string-using-index-position)

Access a specific character in a string using its index position. Every character in a string has a positive index position. From left to right, the first index position is `0` and the last index position is the string length minus one `len(a) - 1`. 

Every character in a string also has a negative index position. Negative indexing allows you to access characters using the end of the string as the reference point. From right to left, the last character in the string has a negative index position of `-1` and moving left the index decreases by `1` (e.g., `-2`, `-3`, `-4`,  . . .). 

To use the index position, first save the string to a variable. Then append to the variable square brackets wrapping the index position of the character you want to access `pants_male[1]`.

```python
# example of using index position with string
pants_male = 'Male Pants'

print(pants_male[1])
print(pants_male[-3])

>>> 'a'
>>> 'n'
```

In the example above, you declare a variable named `pants_male` and set it equal to `'Male Pants'`. Then you print the character in index position `1` in the line `print(pants_male[1])`. The character with an index position of `1` in the `pants_male` value of `'Male Pants'` is `'a'`. You also print the character in index position `-3` in the line `print(pants_male[-3])`. The character with an index position of `-3` in the `pants_male` value of `'Male Pants'` is `'n'`.

Here is a list of the index positions for each character.

```python
Character     Index           Negative Index

'M'             0             -10           
'a'             1             -9
'l'             2             -8
'e'             3             -7
' '             4             -6
'P'             5             -5
'a'             6             -4
'n'             7             -3
't'             8             -2
's'             9             -1
```

# [Check for substring](#check-for-substring)

Check whether a substring is `in` or `not in` a string. For instance, check whether a message contains the word "pants" `"pants" in message`.

The `in` and `not in` operators check whether a substring exists in a string. Expressions using `in` and `not in` return Boolean values `True` or `False`.

```python
# check for a substring using "in" or "not in" (returns True or False)
message = 'We sell pants and shirts.'
x = 'pants' in message
y = 'socks' not in message
print(x, y)

>>> 'True True'
```

Checking for substrings help control the flow of your application. Use them in combination with conditionals and other operators to dictate what happens next. Here is an example of using `in` in a conditional statement inside of a function. 

```python
# define variables
item_pants = 'pants'
item_socks = 'socks'

# return message about whether item is in message
def get_message(item):
    company_message = 'We sell pants'
    if item in company_message:
        return company_message
    else: 
        return 'We do not sell' + ' ' + item
        
# get message for pants and socks 
pants_message = get_message(item_pants)
socks_message = get_message(item_socks)

# print messages for pants and socks
print(pants_message)
print(socks_message)


>>> 'We sell pants'
>>> 'We do not sell socks'
```

The example above defines two variables `item_pants` and `item_socks` and sets them equal to `'pants'` and `'socks'`. You then define the funtion `get_message` that has one parameter `item`. The function defines a variable `company_message` and sets it equal to `'We seel pants'`. Then you check whether `item` is in `company_message`. If `True` the function returns `company_message`. If `False` the function returns `'We do not sell' + ' ' + item`.

Next you call the function twice. First, passing `item_pants` as the argument and saving the return value to `pants_message`. Second, passing `item_sockss` as the argument and saving the return value to `socks_message`. You then print `pants_message` and `socks_message`.

The terminal prints `'We sell pants'` and `'We do not sell socks'`. For the first function call, item equals `pants` so the condition is `True` because `'pants'` is in the `company_message` value of `'We sell pants'`. The function returns `'We sell pants'` and therefore printing `pants_message` results in `'We sell pants'`. For the second function call, item equals `socks` so the condition is `False` because `'socks'` is not in the `company_message` value of `'We sell pants'`. The function returns `'We do not sell socks'` and therefore printing `socks_message` results in `'We do not sell socks'`.

## [Access range of characters in string with slicing](#access-range-of-characters-in-string-with-slicing)

Slicing allows you to access a range of characters in a string using index positions. To slice a variable named `inventory` having a value of `'we got pants'`, you declare the starting and ending values of the range, with the ending value being not included. So choose a number one more than what you want included. You declare these at the end of the string within square brackets `[]` separated by a colon `:`. You also can specify the stepper, which is the value by which the slicing increments within in your range. The default value for the stepper is `1` (every character within the range). Declare it using a colon `:` after the ending number and then the stepper.

```python
# define string
inventory = 'we got pants'

# example of slicing
print(inventory[3:6])

>>> 'got'
```

The example above prints index positions `3 - 5` (`6` not included), which corresponds to `got`. No stepper declared. If, however, you declare a separator greater than `1`, then the output changes.

```python
# define string
inventory = 'we got pants'

# example of slicing with stepper
print(inventory[3:6:2])

>> 'gt`
```

The example above is the same as the one before it, except this one has a stepper of `2` when slicing `inventory[3:6:2]`. It's the same range as before, which returned `'got'`. This time, however, the output is `'gt'` because the stepper is `2`, so it skips every other character in the range of `3 - 6`.

Negative slicing allows you to access characters using the end of the string as the reference point. As mentioned above, strings have a negative index position. The last character in the string is index position `-1` and as you move left across the string, the index position decreases by `1` (e.g., . . ., `-2`, `-3`, `-4`, `-5` . . . beginning of string).

```python
# define string
inventory = 'we got pants'

# example of slicing with stepper
print(inventory[-9:-2])

>>> 'got pan'
```

The example above is the same as the one before it, except this one has a slicing range of index positions `-9` to `-2` and no stepper `inventory[-9:-2]` This time the output is `'got pan'`. The character at index position `-9` is `g` and at index position `-3` is `n`. Remember the ending value of `-2` for slicing is not included, so the value at index position `-3` is the last value in the sliced string.

## [String formatting to combine string with other types](#string-formatting-to-combine-string-with-other-types) 
Use string formatting to combine strings with non-strings, like variables and numbers. With string formatting, you use placeholders `{}` in your string for the non-string data types. At then end of the string, you chain `.format()` and declare inside the parenthesis the data types that belong in the placeholders.

```python
# define variables
message = 'we sell pants and shirts'
varieties = 100

# string formatting example using a string and number
text_string = "Hi world, {}. We have over {} varieties in stock."

print(text_string.format(message, varieties))

>>> 'Hi world, we sell pants and shirts. We have over 100 varieties in stock.'
```

The example above defines two variables at the start `message` and `varieties`. For their values, `message` is a string and `varieties` is a number.  You have a third variable `text_string` set equal to a string using string formatting. The string contains two placeholders `{}`. The next line prints the formatted string with `message` and `varieties` as the arguments in `format()` -- `text_string.format(message, varieties)`. Python maps the arguments `message` and `varieties` to the placeholders in the order listed from left to right.

```python
# define variables
message = {'we', 'sell', 'pants', 'and', 'shirts'}
varieties = [100, 101]

# string formatting example using a set and list
text_string = "Hi world, {}. We have over {} varieties in stock."
print(text_string.format(message, varieties))

>>> 'Hi world, {'shirts', 'pants', 'we', 'and', 'sell'}. We have over [100, 101] varieties in stock.'
```
The example above is the same as the one before it except the `message` value is a set and the `varieties` value is a list. It works. Looks goofy, but it works.

The number of items in `format` must match the number of placeholders `{}` in the string. If not, you get an error.

```python
message = {'we', 'sell', 'pants', 'and', 'shirts'}
varieties = [100, 101]

# string formatting example using a set and list
text_string = "Hi world, {}. We have over {} varieties in stock."
print(text_string.format(message))
```

The example above is the same as the one before it except is has only one argument inside the `format()` call despite there being two placeholders `[]` in the string formatting. You get an error `IndexError: tuple index out of range`, which means you have a mismatch between placeholders `{}` and arguments.

Some people say string formatting is the "old way" because f-strings is a new way to do the same thing. String formatting is still very important to know because you will see it in other people's code all the time. 


to make your code easier to read and more precise, use index numbers (e.g., {0}) that correspond to the position of the arguments within .format()


## [Fstrings to combine string with other types](#fstrings-to-combine-string-with-other-types)

f-string is the "new way" to format strings; the concept is the same as for the old way; however, the syntax is new
simpler syntax
evaluated at runtime, which allows you to insert you can pass anything into f-strings, including functions, methods, expressions, numbers, variables, and objects

In strings.py, see comment:
using f-strings to format strings

To learn more about the nitty gritty details: https://realpython.com/python-f-strings/
