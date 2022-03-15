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
* quantum commands are referred with :code:`@` before the word, i.e. :code:`@h`, :code:`@cnot`
* measurements automatically made with :code:`@return`


Data Types
----------

- :code:`null`: no data
- :code:`bool`: binary data, i.e. true and false, full and empty; represented as :code:`T` and :code:`F`
- [*to be revised*] :code:`register`: sequence of natural amount of enumerated (indexed) single binary data; :code:`hashmap` with integer keys and single binary values. It is intended to store the output collected from each single measurement operation (aka :code:`@return`)
- :code:`int`: integer numbers
- :code:`float`: floating point numbers
- :code:`str`: sequence of 0 or more characters between quotes :code:`""`
- :code:`list`: sequence of any enumerated data
- :code:`circuit`: sequence of 1 or more quantum gates for 1 or more qubits in 1 or more steps; can contain other circuits as well
- :code:`hashmap`: an unordered associative array of keys and values
- :code:`measurement`: a :code:`hashmap`-like type containing relevant data output from the qubits measurement, such as: unique bits sequences final counting, number of shots, some special grouping of bits sequences counting (depending on extra arguments passed)



-----

.. rubric:: Footnotes

.. [#] https://cdagger.com

