# Operators and Expressions

Operators and expressions are critical for allowing your application to “make decisions” as it runs. **Operators** are symbols that perform some sort of function. For instance, the addition symbol `+` is an arithmetic operator. **Operands** are the values on which the operator performs its function. For example, if you add two numbers together, the numbers are the operands. The numbers can be the literal number (e.g., `5`) or a variable that has a number value (e.g., `sale_price`). 

An **expression** is a sequence of operators and operands. For instance, `total_price = sale_price + sale_price * 0.15` is an expression.  

Your Python code will will no doubt contain operators and expressions because you will need to control the flow of your application. This chapter discusses in detail the following types of operators:

- arithmetic operators   
- comparison operators  
- logical operators  
- identity operators  

## Arithmetic Operators

One category of operator is arithmetic. You use arithmetic operators with number operands to write algebraic expressions. Using arithmetic operators, you can add, subtract, divide, multiply, and perform other algebraic operations. For instance, you can multiply a `sale_price` by a tax of `.15` and add the resulting value to the `sale_price` to get the `total_price`.

```python
# example of arithmetic operators
sale_price = 100
total_price = sale_price + sale_price * 0.15
```
In the example above, first `sale_price` is set to 100. Next, the code multiplies `sale_price` by `0.15`. Then the code adds the product of that multiplication operation to `sale_price` and sets the sum of the addition operation equal to `total_price`. Like in algebra, the order of operations in the expression above prioritized the multiplication operation before the addition operation. 

One thing that makes math with Python easier is that you don't have to learn special "Python math". Arithmetic operators are very similar to regular algebra. In other words, you can work with algebra in Python similar to how you would on a calculator.

Examples of arithmetic operators in Python are Add ( `+` ), Subtract ( `-` ), Multiply ( `*` ), Divide ( `/` ), Modulo ( `%` ), Integer division (`//`), and Exponentiation ( `**` ). See examples below for each.

Add ( `+` )
```python
# example of adding
print(4 + 8)

>>> 12
```

Subtract ( `-` )
```python
# example of subtracting
print(9 - 5)

>>> 4
```

Multiply ( `*` )
```python
# example of multiplying
print(9 * 5)

>>> 45
```

Divide ( `/` )
```python
# example of dividing
print(9 / 5)

>>> 1.8
```

Modulo ( `%` ) 
```python
# example of getting the remainder from division
print(9 % 5)

>>> 4
```

Integer division (`//`)
```python
# example of integer division, which returns an int and rounds down
print(10 // 3) 

>>> 3
```

Exponentiation ( `**` )
```python
# example of exponentiation (raising 4 to the power of 8)
print(4 ** 8)

>>> 65536
```
A few notes to help you use the arithmetic operators. Like we saw above in the `total_price` example, you can write expressions that have more than one arithmetic operator. For expressions that have more than one arithmetic operator, the order of operations in Python are the same as in algebra. 

```python
# variable definitions
a = 9
b = 7
c = 3 

# examples of order of operations
print(a + b * c)

>>> 30


print((a + b) * c)

>>> 48
```
In the code above, the first expression goes in a different order than the second. In the first, the expression multiples `b` by `c` and adds the product to `a`. In the second, becuase `a + b` is wrapped in `( )`, the expression adds `a` to `b` and then multiplies the sum by `c`. The different order of operations results in different outcomes.

When using division or integer division in Python, be aware of the nuances of how those operators work. The result of division (`/`) is a float regardless of whether operands are both integers, both floats, or a mixture of the two.  

```python
# examples of numbers
number_of_shirts = 10.0   # float
number_of_pants = 10       # int

# adding a float to an int returns a float
print(number_of_shirts + number_of_pants)

>>> 20.0

total_price_shirts = 40.0   # float
number_of_shirts = 10       # int

# dividing a float by an int returns a float
print(total_price_shirts / number_of_shirts)

>>> 4.0
```

If you want the result to be an `int`, use Python's built-in `int()` function to convert the result. Beware that `int()` rounds down.

