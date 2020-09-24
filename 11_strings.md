# Strings

# strings are arrays of bytes that represent unicode characters
# strings are represented by double or single quotes “ “ or ‘ ’ and can contain any type of text
# strings in python are similar to strings in JS; for instance, you can access a specific character in a string using its index position

In strings.py, see comment:
# access a specific character in a string using index position


Common things to do with strings:

# get the length of a string
# check for substring
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
