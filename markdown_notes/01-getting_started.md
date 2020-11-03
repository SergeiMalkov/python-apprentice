# Getting started

# REPL

`Read, Evaluate, Print, Loop -> REPL`

`_` - special variable, valid only in REPL when playing with interprerter

Identation - four spaces, and identation is an essential part of python, eg is
this snippet with simple for loop.

```python
for i in range(5):
    x= i*10
    print(x) #blank line means end of the block

```
Importance of identation:

1. readable code
2. No clutter
3. Human and computer are "synced"

Rules are simple:

* Prefer `four spaces`
* `Never` mix tabs and spaces
* Be `consistent` on consecutive lines
* only deviate to `improve` readability

## Importing from Python standard library

```python
# just use import module_name
import math

```

getting help
help(module_name)

Simple example:
```python
import math
n=5
k=3
math.factorial(n)/(math.factorial(k)*math.factorial(n-k)) # too many letters
# let's introduce some shorthand with alternative import statement forms

from math import factorial
factorial(n)/(factorial(k)*factorial(n-k))

# finally, the shortest form:
fac(n)/(fac(k)*fac(n-k))
```

Integer division operator `//`
Float division `/`

## Scalar types and values

* int - unlimted precision signed integer
* float
* None - abscence of value
* bool (True and False) - logical states, True/False


```python
# conversion between different bases
10
0b10
0o10
0x10
```
Constructors - convert to corresponding type
int(3.2)
float(4)
bool(1) - True for any object of non-zero length( value is not equal to zero, or bool is used
on collection of non-zero length, like string or dictionary)
bool(0)

Relational operators:
== # Equatlity test, equal objects are interchangable
!=
<
>
<=
=>

## Conditional statements

```python
if True:
    print("it's true!")

# Another example
if False:
    print("fuckoff!")
```

```python
 if h >50: 
     print("more than 50")
 else: 
     print("smaller than 50")

```
Python has two types of loops and surprisingly, there is no `until` loop

* `for` loops
* `while` loops

```python
while expr:
    print("loop while expr is True")
```

### Breaking out

```python
while True:
    if expr:
        break
print("here comes outbreak!")
```

`break` keyword terminates `innermost` loop, transferring execution to the first 
statement after the loop.
Another snipet to consider:

```python
while True:
    response = input()
    if int(response) %7 ==0:
        break
# loop expects input from user
# of course, it should be digit, otherwise int won't be able to convert response
# Then, if response could be divided by 7, then loop will exit
```

When working with `ipython` it could be handy to save session's history with
`%history -f $path_to_file`