# Conditionals

Conditional blocks are blocks of code that run only if a defined condition exists. For instance, `if pant_size = 2: print(pant_size)`. The line of code prints `pant_size` only if its value is `2`. Otherwise, the Python interpreter does nothing but move onto the next line. 

Because the Python interpreter reads your .py files from top to bottom in sequential order, you can use conditional statements to control the flow of your application. Use conditional statements to do things like skip over lines of code, repeat blocks of code, or choose between different code blocks.

The chapter discusses how to use `if`, `else`, and `elif` to write conditional expressions that check the truthiness of a Python object or expression. If the conditional expression is met, the Python interpreter reads and executes the corresponding block of Python code (the expression's statement). If the conditional expression is not met, the Python interpreter does not read or execute the corresponding block of Python code. The chapter also dicusses the `pass` statement.


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

Indentation matters! If the `if` expression's statement appears on the following line but is not indented, the Python interpreter has an Indentation error `IndentationError: expected an indented block`. Indentation matters because that is how the Python interpreter knows which lines of code make up a block of code that belong together. Lines are considered in the same block of code when they have the same indentation. Here the error means that the `if` and `print` statements are in the same block of code when they really shouldn't be. If the `print` statement immediately follows the `if` statement, then the `print` statement should be indented.

```python
# example of indentation error
if True: 
print(True)
    
>>> IndentationError: expected an indented block


```
So far this discussion has used statements that are only one line. A one-line block of code. Here is an example of an intended block of code consisting of more than one line.

```python
# example of statement on line following if expression
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
    pants = 12
    shirts = 10
    inventory = pants + shirts
    if inventory > 20:
	    price = 9.99
	    total_sale = inventory * price
	    print(total_sale)
    
>>> 219.78
```

The first block is four lines. The first three lines in the statement define `pants`, `shirts`, and `inventory`. The fourth checks if `inventory` is greater than `20`. If `True`, the second block runs. It consistes of three lines. The first two lines define `price` and `total_sale`. The third line prints `total_sale`. Notice that what separates the two blocks of code from one another is the indentation.

You can use multiple `if` statements in a single block of code. When `if` statements appear in the same block, the Python interpreter runs the statement for the first one whose condition is met. Subsequent `if` statements in the same block are not read. The examples below each have three `if` statements. The top one checks if `inventory` is greater than 20. The next checks if `inventory` is less than or equal to `20`. The last checks if `inventory` equals `0`. Reading from top to bottom, the Python interpreter will run the corresponding statement for the first `if` statement that is `True`. If none are `True`, none are run.

```python
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

>>> Not part of if block
```

## elif and else
elif and else are used in combination with if and one another to control flow
your code “makes decision” on which block or blocks to run based on truthiness of the conditions set
you can use an if / else pattern or if / elif . . . elif /else
like if, a condition follows elif and runs its code block only if the condition is True 
in contrast, else has no condition and runs only if all the preceding code blocks in the if / elif / else blocks are False

you must have an if statement, but the elif and else statements are optional
you can have as many elif statements as you want but you can have only one else statement
the if / elif / else blocks run until the interpreter reaches the first truthy block, then skips over the remaining blocks
if no truthy blocks and no else, none of the blocks run

```python
# elif and else statement basic examples
# if q:
#     print("yes, q")
# else:
#     print("no q")


# if r:
#     print("yes, r")
# else:
#     print("no, r")


# if r:
#     print("yes, r")
# elif q or r:
#     print("q or r")
# else:
#     print("no, q or r")


# if r:
#     print("yes, r")
# elif r == 10:
#     print("r equals 10")
# elif q or r:
#     print("q or r")
# else:
#     print("no, q or r")
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
