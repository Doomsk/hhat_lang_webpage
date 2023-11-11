Intro
=======

The initial idea for the language was to detach the low level of qubit-targeted quantum gates instructions from the possible capability of quantum processors through abstract instructions or functions that might do the hard work without the need for the user to do so. Additionally, provide meaningful results from the measurements as useful data for the algorithm being run.

Using concepts from *functional* and *array* programming languages, as well as on *concurrent* programming paradigms, such as Erlang_ and Elixir_, the language was defined. It intends to serve as the superposition between what assembly languages and the first Fortran_ version were to classical computing, but now for quantum computing.

--------
TLDR; Summary
--------

* A (high level) quantum algorithms builder
* Uses concepts from functional and array programming languages
* Based on concurrent programming paradigm
* Handling output quantum data with contextualized meaning
* Quantum and classical variables are arrays of data
* No qubit approach: it will be handled by the language as operations (quantum) on indexes; The interpreter/compiler will be responsible to transpile it to low level QASM instructions
* Convert high level languages commands and procedures into low level quantum instructions for quantum languages such as **openQASM**, **cQASM**, **NetQASM**, **Q1ASM** to be executed on their respective quantum backend hardware/simulator
* Debugging results and quantum processes through post-measurement analysis (probably)
* Aimed for both **quantum computers** and **quantum networks**


-----------
Objectives
-----------

* Provide an intermediate picture between classical high-level and QASM- or QIR_-like programming languages
* Make use of basic and complex quantum instructions and procedures in a qubit-free environment
* Give a syntax compatibility for both classical and quantum expressions, making the code easy to read, to understand and to write
* Focus on the problem to solve not on the physical aspects of a particular device
* Bring light to measurement results and their analysis
* Be simple enough to be used by software developers with little knowledge on quantum computing
* Prepare the path for quantum devices with hundreds or thousands of qubits
* Integrate with common programming languages through function calls
* Integrate with quantum hardware and compilers
* Debugging through (partial) quantum analysis of measurement results for results and inner processes comparing them to simulated ones (using fisher information, linear entropy, entanglement measurements, etc.)
* Provide algorithms usability for the context of both quantum processors (quantum computers) and quantum networks (quantum internet)

--------
Features
--------

* simple syntax
* *every input and output* is an array of data
* left-to-right code workflow logic
* scope-based data
* sequential, concurrent and parallel programming made easy with simple syntax
* quantum functions for quantum data
* quantum functions and variables are referred with :code:`@` before the word, i.e. :code:`@shuffle`, :code:`@sync`, :code:`@q`
* measurements automatically occurs when quantum data interacts with classical data via classical functions


--------------------
Built-In Data Types
--------------------

Current available data types are:

- :code:`bool`: binary data, i.e. true and false, full and empty; represented as :code:`T` and :code:`F`
- :code:`int`: integer numbers (including negative numbers)
- :code:`@array` quantum array data, more on `quantum data <Quantum Data_>`_


Data types to be added next:

- :code:`str`: string data
- :code:`float`: floating point data
- :code:`complex`: complex data
- :code:`hashmap`: associative array of keys and values


-------------
Quantum Data
-------------

The first outstanding aspect of :math:`\hat{H}` is how it deals with *quantum data*.
Firstly, it has no concept such as *qubits*. Everything in the language is treated as data in arrays, so array indices are the only essential identifiers of data slices. Unnecessary complexity creates unnecessary confusion and a barrier to developing what matters: a problem-solving code.
Secondly, quantum data is a set of classical and quantum expressions that guide the code execution on a quantum device. It is then stored in a quantum variable as an abstract syntax tree (AST)-like structure that will be evaluated at the right moment when the variable interacts with classical data through classical functions.
Thirdly, since we cannot access quantum states, :math:`\hat{H}` is thought in terms of quantum functions that are composed by quantum instructions, making it a **Heisenberg picture architecture paradigm**. This way, the language aligns with what functional programming paradigms intend to provide: focus on the *what* and not the *how*.
Lastly, measurements are automatically performed once the quantum variable is required to be cast to a particular data type. It happens during the interaction with classical data on classical functions. The quantum variable data, which consists of a mix of classical and quantum expressions in an AST-like structure, starts executing its content, evaluating the classical data, and transpiling the quantum expressions to be performed on the quantum device/simulator. The measurement is then post-processed through a preselected data type-cast protocol that will convert the bitstrings into the corresponding expected data type.


-----

.. _QIR: https://www.qir-alliance.org/
.. _Fortran: https://archive.computerhistory.org/resources/text/Fortran/102649787.05.01.acc.pdf
.. _Erlang: https://erlang.org/download/armstrong_thesis_2003.pdf
.. _Elixir: https://elixir-lang.org/