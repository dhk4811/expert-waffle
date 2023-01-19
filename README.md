# expert-waffle

# You Don't Know JS Yet

## Scope

Things to know about javascript before proceeding

functions are first-class values
can be assigned and passed around just like number or strings

closure
they maintain their original scope no matter where in the program the functions are eventually executed

Modules
code organization pattern characterized by public methods that have privileged access to hidden variables and functions in the internal scope of the module


Compiled vs. Intepreted
compilation: whole source code is transformed at once
resulting instructions are saves as output that can later be executed


interpretation: source code is transformed line by line

but numerous variations of both compilation and interpretation exist

*scope* is determined during compilation
1. tokenizing/lexing: break up a string of characters into meaningful chunks (tokens)

ex) var a = 2;
is broken up into the following tokens: var, a, =, 2 and ;

2. parsing: taking a stream of tokens and tuning it into a tree of nested elements

Abstract Syntax Tree: collectively represent the grammatical structure of the program

a tree as such could be 
VariableDeclaration(var) - Identifier(a) - AssignmentExpression(=) - NumericLiteral(2)

3. Code Generation
takings the AST and turning it into executable code.

JS -> compilation must happen in mere microseconds

the processing of JS programs occurs in two phases

parsing/compilation first, then execution

syntax errors, early errors, and hoisting all prove the existence of the two phases

**Syntax Errors**
```
var greeting = "Hello";
console.log(greeting);
greeting = ."Hi";
```

-> this code throws a SyntaxError about the unexpected . before the "Hi" string.
-> the console.log(..) function is not executed because JS first parses the entire program before execution


**Early Errors**
in strictmode -> duplicate parameter names are not allowed

