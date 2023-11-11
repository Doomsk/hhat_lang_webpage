Getting started
===============

Take a glimpse of the code in the `samples below <Code samples_>`_. Or check it on the :ref:`language syntax` page.

------------
Code samples 
------------

One single expression:

.. code-block::  
    
    .[1 1]:sum:print


Now consider the case where you are playing RPG, Werewolf: The Apocalypse, for instance, and you need to roll a d10 dice for your character's Attribute tests, with `+2` bonus. You can roll the dice using :math:`\hat{H}` and quantum computers!

.. code-block::

    .[1 6]:@shuffle:@dice
    .[2 @dice]:sum:print("Attribute test result: ")


