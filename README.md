🌟 MiniLang Parser and AST Generator
This repository contains the full source code for the Lexer and Parser stages of a compiler for MiniLang, a simple, educational programming language. The project is implemented in C and uses Flex and Bison to generate an Abstract Syntax Tree (AST)


Key Features

Lexical Analysis (Flex): Tokenizes variables, keywords (if, while, for, int, float, string), operators (==, +, -, >, <), literals (Int, Float, String), and handles comments.


Syntactic Analysis (Bison): Implements the LALR(1) grammar rules for MiniLang, supporting variable declarations, assignments, arithmetic/relational expressions, and control flow structures (if-else, while, for).


Abstract Syntax Tree (AST): Successfully builds a hierarchical AST structure in memory for all valid input programs, which is printed to the console for visualization

⚙️ Technical Stack

Component,Tool / Language,Role
Language,C (ISO C99/C11),Core implementation language.
Lexer Generator,Flex (WinFlex),Generates lex.yy.c from lexer.l.
Parser Generator,Bison (WinBison),Generates parser.c and parser.h from parser.y.
Build System,GNU Make (MinGW),Manages dependencies and automates the build process.

🚀 Build and Run Instructions (Windows/MinGW)

Prerequisites
GCC (MinGW-W64): C compiler is installed.

WinFlex & WinBison: Both tools must be installed and accessible via your system's PATH.

Build Process
Navigate to the project root directory (minilang_project) and execute the Makefile using the MinGW compatible make command:

# Clean previous build artifacts (if necessary)
# Manual cleanup may be required if 'del' is not aliased to 'rm'
del parser.c parser.h lex.yy.c *.o minilang.exe 

# Build the project
mingw32-make

Running the Parser
Once minilang.exe is created, run the program and use input redirection (<) to feed a source file to the parser (this is mandatory to ensure a correct EOF signal).

Bash

# Example: Using the provided test file
./minilang.exe < test.minilang


Expected Output
If the parse is successful, the program will output the structured Abstract Syntax Tree (AST) to the console:

MiniLang Compiler

=== AST ===
PROGRAM
  STMT_LIST
    VAR_DECL int a
    ... (AST structure follows)

📝 MiniLang Language Specification
MiniLang is a simple language supporting basic data types and essential control flow:


Keywords: if, else, while, for, int, float, string, print, return.


Data Types: int, float, string.


Identifiers: Start with a letter or underscore, followed by letters or digits.


Comments: Single-line (//) and multi-line (/* ... */) are supported.


Operations: +, -, *, /, =, ==, !=, >, <, >=, <=.


Control Flow: if-else, while, and for loops.
