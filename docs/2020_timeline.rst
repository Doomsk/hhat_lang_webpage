.. _2020 timeline:

2020 Timeline
=============

A studies group on quantum computing, quantum information and quantum algorithms was held in Discord starting on December 2019 [1]_. The idea was to bring the topic to probably-not-physicists-but-enthusiastic-about-quantum-computers people in a friendly fashion with applications in mind. As the months passed by, the pandemic hit the entire world, we dove into the topic as our [probably only] hobby. Soon, we realized that most of the material out there wasn't good enough to explain the algorithms to physicists or enthusiasts. Then, we started writing our very own algorithms in an attempt to, by trial and error, make sense of the logic behind them. It didn't pass long until we felt the need to write algorithms in a more efficient, clear, and understandable way. And then, we started studying how actually to write a programming language to accomplish this objective. That was the birth of :math:`C^{\dagger}` (C dagger) programming language. As a first try, I defined the syntax inspired by Assembly language syntax. Here is a code snippet:

.. code-block::

    gmp:
        loads [lib1 lib2]
        receives [inst1 inst2]
        reads [param1 param2]
        optimizes [
            with lib1.f:
                converts [inst1]
                uses [param1]
            &
            converts [inst2]
            uses [param2]
        ]


One idea was to make it easy to build algorithms through operations rather than states, a core concept that still exists in :math:`\hat{H}`. Another idea was to make it language-independent, so English speakers (writers?) could write a code as Portuguese speakers could read the same code in their native language, or Japanese speakers, Arabic speakers, etc. By having some identifier tokens in the programming language that could serve as wildcards and be replaced by whatever speaking language the programmer wanted to write the code in.


At some point, it became clear that it was difficult for expert people to buy the idea. They weren't convinced localization was relevant or the syntax was nice enough to be widely used. Additionally, on the implementation side, the idea of having core features do the heavyweight for the language and the syntax and abstraction being the lightweight part split the language into two: :math:`C^{\dagger}` would be the higher abstraction part, while : math:`\hat{H}` would be the core language containing all the essential structures, logic, APIs and transpilations to talk to various endpoints -programmer and hardware or simulator.



.. [1] An in-person group with the same purpose happened between the end of 2017 and early 2019 in São Paulo, Brazil.
