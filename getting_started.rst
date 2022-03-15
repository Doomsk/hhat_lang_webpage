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

    func measurement @grover (circuit @oracle): (
        int size: (:@oracle(size))
        circuit @c1(size): (:@superposn, :@oracle)
        measurement @m1(size): (num_shots: 1024)
        for (0..sqrt(div(size 2))): ( @c1 (:@diffusion(@oracle)) )
        @c1 (:@m1)
        @return (@c1)
    )



