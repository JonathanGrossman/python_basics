# Conditionals

Conditional blocks are blocks of code that run only if a defined condition exists. A conditional block starts with a conditional expression that checks whether a condition is `True` and is followed by a statement. For instance, the conditional block is `if pant_size = 2: print(pant_size)`. The conditional expression is `if pant_size = 2:`. The condition the expression is checking is whether `pant_size` equals `2`. The statement is `print(pant_size)`. The line of code prints `pant_size` only if its value is `2`. Otherwise, the Python interpreter does nothing but move onto the next line. 

Because the Python interpreter reads your .py files from top to bottom in sequential order, you can use conditional statements to control the flow of your application. Use conditional statements to do things like skip over lines of code, repeat blocks of code, or choose between different code blocks.

The chapter discusses how to use `if`, `else`, and `elif` to write conditional expressions that check the truthiness of a Python object or expression. If the conditional expression is met, the Python interpreter reads and executes the corresponding block of Python code (the expression's statement). If the conditional expression is not met, the Python interpreter does not read or execute the corresponding statement. The chapter also dicusses the `pass` statement.


## if

An `if` expression evaluates whether a Python object or expression is truthy. If the expression is truthy, the Python interpreter reads the the `if` expression's corresponding statement. If the expression is falsy, the Python interpreter does not read the corresponding statement. 

An `if` expression consists of `if`, an expression, and a colon (`:`). A statement must follow an `if` expression. A statement can be any valid Python code. The statement can be on the same line as the  expression.

```python
# example of if and statement on same line
if True: print(True)

>>> True
``` 

It is more common, however, for the statement to appear on the line following the `if` expression. When on the subsequent line, the statement must be indented.

```python
# example of statement on line following if expression
if True: 
    print(True)
    
>>> True
```
If your `if` expression does not have a statement, the Python interpreter will experience a Syntax error `SyntaxError: unexpected EOF while parsing`.

```python
# example of syntax error
if True: 
   
>>> SyntaxError: unexpected EOF while parsing
```

Indentation matters! If the `if` expression's statement appears on the following line but is not indented, the Python interpreter has an Indentation error `IndentationError: expected an indented block`. 

```python
# example of indentation error
if True: 
print(True)
    
>>> IndentationError: expected an indented block
```

Indentation matters because that is how the Python interpreter knows which lines of code make up a block of code that belong together. Lines are considered in the same block of code when they have the same indentation. Here the error means that the `if` and `print` statements are in the same block of code when they really shouldn't be. If the `print` statement immediately follows the `if` statement, then the `print` statement should be indented.


So far this discussion has used statements that are only one line. A one-line block of code. Here is an example of an indented block of code consisting of more than one line.

```python
# example of multi-line statement block of code
if True: 
    pants = 12
    shirts = 10
    inventory = pants + shirts
    price = 9.99
    total_sale = inventory * price
    print(total_sale)
    
>>> 219.78
```

You can nest blocks of code. The example below has two blocks of code.

```python
# example of statement on line following if expression
if True: 
    # first block of code
    pants = 12
    shirts = 10
    inventory = pants + shirts
    if inventory > 20:
            # second block of code
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale)
    
>>> 219.78
```

The first block is four lines. The first three lines in the statement define `pants`, `shirts`, and `inventory`. The fourth checks if `inventory` is greater than `20`. If `True`, the second block runs. It consistes of three lines. The first two lines define `price` and `total_sale`. The third line prints `total_sale`. Notice that what separates the two blocks of code from one another is the indentation.

You can use multiple `if` statements in a single block of code. When `if` statements appear in the same block, the Python interpreter runs the statement for the first one whose condition is met. Subsequent `if` statements in the same block are not read. The examples below each have three `if` statements. The top one checks if `inventory` is greater than 20. The next checks if `inventory` is less than or equal to `20`. The last checks if `inventory` equals `0`. Reading from top to bottom, the Python interpreter will run the corresponding statement for the first `if` statement that is `True`. If none are `True`, none are run.

```python
# example of multiple if statements
if True: 
    pants = 12
    shirts = 10
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    if inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    if inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 219.78 We have plenty more!
```
The code above prints `219.78 We have plenty more!` because inventory is greater than `20`.

```python
if True: 
    pants = 2
    shirts = 1
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    if inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    if inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 17.97 Running low.
```
The code above prints `17.97 Running low.` because inventory is less than and not equal to `20`.

```python
if True: 
    pants = 0
    shirts = 0
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    if inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    if inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 0 None in inventory.
```
The code above prints `0 None in inventory.` because inventory is equal to `0`.

```python
if True: 
    pants = -1
    shirts = 0
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    if inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    if inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")
```
The code above prints nothing because `inventory` is none of the `if` statements evaluate to `True`. You owe someone a pair of pants.

For reference, here are additional simple examples of `if` statements.

```python
q = 5
r = 0
s = 8
t = 5

# if statement basic examples
if q:
    print("yes, q")
    
>>> yes, q

if r:
    print("yes, r")


if q > r:
    print("yes, q > r")

>>> yes, q > r

if q == r:
    print("yes, q = r")


if t is q:
    print("yes, t is q")    

>>> yes, t is q

if q and s:   
    print('q and s are both truthy') 
    print('q is ' + str(q))
    print('s is ' + str(s))  
    
    if q > s:                      
        print('q is greater than s')

    print('phew, all this math; need a break')

    if q < s:                      
        print('q is less than s')    
print('Not part of if block')


>>> q and s are both truthy
>>> q is 5
>>> s is 8

>>> phew, all this math; need a break

>>> q is less than s

>>> 'Not part of if block'
```

## elif and else

Like `if` expressions, `elif` and `if` each evaluate whether a Python object or expression is truthy. `elif` and `else` statements are optional when using an `if` expression and you cannot use either of them without a preceding `if` expression. In other words, only if you use an `if` expression can you use an `elif` or `else` expression, but you don't have to use either just by using an `if`. The `if / elif / else` blocks run until the interpreter reaches the first truthy block. The interpreter then skips over the remaining corresponding blocks. If none of the conditional expressions are truthy, none of the statements run unless there is an `else` statement, in which case it runs.

Think of it as though an `if` statement can have, but doesn't have to have, corresponding `elif` and `else` statements. Similar to how you saw above with multiple `if` statements, use combinations of `if`, `elif`, and `else` to control how the Python interpreter reads your code. Essentially, write your code so that it "makes decisions" on which block or blocks to run based on truthiness of the conditions set.

When using `elif` statements, any `elif` expressions must come after an `if` or `elif`. If there is a corresponding `else` to the `if`, the `elif` statements must come before the `else`. So any and all `elif` blocks come after the `if` but before any `else`. 

Like `if` statements, `elif` expressions have a condition and a statement. If the condition is truthy, the statement runs. You can have as many `elif` statements in a row as the memory allows. But be sure that the rest of us humans can understand your code. It is not required that you have any `elif` statements.

It is also not required that an `if` expression have a corresponding `else` statement. If it does, the `else` must appear after the `if` and after any and all `elif` expressions. The `else` expression has a statement but no explicit condition. Its condition is implicit. Its statement runs if all the corresponding `if` and `elif` expressions are falsy. You can have only one `else` for each `if`. 

Here are some commone patterns: 

- `if` only 
- `if / else` 
- `if / elif / else` 
- `if / elif . . . elif /else` where `. . .` represents additional `elif` expressions

Here are examples.

```python
if True: 
    pants = 12
    shirts = 10
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    elif inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    else inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 219.78 We have plenty more!
```
The code above prints `219.78 We have plenty more!` because the `if` condition is `True`.

```python
if True: 
    pants = 2
    shirts = 1
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    elif inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    else inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 17.97 Running low.
```
The code above prints `17.97 Running low.` because the `if` condition is `False` and `elif` condition is `True`.

```python
if True: 
    pants = 0
    shirts = 0
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    elif inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    else inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 0 None in inventory.
```
The code above prints `0 None in inventory.` because the `if` and `elif` conditions are `False`.

```python
if True: 
    pants = -1
    shirts = 0
    inventory = pants +  shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale, "We have plenty more!")
    elif inventory <= 20 and inventory > 0:
	    price = 5.99
	    total_sale = inventory * price
	    print(total_sale, "Running low.")
    else inventory == 0:
	    price = 0
	    total_sale = inventory * price
	    print(total_sale, "None in inventory.")

>>> 0 None in inventory.
```
The code above has its inventory at `-1`. Like the `if` example above, you owe someone a pair of pants! Instead of printing nothing like above where none of the `if` expressions accounted for negative `inventory`, the code above prints `0 None in inventory.`. This difference occurs becuase `else` acts as a catchall, whereas the `if` conditions in the previous example have explicit conditions. The `else` expression's condition for running is implicit. That condition is whether all the conditions above it are falsy. Here they are all falsy, so it prints `0 None in inventory.`.

Here are additional basic examples of `elif` and `else` blocks.

```python
# elif and else statement basic examples
if q:
    print("yes, q")
else:
    print("no q")

>>> "yes, q"

if r:
    print("yes, r")
else:
    print("no, r")

>>> "no, r"

if r:
    print("yes, r")
elif q or r:
    print("q or r")
else:
    print("no, q or r")

>>> "q or r"

if r:
    print("yes, r")
elif r == 10:
    print("r equals 10")
elif q or r:
    print("q or r")
else:
    print("no, q or r")

>>> "q or r"
```

## Conditional Expressions

conditional expressions act like operators
conditional expressions look similar to if statements but are different because they do not control program flow
<when_condition_true> if <condition> else <when_condition_false>
conditional expressions are read in a non-intuitive order
	Reads condition
If condition true, runs code preceding if
If condition false, runs code following else

see Conditional Expressions (Python’s Ternary Operator) here for more details

```python
# conditional expressions basic examples
# print("q > r") if q > r else print("q is not greater than r")
# print("r > q") if r > q else print("r is not greater than q")

# conditional expressions can simplify your code; see comparison below
# if r < q:
#     r += q
#     print(r)
# else:
#     r
#     print(r)

# r += q if r < q else r
# print(r)
```

## Pass

Python’s pass statement tells the interpreter to skip ahead to the next line of code
commonly used in development when you want to put a placeholder block of code, yet you don’t want your code to break

```python
# pass statement basic examples
# error results "expected an indented block"
# if r < q:
   

# no error
# if r < q:
#     pass
```