```python
# using int() to get integer sum
number_of_shirts = 10.0   # float
number_of_pants = 10       # int

sum = int(number_of_shirts + number_of_pants)
print(sum)

>>> 20

# using int() to get integer division product
total_price_shirts = 40.0   # float
number_of_shirts = 10       # int

product = int(total_price_shirts / number_of_shirts)
print(product)

>>> 4

# using int() rounds down (here, from 3.9 to 3)
total_price_shirts = 39.0   # float
number_of_shirts = 10       # int

product = int(total_price_shirts / number_of_shirts)
print(product)

>>> 3
```

The result of floor division (`//`) is rounded down. If positive this means the decimal is truncated. If negative, this means the absolute value of the number is rounded up resulting in a more negative number → `- 2.7` is rounded to `3`).  

```python
# examples of numbers
total_price_shirts = 7.9    # float
number_of_shirts = 3  # int
price_discount = -7.9 # float

# examples of floor division
print(total_price_shirts / number_of_shirts)
print(total_price_shirts // number_of_shirts)

>>> 2.6333333333333333
>>> 2.0

print(price_discount / number_of_shirts)
print(price_discount // number_of_shirts)

>>> -2.6333333333333333
>>> -3.0
```

Python has syntax shortcuts you can use to make your code more efficient. For instance, you can use `+=` or `-+` or `*=` as shorthand in expressions. Writing `x += 10` is the same as writing `x = x + 10`. Get used to seeing this shorthand in other people's code becuase it is common for developers to use this shorthand.

```python
# example using += as shorthand
starting_number = 1
starting_number += 10
print(starting_number)

>>> 11
```

## Comparison Operators

Comparison operators check whether an expression is `True` or `False`. You use comparison operators with operands (usually of type number, string, or Boolean) to write Boolean expressions. Using Boolean expressions, you direct the flow of your Python application. You check whether a condition is `True` or `False`:

```python
# example of checking whether a condition is True
if total_price > 100:
  ...
```
The code above checks whether `total_price` is greater than `100`. After checking whether the expression containing `total_price` evaluates to `True`, you can direct your Python application to do something.

```python
# example of doing something if condition is True
if total_price > 100:
  shipping_cost = 0

```
In the code above, if `total_price` is greater than 100, then `shipping_cost` equals `0`. You can add an else statement to handle what happens if `total_price` is not greater than 100.

```python
# example of adding an else statement to handle False
if total_price > 100:
  shipping_cost = 0
else:
  shipping_cost = 4.99

```
In the code above, if `total_price` is equal to or less than 100, then `shipping_cost` equals `4.99`. This is just one example of using Boolean expressions containing comparison operators to direct the flow of your application. For more information, see the conditional statements chapter and examples in my other Python project lessons.

Comparison operators include Equal To ( `==` ), Not Equal To ( `!=` ), Greater Than ( `>` ), Less Than ( `<` ), Greater Than or Equal To ( `>=` ), and Less Than or Equal To ( `<=` ).  Here are examples of each.

```python
# variable definitions for the examples below
a = 9
b = 7
c = 3
```

Equal To ( `==` )
```python
# example of equal to
print(a == c)

>>> False
```


Not Equal To ( `!=` )
```python
# example of not equal to
print(c != b)

>>> True
```


Greater Than ( `>` )
```python
# example of greater than
print(c > b)

>>> False
```

Less Than ( `<` )
```python
# example of less than
print(c < b)

>>> True
```

Greater Than or Equal To ( `>=` )
```python
# example of greater than or equal to
print(c >= b)

>>> False
```

Less Than or Equal To ( `<=` )
```python
# example of less than or equal to
print(c <= b)

>>> True
```
Complex Expression
```python
# example of a complex expression using comparison and arithmetic operators
# adds c + 4 and then compares left to right side of <=
print(b <= c + 4)

>>> True
```

Be careful when comparing floats because the stored value of the float might be more precise than you realize. Some practices for comparing floats include checking whether they are close in value or round the floats to the same decimal place before comparing them.

## Logical Operators

Logical operators check whether an expression is `True` or `False`. The logical operators are `not`, `or`, and `and`. Like comparison operators, you use logical operators with operands (of virtually any data type) to write Boolean expressions. Using Boolean expressions, you direct the flow of your Python application. You check whether a condition is `True` or `False`:

