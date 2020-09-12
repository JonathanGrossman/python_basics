# Comments  

## Comments are code that the computer does not run. 

```python
# this is a comment
def this_is_code():
  return "A function that returns a string"
```

### Why do developers leave comments in their code?  

When we write code, we have two main audiences. Computers and developers. When considering the computer as our audience, we write code that follows the rules of the language we are writing in. We want to write error-free code. In other words, we want to write code that the computer understands. If the computer doesn't understand the code, then the program won't run properly or at all. If your code is written with the proper syntax, the computer won't need any explanation. It will understand how to exectute it.

Second, we write code for developers (our future self included). Unlike computers, developers need help understanding code. While a computer can quickly read code and know what it means, developers can't do it like computers can. Sure, some of the code that you write will be self explanatory. Developers will be able to understand it with ease. However, even if you use tools and techniques other than comments, you'll find that some of the code will grow too complex for developers to understand without an unreasonable amount of tinkering. For instsance, even if you use good names for variables and functions, and even if you use a code editor with good syntax highlighting, the flow of your script and the purpose behind the code may be lost.

By leaving short but meaningful comments in your code, you can explain to people who read the code what the code does and why it’s important. This will decrease the amount of time it takes someone to understand your code and also help make sure they understand it all. Plus, the process of making and updating comments will make you think more about your code, which can lead to more efficient scripts. For instance, before you write the code itself, writing comments in pseudocode can help you plan before writing the actual code.  

Writing comments may seems tedious at first. But once you realize the value of them and how they save you time and frustration, you will begin to incorporate them into your routine. For example, you will write a sophisticated block of code and then not look at it for weeks or months. In the process of maintaining your project or adding to it, you later will come across this complex code and not know what it means at first. If you wrote effective comments when you wrote the code, it should be much easier for you to figure out what the code does and how to work with it. Remember that when you update your code you also need to update your comments.

## How do you turn code into a comment?    

Two main ways exist for commenting out your code. One way is to put a `#` at the beginning of the line you want to turn into a comment. If your code spans multiple lines, you'll need a `#` at the beginning of each line that you want to be a comment. 

```python
# this is a comment
# this is another comment
```

```python
this is not a comment and will result in an error
```

Another way to comment out your code is to highlight the lines of code that you want to be a comment, and press key commands. For Mac users, the key commands are `Command + /`. For Windows users, the key commands are `Control + /`. After pressing the key commands, a `#` should appear at the beginning of each line you highlighted.

For example, if you are on a Mac, highlight the line of code that you want to turn into a comment, and then press:

> Command + / (Mac)  

If you are on Windowns, highlight the line of code that you want to turn into a comment, and then press:

> Control + / (Windows)  

## Examples of comments:  

Here are a few basic examples of comments. Notice that each line that is a comment starts with a `#`. Any line that does not start with a `#` Python will try to interpret.

```python
# examples of comments

# x is an integer
x = 3


# returns a greeting
def get_greeting():
  return "Welcome to my page"
  
  
# returns first item in a list of objects
def get_objects():
  # define list of objects
  list_of_objects = [ {. . .},  {. . .}, {. . .}, . . .]
  
  # get first item in list_of_objects
  first_item = list_of_objects[0]
  
  return first_item
```

## Notes: 
> don’t overuse comments  
> keep comments short  
> keep comments up-to-date with your code  
