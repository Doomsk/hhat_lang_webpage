Getting started
===============

While the code still is in designing process, you can check the current syntax out and have a feel of what to expect soon.

------------
Code samples 
------------

One-line

.. code-block::  
    
    main null C: ( int num: (:add(1 1), :print) )



Quantum functions

.. code-block::

    func circuit @grover (circuit @oracle) (
        int size = (:@oracle(size))
        circuit(size) @c1 = (:@init, :@oracle)
        for (0..i_sqrt(div(size 2))) (
          : @c1(:@ampl(@oracle)) 
        )
        return (@c1)
    )



