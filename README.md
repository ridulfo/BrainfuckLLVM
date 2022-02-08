# Brainfuck LLVM
A LLVM compiler for the esoteric programming language brainfuck.

To run the compiler you have to follow these steps

1. Create a conda env and install the python libraries `llvmlite` and `fire`.
1. Create a file with your brainfuck code: `echo "------[-->+++<]>...---[++>---<]>.--[-->+++++<]>.-----.------.++++++++++++.---.+++.[->+++++<]>+++.+[--->+<]>++++.++++++." > code.bf`
1. Compile to LLVM IR: `python brainfuck.py --input-file code.bf --output-file ir.ll`
1. Compile LLVM to machine code: `clang ir.ll -o program`
1. Run the executable `./program`

The program should print `www.nicolo.io`.

For help: `python brainfuck.py --help`

**Currently only supported on Darwin ARM64 systems. That is, if you are running OSX on an apple silicon chip, you can run it!**