# Strings

You've seen strings in previous chapters. Stings are text. Letters, words, phrases, sentences, and paragraphs are examples of strings. You've printed them and added them to one another. Now are going to take a deeper look into how you can work with strings in Python.

Although strings are easy to think of as just text, technically a string is a sequence of bytes. Each byte represents a unicode character. Unicode is the standard for representing in code the letters, numbers, and other characters in human languages. It's okay to think of it as text.

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

## [Combine multiple strings using string concatenation](#combine-multiple-strings-using-string-concatenation)

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

## [Convert other data types into strings](#convert-other-data-types-into-strings)

Convert other data types into strings using Python's built-in functions. Two of those functions are `str()` and `join()`. 

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

use join() to convert list

## [Convert a string into a list](#convert-a-string-into-a-list)

## [Access character in string using index position](#access-character-in-string-using-index-position)

Access a specific character in a string using its index position. Every character in a string has an index position. From left to right, the first index position is `0` and the last index position is the string length minus one `len(a) - 1`. 

To use the index position, first save the string to a variable. Then append to the variable square brackets wrapping the index position of the character you want to access `pants_male[1]`.

```python
# example of using index position with string
pants_male = 'Male Pants'

print(pants_male[1])

>>> a
```

In the example above, you declare a variable named `pants_male` and set it equal to `'Male Pants'`. Then you print the character in index position `1` in the line `print(pants_male[1])`. The character with an index position of `1` in the `pants_male` value of `'Male Pants'` is `'a'`. Here is a list of the index positions for each character.

```python
Character     Index

'M'             0
'a'            1
'l'             2
'e'             3
' '             4
'P'             5
'a'             6
'n'             7
't'             8
's'             9
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

Slicing allows you to access a range of characters in a string. Using the starting index position and the ending position + 1 of the characters you want to access

In strings.py, see comment:
slicing allows you to access a range of characters in a string


Negative slicing allows you to access characters using the end of the string as the reference point. While strings have positive index positions corresponding to each element in the string, each element in the string also has a negative index position. The last character in the string is index position -1 and as you move left across the string, the index position decreases by 1 (e.g., . . ., -2, -3, -4, -5 . . . beginning of string).

In strings.py, see comment:
# negative slicing allows you to access characters using the end of the string as the reference point

## [String formatting to combine string with other data types](#string-formatting-to-combine-string-with-other-data-types) 
combine strings with non-strings, like variables and numbers. string formatting is the "old way" but still very important to know. f-strings is the "new way" and also important to know.

In strings.py, see comments:
by placing {} within your string and using the .format() method, you can fill in the {} with the arguments within the () of .format()
to make your code easier to read and more precise, use index numbers (e.g., {0}) that correspond to the position of the arguments within .format()


## [Fstrings to combine string with other data types](#fstrings-to-combine-string-with-other-data-types)

f-string is the "new way" to format strings; the concept is the same as for the old way; however, the syntax is new
simpler syntax
evaluated at runtime, which allows you to insert you can pass anything into f-strings, including functions, methods, expressions, numbers, variables, and objects

In strings.py, see comment:
using f-strings to format strings

To learn more about the nitty gritty details: https://realpython.com/python-f-strings/
