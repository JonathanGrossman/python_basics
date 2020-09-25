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


# combine multiple strings using string concatenation
# convert other data types into strings

In strings.py, see comments:
# get the length of a string using len()(returns a number)
# check for a substring using “in” or “not in” (returns True or False)
# combine two strings using + (called string concatenation)
# use str() to convert other data types into strings


# strings in Python have index positions, just like in JS
# slicing allows you to access a range of characters in a string
# using the starting index position and the ending position + 1 of the characters you want to access

In strings.py, see comment:
# slicing allows you to access a range of characters in a string


# negative slicing allows you to access characters using the end of the string as the reference point
# while strings have positive index positions corresponding to each element in the string, each element in the string also has a negative index position
# the last character in the string is index position -1 and as you move left across the string, the index position decreases by 1 (e.g., . . ., -2, -3, -4, -5 . . . beginning of string)
In strings.py, see comment:
# negative slicing allows you to access characters using the end of the string as the reference point


# combine strings with non-strings, like variables and numbers
# string formatting and f-strings are two ways
# f-strings is the “old way”
In strings.py, see comments:
# by placing {} within your string and using the .format() method, you can fill in the {} with the arguments within the () of .format()

# to make your code easier to read and more precise, use index numbers (e.g., {0}) that correspond to the position of the arguments within .format()


# f-string is the “new way” to format strings; the concept is the same as for the old way; however, the syntax is new
#simpler syntax
# evaluated at runtime, which allows you to insert you can pass anything into f-strings, including functions, methods, expressions, numbers, variables, and objects

In strings.py, see comment:
# using f-strings to format strings

To learn more about the nitty gritty details: https://realpython.com/python-f-strings/
