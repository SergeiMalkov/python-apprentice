# Modularity

## Functions

To write reusable code with python, we will have to use functions.
They start with keyword `def`; then follows the name of function, optional list of arguments and body of function.
Then follows function's body, what is actually happening there.
**Trick about functions is that you also must call them to make use of them!**

```python
# Example one
def square(x):
    return x*x

# Example two
def launch_missiles():
    print("Rockets launched!")

# Example three
def even_or_odd(n):
    if n % 2 ==0:
        print("even")
        return 
    print("odd")
```

Functions may:
* accept one or more arguments
* return values or None

Q: How do I know if function returns something? 
A: Capture returned object to function's call with reasonable argument and see type of resulting object (aka variable).
````python
a = square(3)
# examine output of one of those commands in REPL
 a is None
print(a)
a
````

### Difference Between Module and Script

```python
__name__ """ Magic variable, that evaluates
            to "__main__" or actual module name
            depending on how the enclosing module is being used
"""
```

Module code is being executed once, on the first import. 
I guess that script is being executed as many times as it is being run.

How do we run module as a script?
Actually, it's very simple `python3 myfile.py` - this is a run as script
We have a module `python_code/modularity/words_functions.py` which consist of one function.
If we want to run it as script, then we should use magic variable `__name__`, we should use this python idiom:

```python
if __name__ == "__main__":
    fetch_words()
```
So, this is simple - if module is being run as a script, then we want to call specific function

## Python Execution Module 

* When are functions defined?
* What happens when a module is imported?

I will use `python_code/modularity/words_functions.py` as example here.
What is important to understand, that `def` here is a statement, not a declaration.
This means, that `def` is executed at runtie along with ther rest of top-level module-scope code.
`def` simply binds name of the function to the function's body code.

So, we can write a python module - it will contain definition of some functions, which could be imported into REPL  and do something useful.
We can go for a python script, which could be run by interpreter. 
Or we can go even further by writing a python program, that could be composed of multiple modules.
So, modules could be written to allow convenient import, execution or both. I guess, we should try for both.
 
 ## Main Functions and Command-line arguments
 
 ```python
# introducing new forms of import statements
from words import (fetch_words, print_words) # should be one of most common
# it allows import multiple modules, if you have a long list, it could be splitted by multiple lines.

# This form is recommended for usage in REPL only, because later on you could encounter namespaces clashes.
# This is because all functions from module are being imported and this gets out of your control.
 from words import *
```

From `python_code/modularity/words_functions.py` to `python_code/modularity/words_refactored.py`
First of all, `print_words()` is capable of printing any collection. So, we rename it to `print_items()`.
Another point - we have hardcoded url which destroys flexibility of program. So, good solution here is to pass item as command-line option.

URL solution - let's import `sys` module and use argv functions and use sys.argv
This works for our case - one argument which is being passed as command-line option.
But for more complicated cases, it's worth examining `argparse` from Python Standard library or `docopt`. 

Also it could be worth mentioning PEP8 and that there should be two lines between function's definitions.
Anyway, advanced IDE will handle it for you.

## Documenting Code Using Docstrings

We are using those suggested by Google guys, I guess they aren't dumb as Cory and Trevor.
https://google.github.io/styleguide/pyguide.html

String comments are a common thing that you already know

## Shabang
You need to make your script executable and allow `env` command to search for appropriate interpreter in user's path.
Starting from python 3.3 it works on any platform, even on Windows.

# Summary

1