```python
# example of checking whether a condition is True
inventory = ['jeans', 'khakis', 'shorts, `swimsuit`]
selected_pants = 'jeans'
shopping_cart = []
if selected_pants and inventory:
  ...
```
The code above creates a variable called `inventory`. The `inventory` variable is set equal to a list that has four items. The next line creates a variable called `selected_pants` and sets it equal to a string `jeans`. Then the next line creates a variable called `shopping_cart` and sets it equal to an empty list `[]`. The following line checks if `selected_pants` is `True` and if `inventory` is `True`. After checking whether both items in the expression evaluate to `True`, you can direct your Python application to do something.

```python
# example of doing something if condition is True
inventory = ['jeans', 'khakis', 'shorts', 'swimsuit']
selected_pants = 'jeans'
shopping_cart = []
if selected_pants and inventory:
  shopping_cart.append(selected_pants)

print(shopping_cart)

>>> ['jeans']  

```
In the code above, if `selected_pants` is `True` and if `inventory` is `True`, then you add to the `shopping_cart` the `selected_pants`. Here both conditions are `True` because neither are empty values. `selected_pants` is equalt to `'jeans'` (not an empty string) and `inventory` is a list containing four items (not an empty list). 

You can add an else statement to handle what happens if `selected_pants` or `inventory` is not `True`. In the example below, instead of being equal to `'jeans'`, `selected_pants` is equal to and empty string (`''`).

```python
# example of doing something if condition is False
inventory = ['jeans', 'khakis', 'shorts', 'swimsuit']
selected_pants = ''
shopping_cart = []
if selected_pants in inventory:
  shopping_cart.append(selected_pants)
else:
  print('no pants selected')

print(shopping_cart)

>>> soccer shorts not in inventory
>>> []

```
In the code above, if `selected_pants` or `inventory` is not `True`, then the script prints a message saying that `'no pants selected'` and also prints an empty list. This is just one example of using Boolean expressions containing logical operators to direct the flow of your application. For more information, see the conditional statements chapter and examples in my other Python project lessons.


Here are a few examples of the logical operators.

```python
# examples of logical operators
pants_female = 8
pants_male = 9

# not
print(not pants_female < 10) # pants_female is less than 10, so that expression is True; meaning not that expression is False
print(not pants_female > 10) # pants_female is not greater than 10, so that expression is False; meaning not that expression is True

>>> False
>>> True


# or
print(pants_female > 10 or pants_male < 10) # at least one of the expressions is True, so returns True
print(pants_female > 10 or pants_male > 10) # neither expressions is True, so returns False

>>> True
>>> False


# and
print(pants_female > 10 and pants_male < 10) # at least one of the expressions is False, so returns False
print(pants_female < 10 and pants_male < 10) # both expressions are True, so returns True

>>> False
>>> True
```


When using logical operators to compare non-Boolean objects and expressions, such as numbers, strings, lists, tuples, dicts, sets, expressions, and functions
the result of such non-Boolean comparisons is "falsy" or "truthy".

Python interprets "falsy" values the same as the Boolean `False` value. You've already seen values that are falsy: `0`; `''`, `[]`, `()`, `{}`, and `None`. Python interprets everything else as "truthy". 

When using logical operators to compare non-Boolean operands, the truthiness determines the outcome and the type of the result varies depending upon the operator. 

For `not`, "truthy" objects and expressions are `True` and "falsy" objects and expressions are `False`. For `or` and `and`, the result is the value of one of the operands, evaluated from left to right.

For `or`, it returns the first operand that is "truthy". If none are "truthy", the `or` expression returns the last operand. 

For `and`, if all operands are "truthy", it returns the last operand. If none are "truthy", it returns the first operand. If some are "truthy" and some "falsy", it returns the first "falsy" value.

Here are examples of logical operators with non-Boolean values.

```python
# define variables for examples below of logical operators with non-Boolean values
pants_female = 0.0
pants_male = 10
shirts = 12
no_inventory = 0
```

```python
# not
print(not pants_female)
print(not pants_male)

>>> True
>>> False
```

The `not` operator returns the opposite of whatever the value's Boolean status. The `not pants_female` expression evaluates to `True` because `pants_female` evalutates to `False` (it equals `0.0`), and the opposite of `False` is `True`. The `not pants_male` expression evaluates to `False` because `pants_male` evalutates to `True` (it equals `10`), and the opposite of `True` is `False`.

