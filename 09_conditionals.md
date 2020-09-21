# Conditionals.
Conditional statements allow you to control the flow of your application, which otherwise will read every line sequentially, meaning one after the next from top to bottom. Conditional statements are used to skip over lines of code, repeat blocks of code, or choose between different code blocks
Here we cover if, else, elif, conditional expressions, and pass. Later we will discuss other ways to control application flow

if evaluates the specified object’s or expression’s truthiness
an if expression consists of if, an expression, a colon (:), and a statement (which appears on the following line and must be indented)
when the if expression is truthy, the statement is executed; when falsy, the statement is not executed
indentation matters! lines are considered in the same block of code when they have the same indentation; can nest blocks of code

```python
q = 5
r = 0
s = 8
t = 5

# if statement basic examples
# if q:
#     print("yes, q")


# if r:
#     print("yes, r")


# if q > r:
#     print("yes, q > r")


# if q == r:
#     print("yes, q = r")


# if t is q:
#     print("yes, t is q")    


# if q and s:   
#     print('q and s are both truthy') 
#     print('q is ' + str(q))
#     print('s is ' + str(s))  
    
#     if q > s:                      
#         print('q is greater than s')

#     print('phew, all this math; need a break')

#     if q < s:                      
#         print('q is less than s')    
# print('Not part of if block')
```

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
