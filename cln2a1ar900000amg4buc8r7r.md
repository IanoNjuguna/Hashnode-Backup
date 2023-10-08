---
title: "Conditional Statements in Python"
datePublished: Wed Sep 27 2023 21:47:08 GMT+0000 (Coordinated Universal Time)
cuid: cln2a1ar900000amg4buc8r7r
slug: conditional-statements-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695844961016/ce286433-1242-43e3-bd54-a7a587bf61b6.png
tags: python, python3, python-beginner

---

## Introduction

Conditionals are statements that allow you to make decisions based on certain conditions or criteria (Jeremiah, 2023). They are essential in any program's control flow.

**Control flow** is the order in which individual statements, instructions or function calls of a program are executed. In an interpreted language such as Python, statements are run one at a time from top to bottom and from left to right.

Function definitions do not alter the flow of a program, they act as a detour in the flow of execution. In such a case, the control flow does not go to the next statement as it jumps to the body of the function, runs the statements there, and then comes back to pick up where it left off (Downey, 2015b). Bear in mind that this also applies when such a function calls another function.

## Conditionals

In this article, we'll explore the most common types of conditionals in programming. They are:

* ### `if` statements
    

The `if` statement evaluates whether a condition has been met. The syntax is as follows:

```python
if condition_is_true:
   execute_statement(s)
```

The condition is evaluated as a boolean using logical operators. This means there are no options other than true or false. When the condition in the `if` statement is true, the body of code indented under it is executed.

* ### `elif` statements
    

An `elif` statement branches the control flow execution based on a set of multiple alternatives. Hence, there is no limit to the number of `elif` statements you can specify.

The syntax is as follows:

```python
if condition_is_true:
   execute_statement(s)
elif this_condition_is_true:
   execute_statement(s)
elif this_condition_true:
   execute_statement(s)
```

In the `elif` statement, once an expression is found to be true and its block is executed, none of the remaining expressions are tested.

* ### `else` statements
    

When you want to specify a block of code to execute when the preceding `if` and `elif` conditions are false, you use an `else` statement.

> The else statement is optional. If it is present, there can be only one and it must be specified last (Python, 2023b).

The syntax for an else statement is as follows:

```python
if condition_is_true:
   execute_statement(s)
elif this_condition_is_true:
   execute_statement(s)
elif this_condition_true:
   execute_statement(s) 
else:
   execute_statement(s)
```

* ## `match` Statements
    
    The `match` statement evaluates an expression, and matches the expression's value against a series of `case` clauses, and executes statements after the first `case` clause with a matching value (More Control Flow Tools, n.d.)  
      
    It is similar to a switch statement in C-style languages. Syntax:
    

```python
def http_error(status):
    match status:
        case 400:
            return "Bad request"
        case 404:
            return "Not found"
        case 418:
            return "I'm a teapot"
        case _:
            return "Something's wrong with the internet"
```

In the last case statement, the “variable name” `_` acts as a *wildcard* and never fails to match. If no case matches, none of the branches is executed.

* ### Chained Conditionals
    

A chained conditional occurs when multiple conditional statements are placed in such a way that the interpreter evaluates them sequentially. If one condition is true, the corresponding block of code is executed, and the rest of the conditions are not evaluated. Such as the code example preceding this section.

* ### Nested Conditionals
    

A nested conditional occurs when you place (nest) conditional statements inside other conditional statements to create more of a hierarchy of conditions where each inner condition is evaluated only if the outer condition is true. For example:

```python
age = 25
income = 50000

if age >= 21:
    if income >= 30000:
        print("You are eligible for a credit card.")
    else:
        print("You need a higher income to qualify.")
else:
    print("You must be at least 21 years old to apply.")
```

## References

1. Jeremiah, O. (2023). How to Use Conditional Statements in Python – Examples of if, else, and elif. [*freeCodeCamp.org*](http://freeCodeCamp.org). [https://www.freecodecamp.org/news/how-to-use-conditional-statements-if-else-elif-in-python/](https://www.freecodecamp.org/news/how-to-use-conditional-statements-if-else-elif-in-python/)
    
2. Downey, A. B. (2015b). *Think Python : How to think like a computer scientist*. [https://openlibrary.org/books/OL26455778M/Think\_Python](https://openlibrary.org/books/OL26455778M/Think_Python)
    
3. Sturtz, J. (2023b). Conditional statements in Python. [*realpython.com*](http://realpython.com). [https://realpython.com/python-conditional-statements/](https://realpython.com/python-conditional-statements/)
    
4. *More control flow tools*. (n.d.). Python Documentation. [https://docs.python.org/3/tutorial/controlflow.html#match-statements](https://docs.python.org/3/tutorial/controlflow.html#match-statements)