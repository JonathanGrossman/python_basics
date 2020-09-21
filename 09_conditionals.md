# Conditionals.
Conditional statements allow you to control the flow of your application, which otherwise will read every line sequentially, meaning one after the next from top to bottom. Conditional statements are used to skip over lines of code, repeat blocks of code, or choose between different code blocks
Here we cover if, else, elif, conditional expressions, and pass. Later we will discuss other ways to control application flow

if evaluates the specified object’s or expression’s truthiness
an if expression consists of if, an expression, a colon (:), and a statement (which appears on the following line and must be indented)
when the if expression is truthy, the statement is executed; when falsy, the statement is not executed
indentation matters! lines are considered in the same block of code when they have the same indentation; can nest blocks of code
In conditionals.py, see
if statement basic examples

elif and else are used in combination with if and one another to control flow
your code “makes decision” on which block or blocks to run based on truthiness of the conditions set
you can use an if / else pattern or if / elif . . . elif /else
like if, a condition follows elif and runs its code block only if the condition is True 
in contrast, else has no condition and runs only if all the preceding code blocks in the if / elif / else blocks are False

you must have an if statement, but the elif and else statements are optional
you can have as many elif statements as you want but you can have only one else statement
the if / elif / else blocks run until the interpreter reaches the first truthy block, then skips over the remaining blocks
if no truthy blocks and no else, none of the blocks run
In conditionals.py, see
elif and else statement basic examples

conditional expressions act like operators
conditional expressions look similar to if statements but are different because they do not control program flow
<when_condition_true> if <condition> else <when_condition_false>
conditional expressions are read in a non-intuitive order
	Reads condition
If condition true, runs code preceding if
If condition false, runs code following else

see Conditional Expressions (Python’s Ternary Operator) here for more details

In conditionals.py, see
conditional expressions basic examples

Python’s pass statement tells the interpreter to skip ahead to the next line of code
commonly used in development when you want to put a placeholder block of code, yet you don’t want your code to break

In conditionals.py, see
pass statement basic examples
