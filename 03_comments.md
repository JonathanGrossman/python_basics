# Comments  

## Comments are code that the computer does not run.  

### Why do developers leave comments in their code?  

When we write code, we have two main audiences. First, we write code for the computer. We want to write code that the computer understands. If the computer doesn't understand the code, then the program won't run properly or at all. Second, we write code for developers (our future self included). While the code that you write might be self explanatory, especially if you use good names for variables, comments will nonetheless help. Sure, certain blocks of code will be easy to understand without comments. Others, however, will become complex and too difficult to fully comprehend without an unreasonable amount of tinkering. 

By leaving short but meaningful comments, you can explain to people who read the code what the code does and why it’s important. This will decrease the amount of time it takes someone to understand your code and also help make sure they understand it all. Plus, the process of making and updating comments will make you think more about your code, which can lead to more efficient scripts. For instance, before you write the code itself, writing comments in pseudocode can help you plan before writing the actual code.  

Writing comments may seems tedious at first. But once you realize the value of them and how they save you time and frustration, you will begin to incorporate them into your routine. For example, you will write a sophisticated block of code and then not look at it for weeks or months. In the process of maintaining your project or adding to it, you later will come across this complex code and not know what it means at first. If you wrote effective comments when you wrote the code, it should be much easier for you to figure out what the code does and how to work with it. 

## How do you turn code into a comment?    

Two main ways exist for commenting out your code. One easy is to put a `#` at the beginning of the line you want to turn into a comment. If your code spans multiple lines, you'll need a `#` at the beginning of each line that you want to be a comment. 

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

```python
# examples of comments

# x is an integer
x = 3


# returns a greeting
def get_greeting():
  return "Welcome to my page"
  
  
# returns a list of objects
def get_objects():
  # define list of objects
  list_of_objects = [ {. . .},  {. . .}, {. . .}, . . .]
  
  return list_of_objects
```

## Notes: 
> don’t overuse comments
> keep comments short
> keep comments up-to-date with your code
