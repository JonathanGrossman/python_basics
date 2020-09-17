# Data Types

Like many other programming languages, Python categorizes data into several different data types. For instance, numbers, text, Boolean, sequence, mapping, set, and binary are Python data types. Essentially, data types are categories for data. 

Each piece of data falls into one of the Python categroeis, and the category that the data is in determines what kind of operations you can do with that data. For instance, text is iterable but numbers are not. Because text is iterable, you can loop through it to access each letter in the text. You can't do that with numbers.

When writing Python code, you don't have to explicitly declare what type a variable represents. Rather, the Python intepreter will check the type of a variable when the interpreter runs.

Let's look at some examples.

## Numeric
int: x = 100  
float: y = 100.1  
complex: z = 10j  
 
## Text
str: x = "Israel Tech Challenge"  

## Boolean
bool: x = True  

## Sequence
list: x = \["Israel", "Tech", "Challenge"]  
tuple: x = ("Israel", "Tech", "Challenge")  
range: x = range(100)  

## Mapping
dict: x = {"name" : "ITC", "success" : True}  

## Set
set: x = {"Israel", "Tech", "Challenge"}  
frozenset: x = frozenset({"Israel", "Tech", "Challenge"})  

## Binary
bytes: x = b"Hello"  
bytearray: x = bytearray(5)  
memoryview: x = memoryview(bytes(5))  


If you want to determine what type a value is, you can use type()  
For instance, before adding a number to a variable, you may want to make sure the variable is also a number  
For instance, before trying to loop through a variable, you may want to confirm it is iterable  

## Examples of data types  

```python
a = int(100)  
b = float(100.1)  
c = str("Israel Tech Challenge")  
d = list(("Israel Tech Challenge"))  
e = tuple(("Israel Tech Challenge"))  
f = range(100)  
g = dict(name="ITC", success=True)  
h = set(("Israel Tech Challenge"))  
i = bool(100) # True; x = bool(0) => False  
j = bytes(100)  
```

```python
print(a, type(a))  
print(b, type(b))  
print(c, type(c))  
print(d, type(d))  
print(e, type(e))  
print(f, type(f))  
print(g, type(g))  
print(h, type(h))  
print(i, type(i))  
print(j, type(j))  
```

## Examples of variables

You must assign a variable a value before you can use the variable  
```python
j = 10  
print(j)
```


You can change the value of a variable (hence the meaning of “variable”)  
```python
j = 20    
print(j)  
```

You can set variables equal to any data type  
```python
g = "this is a letter"   
print(g)  
```

You can assign a variable to a variable  
```python
j = g    
print(j)
```


You can set multiple variables in one expression  
```python
a, b, c = 1, 2, 3    
print(a)  
print(b)  
print(c)  
```

If a variable is assigned a value, you can use it
```python
k = 12  
print(k + 1)  
print(k)  
```

If you have not assigned a value to a variable, you can't use it  
```python
k = k + 1  
print(k)  
```

None is a value  
```python
print(type(None))  
```





