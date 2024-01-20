.. _2021 timeline:

2021 Timeline
=============

Implementing :math:`C^\dagger` syntax, resolving all the edgy cases and keeping it clean, producing a decent lexer, parser and interpreter was a tough task. Every single modification on any of the steps produced a cascade event of modifications on the following ones. So every correction or redesign produced a huge overhead on the language implementation. Important lessons were learned throughout the design and coding processes.

At first, theory from books didn't seem useful, because they were too theoretical for something very practical. However, as I dug into the development and hit some hard walls that prevent me from moving on, those books showed to have valuable lessons. What I can get from it is that you need to hit some dead-ends before some theory starts making sense or being applicable. A hard way to learn, but I think the most precious one.

At some point, I started spreading the word outside the studies group to see whether I could gain some attention and more people interested in collaborating with. I talked to many experts from programming language implementation, distributed computing, quantum information and quantum computing backgrounds. Some tough feedbacks, some nice feedbacks, some nonsensical feedbacks were given.

However, it became clear that it was difficult for expert people to buy the idea, at least in the current state and the current way the language was presented. They weren't convinced localization was relevant or the syntax was nice enough to be widely used. Additionally, on the implementation side, the idea of having core features do the heavyweight for the language and the syntax and abstraction being the lightweight part split the language into two: :math:`C^{\dagger}` would be the higher abstraction part, while :math:`\hat{H}` would be the core language containing all the essential structures, logic, APIs and transpilations to talk to various endpoints -programmer and hardware or simulator.


-----
:math:`\hat{H}` is born
-----
