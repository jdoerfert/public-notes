Zing Falcon
-----------

Over the last few years, I helped to develop the Falcon compiler for the Azul Zing VM.  Somewhat unfortunately, there's fairly little public information on the project.  (Marketing has never exactly been Azul's strength.)  This page exists to consolidate known public information along with some basic factual overview.  

What is it?
------------
Falcon is a LLVM-based in memory compiler for java bytecode to x86-64 assembly.  It is the top tier compiler for the Azul Zing VM.  It is a heavily optimizing just in time compiler which is fed with high quality profiling information collected in lower tiers of execution.  

Falcon's strength is the ability to emit high quality code resulting in runtime performance for workloads on Zing which absolutely trounces the competition.  Almost more interestingly, because it uses the same underlying compiler technology as Clang, Falcon can generate high performance code for just about anything Clang can.  With Falcon, it is routine and common to see vectorization of common loop idioms native for the platform of execution.

Falcon's largest weakness is compile time.  It's very much not a classic just in time compiler design; there's a reason I called it an "in memory compiler" above.  While the team has done a lot to mitigate this (which I can't talk about here), there do remain cases where this is observable.  

Public Talks
-------------

The best intro talk is probably the keynote that I gave at the 2017 LLVM Developers Meeting.  Beyond that, there have been a number of talks presented by members of the team over the development life cycle.  I'm listing the ones I know of in reverse chronological order.  

* An Update on Optimizing Multiple Exit Loops. Philip Reames. 2020 LLVM Virtual Developers Meeting.
* Control-flow sensitive escape analysis in Falcon JIT. Artur Pilipenko. 2020 LLVM Virtual Developers Meeting.
* Falcon: An optimizing Java JIT. Philip Reames, 2017 LLVM Developers Meeting 
* Expressing high level optimizations within LLVM. Artur Pilipenko. 2017 European LLVM Developers Meeting.
* LLVM for a managed language: what we’ve learned. Sanjoy Das and Philip Reames. 2015 LLVM Developers Meeting
* Supporting Precise Relocating Garbage Collection in LLVM. Sanjoy Das and Philip Reames. 2014 LLVM Developers Meeting

Other Citable Stuff
-------------------
`Introducing the Falcon JIT Compiler <https://www.azul.com/products/zing/falcon-jit-compiler/>`_
