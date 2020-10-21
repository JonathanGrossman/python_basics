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
Docstring: `D.clear() -> None.  Remove all items from D.`  
Notes: removes all key:value pairs from dictionary

Method: .copy()  
Docstring: `D.copy() -> a shallow copy of D`  
Notes: copies the dictionary

Method: .fromkeys(k, v)  
Docstring: `dict.fromkeys(S[,v]) -> New dict with keys from S and values equal to v. v defaults to None.`  
Notes: returns a dict (takes in 2 args - first = keys, second = values)

Method: .get(key)  
Docstring: `D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.`  
Notes: gets value for specified key; returns None if no such key

Method: .has_key()  
Docstring: `D.has_key(k) -> True if D has a key k, else False`  
Notes: checks if dictionary has key; returns a Boolean

Method: .items()  
Docstring: `D.items() -> list of D's (key, value) pairs, as 2-tuples`  
Notes: returns a list of tuples containing the key-value pairs

Method: .iteritems()  
Docstring: `D.iteritems() -> an iterator over the (key, value) items of D`  
Notes: returns an iterator over the dictionary's keys and values

Method: .iterkeys()  
Docstring: `D.iterkeys() -> an iterator over the keys of D`  
Notes: returns an iterator over the dictionary's keys

Method: .itervalues()  
Docstring: `D.itervalues() -> an iterator over the values of D`  
Notes: returns an iterator over the dictionary's values

Method: .keys()  
Docstring: `D.keys() -> list of D's keys`  
Notes: returns a list of keys

Method: .pop(key, default)  
Docstring: `D.pop(k[,d]) -> v, remove specified key and return the corresponding value. If key is not found, d is returned if given, otherwise KeyError is raised`  
Notes: removes key and returns value/default; error if no such key

Method: .popitem()  
Docstring: `D.popitem() -> (k, v), remove and return some (key, value) pair as a
2-tuple; but raise KeyError if D is empty.`  
Notes: removes last key:value pair and returns it as tuple

Method: .setdefault()  
Docstring: `D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D`  
Notes: sets the default to be returned if a key doesn't exist when trying to access that key

Method: .update(obj)  
Docstring: `D.update([E, ]**F) -> None. Update D from dict/iterable E and F. If E present and has a .keys() method, does: for k in E: D[k] = E[k] If E present and lacks .keys() method, does: for (k, v) in E: D[k] = v. In either case, this is followed by: for k in F: D[k] = F[k]`  
Notes: merges dictionaries or dict with sequence of key:value pairs

Method: .values()  
Docstring: `D.values() -> list of D's values`  
Notes: returns a list of values

Method: .viewitems()  
Docstring: `D.viewitems() -> a set-like object providing a view on D's items`  
Notes: returns list of tuples where each tuple contains a key:value pair

Method: .viewkeys()  
Docstring: `D.viewkeys() -> a set-like object providing a view on D's keys`  
Notes: returns a list of keys

Method: .viewvalues()  
Docstring: `D.viewvalues() -> an object providing a view on D's values`  
Notes: returns a list of values


## [Dictionary and for loop](#dictionary-and-for-loop)
In dictionaries.py, see:
examples of for loop with dictionaries

## [Dictionary in expressions](#dictionary-in-expressions)
examples using in with dictionaries


