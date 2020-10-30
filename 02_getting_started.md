# Getting Started

## [Installing Python](#installing-python)

Before you can start writing Python code, you need to make sure you have Python installed on your computer. Some computers have Python pre-installed and others don't. Even if a computer has Python pre-installed, you want to make sure you know which version, as Python has versions 2 and 3 out in the wild. You can check whether you have Python installed and which versions by using the terminal. You should check for both Python 2 and Python 3. Open up a terminal session on your computer and enter `python --version` to check for Python 2 and `python3 --version` to check for Python3.

```python
python --version
```

```python
python3 --version
```

If you have that Python version installed, the terminal will respond with the version number.

```python
Python 2.7.16
```

```python
Python 3.7.7
```

If you don't have a Python version installed, you should install it. To download Python, visit the [Python downloads](https://www.python.org/downloads/) page. Find Check to make sure you're in the page for your operating sysmte (for instance, Mac, Windows, etc.). Choose the version you want to download and follow the installation instructions. 

When installation is complete, check again whether Python is installed. Depending upon which version you installed, enter in the terminal `python --version` to check for Python 2 or `python3 --version` to check for Python3.

```python
python --version
```

```python
python3 --version
```

If installation succeeded, the terminal will respond with the version number that you installed.

## [Installing Visual Studio Code](#installing-visual-studio-code)

## [Creating and activating virtual environment](#creating-and-activating-virtual-environment)

After confirming that your project setup is correct, create and activate your virtual environment. By creating a virtual environment, you keep the project dependencies for this project separate from the project dependencies of your other projects on the same computer. For instance, using virtual environments allows you to have one Flask project that uses Flask version 1.1.2 and Python 3.7 and another Flask project that uses Flask version 1.0 and Python 3.6.4. You can run them from the same computer without having to uninstall and reinstall the packages when switching between projects.

Because of its role as a partition between projects, setting up a virtual environment should be part of the initial setup of every Flask application. The first step is to install, or confirm that you already have installed, the tool for creating and managing a virtual environment.The next step is to actually create the virtual environment. 

Confirm the terminal is in the root level of your project folder. Look at your project folder and notice that it does not have an env folder. 

As shown below, enter the command in your terminal that creates the virtual environment. The last item in the command is the name of the virtual environment folder that will appear in your project folder. You can name it whatever your want, but the convention is to name it env or venv. In this example, I name it env. After you run the command, look in your project folder. You should see a folder named env.

For MacOS users, create a virtual environment by entering the following in your terminal:

```python
 python3 -m venv env
```

For Windows users, create a virtual environment by entering the following in your terminal:

```python
py -m venv env
```

Activate the virtual environment. Now that you have a virtual environment, you need to activate it. Each time you open your project folder, you will need to activate your virtual environment.

For MacOS users, activate the virtual environment by entering the following in your terminal: 

```python
source env/bin/activate
```

For Windows users, activate the virtual environment by entering the following in your terminal: 


```python
.\env\Scripts\activate
```

Confirm you are in the virtual environment. In your terminal, if you see on the far left of the command line the name of your virtual environment inside parenthesis, then you have successfully activated your virtual environment. You can also confirm whether you are in your virtual environment using a terminal command.

For macOS users, confirm that you are in your virtual environment by entering the following in your terminal:

```python
which python
```

For Windows users, confirm that you are in your virtual environment by entering the following in your terminal: 

```python
where python
 ```

If your virtual environment is activated, your terminal will point you to the directory in which your virtual environment exists (i.e., the env folder). For instance:

```python
. . . /env/bin/python
```

If your virtual environment is not activated, your terminal will point you to the directory in which your Python installation lives globally on your computer. For instance:

```python
/usr/bin/python
```

While still in your project folder, create a requirements.txt file. Instructions below. It will list the packages installed in your env. 

Before you run the command below, look in your project folder and notice that it is missing a requirements.txt file. After running the command, look again. Your project folder should have a requirements.txt file.

```python
pip3 freeze > requirements.txt
```

If you look inside the requirements.txt file, it should be empty.


Also create a .gitignore file (starts with a . and ends with no extension). Inside the .gitignore file, type env. By having a requirements.txt file that lists the dependencies and a .gitignore file that lists the env file containing the dependencies, you can save your code to GitHub without pushing all the dependency packages. Without including the dependencies, your code will download and upload more quickly and will take less storage space on GitHub. Then, when you or someone pulls the code from GitHub, you can install the dependencies listed in the requirements.txt file.

Now you can install packages. Install Flask so that you can set up your server.

```python
pip3 install Flask
```

Next, in your terminal, again run

```python
pip3 freeze > requirements.txt 
```

This updates the requirements.txt file with the installed packages. After freezing your requirements.txt file, if you look at your requirements.txt file, you should see an updated list of the packages installed for your project’s virtual environment. Yours should include Flask and any other packages you installed. When you push to GitHub, notice that the env folder is missing (if you remembered to create your .gitignore file).

Sidenote: You can freeze as many times as you want. It is best to do so before deployment and also good practice to do so after installing one or more new packages.

To deactivate your virtual environment, type in your terminal 

```python
deactivate
```
For now, do not deactivate your virtual environment. You should continue working in it for the remainder of the tutorial.

## [Writing and running a Python script](#writing-and-running-a-python-script)
