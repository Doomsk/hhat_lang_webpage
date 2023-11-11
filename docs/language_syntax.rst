.. _language syntax:

###############
Language Syntax
###############


Here we present the language syntax, from data types to the way expressions look like and function.


******************
Current Data Types
******************

There are some data types defined below:
 
- :code:`bool`
- :code:`int`
- :code:`@array`


*********
Structure
*********

**Expressions**

The most atomic part of the language is an expression. For instance, it can be a literal, a function, or a variable. Each expression interacts with the other through a special operator: the pipe :code:`:`. It enables the data to pass from the left-side to the right-side expressions. A group of expressions can form single, sequential, concurrent, or parallel expressions related to scopes and data lifetime.


**Scoping**

The general structure of the language relies on function scopes. The outer scope is the main [1]_. Besides that, scopes can be of four kinds: single, sequential, concurrent, and parallel. Single expressions are without branching; one expression receives an input, produces an output, and passes it to the following expression. Sequential scopes may have one or more expressions that will be executed **in order**, one after the other. It is given by the syntax sugar :code:`.[ ]`. Concurrent scopes have the same properties as the sequential ones, but they execute each expression **concurrently**, prioritizing the written expression's order. Its syntax sugar is :code:`.( )`. Parallel scopes have their expressions executed in **parallel**. The syntax sugar is then :code:`.{ }`.


**Data Lifetime**

Ordinary data can only survive one pipe operator. The expression gets it as input and produces a new output, whether it is identical data or not. However, variables live from their assignment until the end of the scope it was created; when it is the last expression in the scope, it will make part of the upper scope. This process guarantees no active garbage collector or user data management is needed. It was inspired by the Resource Acquisition Is Initialization (RAII) from C++.


Syntax Examples
----

.. code-block::

    .[1 1]:sum:print



One main single expression containing a *sequential scope* expression :code:`.[1 1]` with two literal elements (a 2-element array), piped to the expression :code:`sum`, piped to the expression :code:`print`, resulting in a printed output :code:`2` on the terminal.

.. code-block::

    .[5 10]:.(sum times):print

The sequential scope expression containing literal elements, piped to a concurrent scope expression containing two function elements, piped to the last expression. The result is a 2-element array printed on the terminal :code:`15 50`.


.. code-block::

    .[8 8]:.(sum:n times(n):m):print

Similar to the code above, now with variables :code:`n` and :code:`m`. :code:`times(n)` waits for :code:`sum:n` to be completed and then starts executing, due to its dependency on an expression-external resource (a variable in this case). The behavior of :code:`times(n)` is slightly different from :code:`times`. Now, :code:`n` is multiplied by each array element that is piped to :code:`times(n)`, resulting on an array of the same length as the input. In this case, :code:`print` will print a 3-element array, :code:`16 64 64`, with :code:`n` storing :code:`16` and :code:`m` storing :code:`64 64`.


----

.. [1] For now, main is anything in the file. When user-defined functions are implemented and enabled, it will change.