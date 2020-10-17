# Dictionaries

A dictionary is a collection of comma-separated key:value pairs wrapped in curly braces `{}`. You can use a dictionary to store information. Oftentimes, a dictionary is used to store multiple properties for a single item. For instance, it is common to use a dictionary to store information about a user. A user dictionary might have keys for first name, last name, email, and other user information. Another example of using a dictionary is for a transaction. A transaction dictionary might have keys for seller, buyer, price, date purchase, and other transactional information. 

A dictionary wraps its content in curly braces `{}`. You can create a dictionary using `{}` or use the built-in `dict()` function. The `dict()` function accepts a sequence of tuples where each tuple contains a key:value pair. You can create dictionaries on the fly, for instance, by creating an empty dictionary saved to a variable, and adding to it as you go.

Like lists, dictionaries are mutable (can be changed), dynamic (can grow and shrink in size), and can be nested (i.e., one inside another)

## [Dictinary keys](#dictionary-keys)

Unlike lists, dictionaries are not accessed by index. Instead, you use keys to access the contents inside a dictonary. Although almost anything can be a key (e.g., integer, float, Boolean, string, etc.), keys need to be unique (no duplicates) and immutable. It is probably most common to use a string as key. If, however, you use numbers for your keys, it makes accessing a dictionary appear the same as accessing a list index.

You can store a dictionary in memory as a variable and then retrieve a `value` from a dictionary by calling the value's `key`. You call the `key` using square brackets (`[]`) at the end of the name of the variable.

Trying to access a non-existing key results in a Key Error.

Adding and changing values is as simple as assigning a new key to a value or an existing key to a new value

Delete a key and its corresponding value using the `del` keyword followed by accessing the key.


Retrieve the value of a nested dictionary using the key of the outer dictionary that corresponds to a dictionary type, and also use the key of the inner dictionary corresponding to the value

Retrieve the value of a nested list using the dictionary key that corresponds to a list type, and also use the list index of the value

## [Dictionary Methods](dictionary-methods)

 Method
What it does
_dict.clear()
removes all key:value pairs from dictionary
_dict.get(<key>)
gets value for specified key; returns None if no such key
_dict.items()
returns a list of tuples containing the key-value pairs
_dict.keys()
returns a list of keys
_dict.values()
returns a list of values
_dict.fromkeys(<k>, <v>)
returns a dict (takes in 2 args - first = keys, second = vals)
_dict.pop(<key>, default)
removes key and returns value/default; error if no such key
_dict.popitem()
removes last key:value pair and returns it as tuple
_dict.update(<obj>)
merges dictionaries or dict with sequence of key:value pairs

Add more on built-in methods for dictionaries

## [Dictionary and for loop](#dictionary-and-for-loop)
In dictionaries.py, see:
examples of for loop with dictionaries

## [Dictionary in expressions](#dictionary-in-expressions)
examples using in with dictionaries


