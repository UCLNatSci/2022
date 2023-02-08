# Tools
## Anaconda

Anaconda is a software distribution which includes the Python language, software libraries useful for scientific computing, and a number of graphical tools. Anaconda is installed on computers in UCL teaching rooms and available to download from the link below.

[Download Anaconda](https://www.anaconda.com/products/distribution)

Included in the Anaconda is:
 - The Python programming language
 - Useful libraries for scientific computing include [Numpy](https://numpy.org/), [Scipy](https://scipy.org/) and [Matplotlib](https://matplotlib.org/)
 - An Integrated Development Environment (IDE) called [Spyder](https://www.spyder-ide.org/)

## Spyder

Spyder is a software development tool designed for scientific computing. The interface of Spyder is very similar to other IDEs such as MATLAB and RStudio including console, code editor, file browser and object viewer. It is important to become familiar with this interface since it is quite different to the notebook-style interface that you might be used to. While it might seem more complicated at first, Spyder has many benefits including:

- ability to perform computing directly on your computer's hardware
- ability to dynamically inspect variable values
- interactive debugging tools
- interactive code execution

To get started using Spyder, watch the two introductory videos "Getting Started" and "Learning the Basics":

https://docs.spyder-ide.org/current/videos/first-steps-with-spyder.html

Spyder is available in all teaching rooms or by downloading Anaconda to your computer.

## Introduction to Sypder

> Open Spyder and identify the **code editor**, **console** and **variable explorer** panes.

> Enter the following command into the console and press `Enter`:

```
print("One for all, all for one")
```

The console is for executing Python commands interactively. Python executes each command as soon as you press `Enter`, and then displays the result below.

> Execute the following command using the console:

```
x = 33
```

Python creates a new variable `x` with value `33`. Notice that a new line has appeared in the variable explorer. What is the type of `x`?

> Execute the following command using the console:

```
y = x / 3
```

Python creates a new variable `y`. What is its type and value, according to the variable explorer? In {numref}`types_section` we will study what the different types represent, and how Python determines the type of the variables we create.

> Create two more variables, one of type string and one of type list.

The variable explorer shows all four variables that you have created. We can clear all variables by restarting the Python kernel. 

> Select *Consoles* > *Restart kernel* from the Spyder menu.

Python restarts. All declared variables and functions are removed from memory.

> What do you expect the variable explorer to look like after running each line of code? Enter them one at a time into the console and check.

```
x = 100
y = x
x = x + 2
```

> Restart the kernel and then enter the following lines of code in the console  :

```
x = [10, 20, 30]
y = x
x[0] = 77
```

Notice the difference in behaviour between integers and lists. We'll see why in {numref}`objects_section`.

The console is useful for interactive programming. For writing complete programs or scripts, use the code editor.

> Create a new `.py` file (*File* > *New File...*) and enter the following:

```
def double(x):
    x = x * 2
```

> Execute the code (*Run* > *Run* or press `F5`). Check that the new function definition appears in the variable explorer. Then, enter the following at the console:

```
z = 10
double(z)
```

> The function didn't change the value of `z`. Fix the function by adding a `return` statement, and then use the function to double the value of `z`.

> Replace the text in the code editor with the following then execute the code.

```
def double(x):
    for i in range(len(x)):
        x[i] = x[i] * 2
```

> Enter the following at the console:

```
z = [1, 2, 3]
double(z)
```

> What happened to the value of `z` after executing this code? Again the behaviour of integers and lists is different. We'll see why in {numref}`functions_section`.
