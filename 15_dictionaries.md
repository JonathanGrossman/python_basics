# Dictionaries 

A dictionary is a collection of comma-separated key:value pairs wrapped in curly braces `{}`. You can use a dictionary to store information. 

Oftentimes, you use a dictionary to store multiple properties for a single item. For instance, it is common to use a dictionary to store information about a user. A user dictionary might have keys for first name, last name, email, and other user information. 

```python
# example of a dictionary for a user
user_dict = {
    "first_name": "Elka",
    "last_name": "Cohen",
    "email": "elka@gmail.com",
}
```

Another example of using a dictionary is for a transaction. A transaction dictionary might have keys for seller, buyer, price, date purchase, and other transactional information. 

```python
# example of a dictionary for a transaction
transaction_dict = {
    "seller": "Sally",
    "buyer": "Billy",
    "price": "$15",
    "date": "October 21, 2020"
}
```
Users and transactions aren't the only things you use dictionaries for. Rather, they are just examples of things that have multiple properties for which a dictionary is a good choice for storing that information. In the discussion below, you will see more examples of dictionaries.

## [Keys vs index](#keys-vs-index)

Unlike lists, dictionaries do not have index positions. Instead of index positions, you use keys from the key:value pairs in dictionaries in order to do things like add, change, retrieve, and delete information from a dictionary.

