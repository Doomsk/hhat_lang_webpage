.. _2020 timeline:

2020 Timeline
=============

A studies group on quantum computing, quantum information and quantum algorithms was held in Discord starting on December 2019 [1]_. The idea was to bring the topic to probably-not-physicists-but-enthusiastic-about-quantum-computers people in a friendly fashion with applications in mind. As the months passed by, the pandemic hit the entire world, we dove into the topic as our [probably only] hobby. Soon, we realized that most of the material out there wasn't good enough to explain the algorithms to physicists or enthusiasts. Then, we started writing our very own algorithms in an attempt to, by trial and error, make sense of the logic behind them. It didn't pass long until we felt the need to write algorithms in a more efficient, clear, and understandable way.

----
:math:`C^{\dagger}` programming language
----

And then, we started studying how actually to write a programming language to accomplish this objective. That was the birth of :math:`C^{\dagger}` (C dagger) programming language. As a first try, I defined the syntax inspired by Assembly language syntax. Here is a code snippet example:

.. code-block::

    main:
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

The central language concept was to be as close to natural language as possible [2]_ to make the programming of quantum parts less steep. For that reason, there was this concept of :code:`noun verb object`. The syntax was easy: :code:`noun: verb [objects]`, eventually having prepositions, adverbs and conjunctions between verb and object or between objects to provide extra functionalities for the language completeness. :code:`object` could be either variables or function calls providing results by themselves or another sentence group as :code:`with noun: verb [objects]`.

The code was meant to be clean without any annoying things imposed on other languages, such as semicolons or indentation. Those last two are a big requirement for any implementation I have ever done since.

The language was beyond just a domain specific language (DSL), because it included accounts for running quantum instructions remotely and also having access to the hardware that would generate the pulse sequences for the quantum operations. A whole concept around the scheduling, messaging and syncing was being developed. It was heavily influenced by the way Erlang works [3]_, and also by some ideas that seemed to make sense to have in a language that should not only have direct access to the quantum hardware, but remote access to it or to requests from remote operations.

At the time, I didn't have the idea to think of this whole system as a virtual machine (VM) that contained a programming language on top, but now it seems very natural to think this way.



.. [1] An in-person group with the same purpose happened between the end of 2017 and early 2019 in São Paulo, Brazil.
.. [2] Although I have never programmed in Cobol, I recognize it is already an existing concept. Nevertheless, it was never used as a reference.
.. [3] At this point I haven't read extensively enough about Erlang, or BEAM, or OTP to known exactly what they were doing under the hood, just had some vague ideas but they were enough to build a concept around the language.