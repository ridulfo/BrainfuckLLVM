# Brainfuck LLVM
A LLVM compiler for the esoteric programming language brainfuck.

To run the compiler you have to follow these steps

1. Create a conda env and install the python library `llvmlite`.
1. Run `python brainfuck.py`
1. Run `clang ir.ll`
1. Run `./a.out`

The program should print `www.nicolo.io`.

**Currently only supported on Darwin ARM64 systems. That is, if you are running OSX on an apple silicon chip, can run it!**