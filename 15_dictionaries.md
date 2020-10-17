# Dictionaries

A dictionary is a collection of comma-separated key:value pairs wrapped in curly braces `{}`. You can use a dictionary to store information. Oftentimes, a dictionary is used to store multiple properties for a single item. For instance, it is common to use a dictionary to store information about a user. A user dictionary might have keys for first name, last name, email, and other user information. Another example of using a dictionary is for a transaction. A transaction dictionary might have keys for seller, buyer, price, date purchase, and other transactional information. 

A dictionary wraps its content in curly braces `{}`. You can create a dictionary using `{}` or use the built-in `dict()` function. The `dict()` function accepts a sequence of tuples where each tuple contains a key:value pair.

Like lists, dictionaries are mutable (can be changed), dynamic (can grow and shrink in size), and can be nested (i.e., one inside another)

Unlike lists, dictionaries are not accessed by index. Instead, you use keys to access the contents inside a dictonary. 

Almost anything can be a key (e.g., integer, float, Boolean, string, etc.). However, keys need to be unique (no duplicates) and immutable.


retrieve a value from a dictionary by calling its key in square brackets ([]) following the name of the dictionary
you can use strings or numbers as keys; using numbers makes accessing a dictionary appear the same as accessing a list index
trying to access a non-existing key results in a Key Error
adding and changing values is as simple as assigning a new key to a value or an existing key to a new value
delete a key using del followed by accessing the key

In dictionaries.py, see:
examples of dictionaries
retrieving a value from a dictionary
adding a value to a dictionary
changing a value in a dictionary
deleting a value from a dictionary
numbers as keys make dicts looks like lists

you can create dictionaries on the fly, for instance, by creating an empty dictionary saved to a variable, and adding to it as you go
retrieve the value of a nested dictionary using the key of the outer dictionary that corresponds to a dictionary type, and also use the key of the inner dictionary corresponding to the value
retrieve the value of a nested list using the dictionary key that corresponds to a list type, and also use the list index of the value
In dictionaries.py, see:
create dictionaries on the fly
retrieve the value of a nested dictionary
retrieve the value of a nested list

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

In dictionaries.py, see:
examples of for loop with dictionaries
examples using in with dictionaries

Add more on built-in methods for dictionaries
