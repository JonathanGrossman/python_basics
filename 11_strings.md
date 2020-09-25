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

The first example above prints the length of `'pants'`, which is `5`. The second example prints the data type `type()` of `len()`, which is an integer `<class 'int'>`. The third example attempts to print the length of two strings in the same `len()` call. It returns an error because `len()` takes exactly one argument but you gave it `2` `'TypeError: len() takes exactly one argument (2 given)'`.

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

female_pants = check_string(pants_female)
male_pants= check_string(pants_male)
all_pants = check_string(pants)

>>> 'Too long.'
>>> 'Too short.'
>>> 'Nice.'
```

The example above defines three variables `pants_female`, `pants_male`, and `pants`. It then defines a function `check_string` that has one parameter `input`. The function checks the length of `input`. If greater than `15` the function prints `'Too long.'` If less than `5`, it prints `'Too short.'`. Otherwise, it prints `'Nice.'` You call the function three times, each time with one of the three variables in the order of `pants_female`, `pants_male`, and `pants`. Printing the outcome of each call results in `'Too long.'`, `'Too short.'`, and `'Nice.'`

## [Combine multiple strings using string concatenation](#combine-multiple-strings-using-string-concatenation)

## [Convert other data types into strings](#convert-other-data-types-into-strings)

use str() to convert other data types into strings

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

## [Combine strings with non-strings](combine-strings-with-non-strings)


combine strings with non-strings, like variables and numbers. string formatting is the "old way" but still very important to know. f-strings is the "new way" and also important to know.

## [String formatting](#string-formatting) 

In strings.py, see comments:
by placing {} within your string and using the .format() method, you can fill in the {} with the arguments within the () of .format()
to make your code easier to read and more precise, use index numbers (e.g., {0}) that correspond to the position of the arguments within .format()


## [f-strings](#f-strings)

f-string is the "new way" to format strings; the concept is the same as for the old way; however, the syntax is new
simpler syntax
evaluated at runtime, which allows you to insert you can pass anything into f-strings, including functions, methods, expressions, numbers, variables, and objects

In strings.py, see comment:
using f-strings to format strings

To learn more about the nitty gritty details: https://realpython.com/python-f-strings/
