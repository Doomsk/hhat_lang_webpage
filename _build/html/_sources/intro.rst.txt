Intro
=======

:math:`\hat{H}` is the **core** quantum language for :math:`C^{\dagger}` programming language [#]_.

The initial idea for the language was to detach the low level of qubit-targeted quantum gates instructions from the possible capability of quantum processors through abstract instructions or functions that might do the hard work without the need for the user to do so. Additionally, provide meaningful results from the measurements as useful data for the algorithm being run.


--------
Summary
--------

* A (high level) quantum algorithms builder
* Handling output data with context meaning
* Debugging results and quantum processes through post-measurement analysis
* Convert high level languages commands into low level quantum instructions for quantum languages such as **openQASM**, **cQASM**, **NetQASM**, **Q1ASM** to be execute on their respective hardware/simulator
* Gates approach - no directed qubit relation since it will be handled by the language, its interpreter/compiler and subsequently by the low level quantum languages compiler
* Aimed for both quantum computers and quantum networks


-----------
Objectives
-----------

* Provide an intermediate picture between high-level and QASM-like programming languages
* Make use of basic quantum gates and complex quantum instructions in a dummy-qubit environment
* Bring light to measurement results and their analysis as a language built-in property
* Debugging through (partial) quantum analysis of measurement results for results and inner processes comparing them to simulated ones (using fisher information, linear entropy, entanglement measurements, etc)
* Provide algorithms usability for the context of both quantum processors (quantum computers) and quantum networks (quantum internet)


--------
Features
--------

* simple syntax
* static-typed
* quantum functions for quantum data
* quantum commands and variables are referred with :code:`@` before the word, i.e. :code:`@h`, :code:`@cnot`, :code:`@var`
* measurements automatically occurs when quantum data interacts with classical instructions,
  functions, operators and variables


--------------------
Built-In Data Types
--------------------

- :code:`null`: no data
- :code:`bool`: binary data, i.e. true and false, full and empty; represented as :code:`T` and :code:`F`
- :code:`int`: integer numbers
- :code:`float`: floating point numbers
- :code:`str`: sequence of 0 or more characters between quotes :code:`""` or :code:`''`
- :code:`circuit`: sequence of 1 or more quantum gates for 1 or more indices in 1 or more steps; can contain other circuits as well
- :code:`hashmap`: an unordered associative array of keys and values
- :code:`measurement`: a :code:`hashmap`-like type containing relevant data output from the qubits measurement, such as: unique bits sequences final counting, number of shots, some special grouping of bits sequences counting (depending on extra arguments passed)

Additionally, except for :code:`hashmap` and :code:`measurement` types, it is possible to
have many elements of a single type arranged as a list.


-------------
Quantum Data
-------------

The first different aspect of :math:`\hat{H}` is how it deals with *quantum data*. Here
quantum data is built on circuits with no reference to qubits (in which there is no access), but rather to *indices* where should be seeing as markers for the compilers to take the instructions and perform their optimizations, mitigations and operations to be carried to the *actual* quantum hardware (or simulator). By doing so, quantum gates and how they are arranged matter most than actual quantum states from qubits, due to quantum gates feasibility to define instructions for the quantum device. Hence we define this as a **Heisenberg architecture** language, where gates evolve the circuit-carried data.


Another aspect that differs is how the quantum data interactcs with classical data and
operators: here there are no *measurements* explictly being made; we designed the language
in such a way to avoid bringing too much of physical aspects that would slow down a
programmer ability to solve the actual problem and make them spend too much time trying to figure
out how to deal with quantum counterparts in the process. We *have to assume* that some
parts of the hardware will just work fine, as we do for classical devices. They must be
underneath the language and compiler if we want to provide a clear path for programmers to
use quantum advantage on their daily-life and, soon, on production code. In this sense,
*every time that a circuit type variable interacts with a classical operator or variable,
that encounter will trigger a series of procedures that will result in a classical data
from the quantum data*. The resulting data will depending on: which data type or operator it is
interacting with; and the type of quantum data to be generated from: one-shot-at-a-time or
a all-shots-at-once. 



-----

.. rubric:: Footnotes

.. [#] https://cdagger.com

