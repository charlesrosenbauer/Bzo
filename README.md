# Bzo Compiler

This is some code for the self-hosted version of the Bzo compiler.

This version will include extra features not available in the bootstrapping
version and will hopefully be better architected.


Layout Plans:

* Main Passes:
  * Lexer - convert file to sequence of tokens, symbol table, and comment blocks (in case users want to analyze the comments)
  * Parser - convert sequence of tokens into parser AST
  * Namespace Mapping - create table mapping ids to definitions, and files to visibility sets
  * Modeller - convert types to Type trees, and expressions to SSA form
  * Checker - type checking, type class checking, etc.
  * Analyzer - perform dependency analysis, lattice analysis, etc.
  * Transformer - apply transforms, e.g. allocators, etc.
  * Optimizer - software pipelining, superoptimization, inlining, vectorization, etc.
  * Codegen - generate machine code, perform linking, etc.
