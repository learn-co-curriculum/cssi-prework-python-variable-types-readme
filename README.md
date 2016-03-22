# Python Variable Types and Their Scope

## Objectives

1. Learn about the different types of variables in Python
2. Learn about the scoping of these variable types

## Introduction

Variables hold data of any type in memory. In Python, there are a few different variable types we'll be going over. Note that here "type" does not mean "data type". Unlike in languages such as C, C++, and Objective-C, data types in Python do not need to be explicitly declared when variables are assigned.

We're going to focus here on two main variable types.


## Local Variables

You should already be familiar with declaring local variables. They're written most commonly as lowercase words, or sometimes you might see developers declare them with an underscore (like `_this`––DON'T DO THIS, btw). Most commonly, they look like this:

```python
languages = ["Python", "JavaScript", "C", "Ruby"]
```

Local variables are distinguished from other types of variables primarily by their "scope". Local variables have a "local scope", meaning that their definitions remain where they are declared.

If we define a variable within a function definition, only the function knows about that variable. Any type of reference to that local variable will result in an error;

```python
def my_function():
  local_variable = "Only my method knows about me!"

print local_variable
=> NameError: name 'local_variable' is not defined
```

## Global Variables

Global variables, as you may have guessed, have a "global scope". These variables may be accessed anywhere in a program and are declared by using the `global` keyword, like so:

```python
def my_function():
    global my_variable
    my_variable = "The entire program knows about me!"

print my_variable
=> "The entire program knows about me!"
```

Global variables should be used **very** sparingly, if at all. The concern with global variables is that because of their global reach, they can "break encapsulation"—if any method can modify a global variable, then any other place that relies on that variable can work in unpredictable ways. This can be very difficult to debug.