Although almost anything can be a key (e.g., integer, float, Boolean, string, etc.), keys need to be unique (no duplicates) and immutable (can't be changed). It is probably most common to use a string as key. See the example of above where the keys are strings `'first_name'`, `'last_name'`, `'email'`, `'seller'`, `'buyer'`,`'price'`, `'date'`

If, however, you use numbers for your keys, it makes accessing a dictionary appear the same as accessing a list index.

```python
# define a list and a dict
list_of_string = ['Zero', 'One', 'Two']
numbes_as_keys = {
    0: 'Zero',
    1: 'One',
    2: 'Two'
}

# numbers as keys make dicts looks like lists
print(list_of_string[0])
print(numbes_as_keys[0])

>>> Zero
>>> Zero
```

In the example above, you define a list `list_of_string = ['Zero', 'One', 'Two']` and a dictionary `numbes_as_keys = {0: 'Zero', 1: 'One', 2: 'Two'}`. The dictionary has numbers as keys. Then you print the item at index position `0` from the list and then also print the value from the dictionary that has a key of `0`. In both cases, the syntax looks the same `list_of_string[0]` vs `numbes_as_keys[0]`. Both print statements print `Zero`. `Zero` is in index position `0` of the list and is also the value for the key `0` in the dictionary.

## [Creating a dictionary](#creating-a-dictionary)

You can create a dictionary using `{}` or use the built-in `dict()` function. The user and transction examples above create the dictionary using `{}`. Here is one more example.

```python
# example of a dictionary using {}
our_inventory = {
    'male_pants' : ['khakis', 'jeans', 'athletic pants'],
    'male_shirts' : [],
    'female_pants' : ['khakis', 'jeans', 'athletic pants'],
    'female_shirts' : ['tank-top', 'long-sleeve'],
}
```

Instead of using `{}`, you can use the `dict()` function to create a dictionary. The `dict()` accepts a sequence of tuples where each tuple contains a key:value pair. The resulting dictionary will be wrapped in curly braces. 

```python
# example of a dictionary using dict()
same_inventory = dict([
    ('male_pants', ['khakis', 'jeans', 'athletic pants']),
    ('male_shirts', []),
    ('female_pants', ['khakis', 'jeans', 'athletic pants']),
    ('female_shirts', ['tank-top', 'long-sleeve']),
])
```

Regardless of which approach you take, the result is the same.

```python
our_inventory = {
    'male_pants' : ['khakis', 'jeans', 'athletic pants'],
    'male_shirts' : [],
    'female_pants' : ['khakis', 'jeans', 'athletic pants'],
    'female_shirts' : ['tank-top', 'long-sleeve'],
}

same_inventory = dict([
    ('male_pants', ['khakis', 'jeans', 'athletic pants']),
    ('male_shirts', []),
    ('female_pants', ['khakis', 'jeans', 'athletic pants']),
    ('female_shirts', ['tank-top', 'long-sleeve']),
])

print("our inventory -> ", our_inventory)
print("same inventory -> ", same_inventory)

>>> ('our inventory -> ', {'male_pants': ['khakis', 'jeans', 'athletic pants'], 'female_shirts': ['tank-top', 'long-sleeve'], 'male_shirts': [], 'female_pants': ['khakis', 'jeans', 'athletic pants']})
>>> ('same inventory -> ', {'male_pants': ['khakis', 'jeans', 'athletic pants'], 'female_shirts': ['tank-top', 'long-sleeve'], 'male_shirts': [], 'female_pants': ['khakis', 'jeans', 'athletic pants']})
```

In the examples above, you create the first dictionary using `{}` and the second using `dict()` and the same key:values as the first dictionary. Printing the results of each returns the same thing.

## [Adding keys to a dictionary](#adding-keys-to-a-dictionary)

Adding a key:value pair to a dictionary is as simple as assigning a new key to a value. You can create dictionaries on the fly, for instance, by creating an empty dictionary saved to a variable, and adding to it as you go.

```python
the_inventory = {}
the_inventory['male_pants'] = ['khakis', 'jeans', 'athletic pants']
print(the_inventory)

the_inventory['male_shirts'] = []
print(the_inventory)

the_inventory['female_pants'] = ['khakis', 'jeans', 'athletic pants']
the_inventory['female_shirts'] = ['tank-top', 'long-sleeve']
print(the_inventory)
```
In the example above, first you create a variable named `the_inventory` and set it equal to an empty dictionary `{}`. Then you add a key of `'male_pants'` and set it equal to a list `['khakis', 'jeans', 'athletic pants']`. Next, you print `the_inventory`, which outputs the dictionary `{'male_pants': ['khakis', 'jeans', 'athletic pants']}`. The dictionary is no longer empty. 

Then you add a key of `'male_shirts'` and set it equal to an empty list `[]`. Next, you print `the_inventory` again, which outputs `{'male_pants': ['khakis', 'jeans', 'athletic pants'], 'male_shirts': []}`. Appearing in the dictionary are both key:value pairs that you added.

Finally, you add two more key:value pairs. First, a key of `'female_pants'` set equal to a list and a key of `'female_shirts'` also set equal to a list. Next, you print `the_inventory` again, which outputs `{'male_pants': ['khakis', 'jeans', 'athletic pants'], 'female_shirts': ['tank-top', 'long-sleeve'], 'male_shirts': [], 'female_pants': ['khakis', 'jeans', 'athletic pants']}`. Appearing in the dictionary are all four key:value pairs that you added.

Like lists, dictionaries are mutable and dynamic. This means that the keys and values can be edited and also you can add and remove keys:values from a dictionary. You also can nest a dictionary inside another dictionary. Do this by making one or more of the values a dictionary.

## [Changing values in a dictionary](#changing-values-in-a-dictionary)

Changing a value in a dictionary is as simple as assigning an existing key to a new value.

## [Retrieving keys in a dictionary](#retrieving-keys-in-a-dictionary)

## [Retrieving values in a dictionary](#retrieving-values-in-a-dictionary)

You can store a dictionary in memory as a variable and then retrieve a `value` from a dictionary by calling the value's `key`. You call the `key` using square brackets (`[]`) at the end of the name of the variable.

Trying to access a non-existing key results in a Key Error.

Retrieve the value of a nested dictionary using the key of the outer dictionary that corresponds to a dictionary type, and also use the key of the inner dictionary corresponding to the value

Retrieve the value of a nested list using the dictionary key that corresponds to a list type, and also use the list index of the value

## [Deleting keys from a dictionary](#deleting-keys-from-a-dictionary)

Delete a key and its corresponding value using the `del` keyword followed by accessing the key.

## [Dictionary Methods](#dictionary-methods)

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


