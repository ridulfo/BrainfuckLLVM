# Brainfuck LLVM
A LLVM compiler for the esoteric programming language brainfuck.

Here is a [gist](https://gist.github.com/ridulfo/3a97bc4692607ad5a351e3c7d84624a4) showing the LLVM IR.

To run the compiler you have to follow these steps

1. Create a conda env and install the python libraries `llvmlite` and `fire`.
1. Create a file with your brainfuck code: `echo "------[-->+++<]>...---[++>---<]>.--[-->+++++<]>.-----.------.++++++++++++.---.+++.[->+++++<]>+++.+[--->+<]>++++.++++++." > code.bf`
1. Compile to LLVM IR: `python brainfuck.py --input-file code.bf --output-file ir.ll`
1. Compile LLVM to machine code: `clang ir.ll -o program`
1. Run the executable `./program`

The program should print `www.nicolo.io`.

### Help

`python brainfuck.py --help`
```
NAME
    brainfuck.py

SYNOPSIS
    brainfuck.py <flags>

FLAGS
    --input_file=INPUT_FILE
        Type: Optional[]
        Default: None
    --input_code=INPUT_CODE
        Type: Optional[]
        Default: None
    --tape_length=TAPE_LENGTH
        Default: 100
    --output_file=OUTPUT_FILE
        Type: Optional[]
        Default: None
```

**Currently only supported on Darwin ARM64 systems. That is, if you are running OSX on an apple silicon chip, you can run it!**
