# Dictionaries

A dictionary is a collection of comma-separated key:value pairs wrapped in curly braces `{}`. You can use a dictionary to store information. Oftentimes, a dictionary is used to store multiple properties for a single item. For instance, it is common to use a dictionary to store information about a user. A user dictionary might have keys for first name, last name, email, and other user information. Another example of using a dictionary is for a transaction. A transaction dictionary might have keys for seller, buyer, price, date purchase, and other transactional information. 

A dictionary wraps its content in curly braces `{}`. You can create a dictionary using `{}` or use the built-in `dict()` function. The `dict()` function accepts a sequence of tuples where each tuple contains a key:value pair. You can create dictionaries on the fly, for instance, by creating an empty dictionary saved to a variable, and adding to it as you go.

Like lists, dictionaries are mutable and dynamic. This means that the keys and values can be edited and also you can add and remove keys:values from a dictionary. You also can nest a dictionary inside another dictionary. Do this by making one or more of the values a dictionary.

## [Dictionary keys](#dictionary-keys)

Unlike lists, dictionaries are not accessed by index. Instead, you use keys to access the contents inside a dictionary. Although almost anything can be a key (e.g., integer, float, Boolean, string, etc.), keys need to be unique (no duplicates) and immutable (can't be changed). It is probably most common to use a string as key. If, however, you use numbers for your keys, it makes accessing a dictionary appear the same as accessing a list index.

You can store a dictionary in memory as a variable and then retrieve a `value` from a dictionary by calling the value's `key`. You call the `key` using square brackets (`[]`) at the end of the name of the variable.

Trying to access a non-existing key results in a Key Error.

Adding and changing values is as simple as assigning a new key to a value or an existing key to a new value

Delete a key and its corresponding value using the `del` keyword followed by accessing the key.

Retrieve the value of a nested dictionary using the key of the outer dictionary that corresponds to a dictionary type, and also use the key of the inner dictionary corresponding to the value

Retrieve the value of a nested list using the dictionary key that corresponds to a list type, and also use the list index of the value

## [Dictionary Methods](dictionary-methods)

Dictionaries have built-in methods you can use that help you work with dictionaries. To see the available methods, enter the following in your terminal `print(dir({}))`. You should see the following output in the terminal. The items without `__` in their names are the methods for dictionaries.

```python
['__class__', '__cmp__', '__contains__', '__delattr__', '__delitem__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'has_key', 'items', 'iteritems', 'iterkeys', 'itervalues', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values', 'viewitems', 'viewkeys', 'viewvalues']
```
Here is a list of those methods, their docstring, and a short note from me.
 
Method: .clear()  
Docstring:
Notes: removes all key:value pairs from dictionary

Method: .copy()  
Docstring:
Notes:

Method: .fromkeys(<k>, <v>)  
Docstring:
Notes: returns a dict (takes in 2 args - first = keys, second = vals)

Method: .get(<key>)  
Docstring:
Notes: gets value for specified key; returns None if no such key

Method: .has_key()  
Docstring:
Notes:

Method: .items()  
Docstring:
Notes: returns a list of tuples containing the key-value pairs

Method: .iteritems()  
Docstring:
Notes:

Method: .iterkeys()  
Docstring:
Notes:

Method: .itervalues()  
Docstring:
Notes:

Method: .keys()  
Docstring:
Notes: returns a list of keys

Method: .pop(<key>, default)  
Docstring:
Notes: removes key and returns value/default; error if no such key

Method: .popitem()  
Docstring:
Notes: removes last key:value pair and returns it as tuple

Method: .setdefault()  
Docstring:
Notes:

Method: .update(<obj>)  
Docstring:
Notes: merges dictionaries or dict with sequence of key:value pairs

Method: .values()  
Docstring:
Notes: returns a list of values

Method: .viewitems()  
Docstring:
Notes:

Method: .viewkeys()  
Docstring:
Notes:

Method: .viewvalues()  
Docstring:
Notes:


## [Dictionary and for loop](#dictionary-and-for-loop)
In dictionaries.py, see:
examples of for loop with dictionaries

## [Dictionary in expressions](#dictionary-in-expressions)
examples using in with dictionaries


