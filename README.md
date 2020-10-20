# Bzo Compiler

![Bzo Logo](assets/bzologo.png)

This is some code for the self-hosted version of the Bzo compiler.

This version will include extra features not available in the bootstrapping
version and will hopefully be better architected.


**Language Concept:**

At the end of the day, a programmer's job is not to fill text files, but rather to create an executable file that solves a problem with a certain set of constraints.

The two main benefits of high-level languages over assembly (or machine code!) are automation and analysis. Automation removes much of the tedium and human error from building complex systems, and analysis narrows the space of possible programs to one where correct and useful programs are more easily reached than programs that are not.

However, from a certain perspective, programming languages have generally gotten less expressive. There are a wide variety of features available to assembly programmers that are almost completely unavailable in higher-level languages. Code can be structured in unique ways. Usually inaccessible features like floating point rounding modes can be used. Rare features like overflow detection become easily available. The overall structure of the executable can even be controlled.

When moving to even higher-level languages, access to features like pointers, direct memory management and layout, and many others are lost. In some languages, access to basic features like integers are lost as well.

Moving up the abstraction hierarchy is often associated with the removal of features deemed too "low-level."


The goal of Bzo is to create a language that bridges the gap between the extremely high-level, and the extremely low-level; a language where the executable file can be laid out on the byte level if the programmer so chooses, but where advanced metaprogramming, code synthesis, and higher-order programming is available as well.