```python
# or
print(pants_female or pants_male)
print(pants_female or no_inventory)
print(pants_female or shirts or pants_male)
print(pants_female or pants_male or shirts)

>>> 10
>>> 0
>>> 12
>>> 10
```

Reading from left to right, the `or` operator returns the first "truthy" value. If none are "truthy", it returns the last value. In the first `or` example above, the `pants_female or pants_male` expression evaluates to `10` because `pants_male` is the first "truthy" value in the expression. `pants_female` evalutates to `False`. It equals `0.0`. `pants_male` evaluates to `True` because it equals `10`. 

In the second `or` example above, the `pants_female or no_inventory` expression evaluates to `0` because none of the operands are "truthy", so it returns the last operand. `pants_female` evalutates to `False` (it equals `0.0`) and although `no_inventory` evaluates to `False` too, the expression returns `no_inventory` because it is the last operand in the expression.

In the third `or` example above, the `pants_female or shirts or pants_male` expression evaluates to `12` because it returns the first "truthy" operand, which is `shirts`. `pants_female` evalutates to `False` (it equals `0.0`) and `shirts` evaluates to `True` because it equals `12`. Although `pants_male` is also `True`, the expression returns `shirts` because it is the first `True` operand.

In the fourth `or` example above, the `pants_female or pants_male or shirts` expression evaluates to `10` because it returns the first "truthy" operand, which is `pants_male`. `pants_female` evalutates to `False` (it equals `0.0`) and `pants_male` evaluates to `True` because it equals `10`. Although `shirts` is also `True`, the expression returns `pants_male` because it is the first `True` operand.

```python
# and
print(no_inventory and pants_female)
print(pants_male and pants_female)
print(pants_male and shirts)
print(pants_male and shirts and pants_female and no_inventory)

>>> 0
>>> 0.0
>>> 12
>>> 0.0
```

Reading from left to right, the `and` operator returns the last operand if all operands are "truthy". It returns the first operand if none are "truthy". If some are "truthy" and some "falsy", the `and` operator returns the first "falsy" value.

In the first `and` example above, the `no_inventory and pants_female` expression evaluates to `0` because both operands are "falsy". So it returns the first value. `no_inventory` evaluates to `False` because it equals `0`. `pants_female` evalutates to `False` because it equals `0.0`. The first operand is`no_inventory`, so the expression returns its value of `0`.

In the second `and` example above, the `pants_male and pants_female` expression evaluates to `0.0` because `pants_male` evalutates to `True`. It equals `10` `pants_female` evalutates to `False`. It equals `0.0`. The expression returns `pants_female` because the `and` expression contains both "truthy" and "falsy" values, so it returns the first "falsy" value.

In the third `and` example above, the `pants_male and shirts` expression evaluates to `12` because both operands are "truthy". `pants_male` evalutates to `True`. It equals `10`. `shirts` evaluates to `True` because it equals `12`. Because both are "truthy", the `and` expression returns the last value in the expression, `12` for `shirts`. 

In the fourth `and` example above, the `pants_male and shirts and pants_female and no_inventory` expression evaluates to `0.0` because it is a mixed expression where `pants_female` is the first "falsy" operand. `pants_male` and `shirts` are both "truthy". They are `10` and `12`, respectively. `pants_female` evalutates to `False` because it equals `0.0`. Although `no_inventory` also evaluates to `False` because it equals `0`, the 'and' expression returns `pants_female` because it is the first `False` operand.





use operators to avoid exceptions (prevent your program from having an error)

```python
# examples of logical operators for avoiding exceptions
# print(i / c == 3.0)
# print(i / y) == 3.0 # returns an error because diving by zero
# print(y != 0 and (i / y == 3.0)) # returns False because y !=0, so expression returns first operand (and doesn't even read second operand)
```


use operators to set a default value

```python
# examples of logical operators for setting default values
truthy_string = "Israel Tech Challenge"
c = truthy_string or 'ITC'
# print(c)
falsy_string = ''
d = falsy_string or 'ITC'
# print(d)
```

# Identity Operators

the identity operators are is and is not 
in contrast to other operators, which compare the operand data value, identity operators evaluate whether two or more operands are the same Python object stored in memory

In operators_and_experessions.py, see
examples of identity operators



