Compiler Construction - Project Report
===============================

# Compiler for Mini C to Python  
This is a mini compiler for a subset of the C language built as part of our Compiler Construction course (110072).  

## Team Members

| Student ID     | Student Name                |
| -------------  | -------------               |
| 63095          | Farit Zafar (Group Leader)  | 
| 63006          | Sumair Ansar                |
| 63761          | Humaira Noor                | 
| 63052          | Ibadullah                   |
| 63064          | Ashar akhtar                |  

## Introduction about compiler  
A compiler is a program that can read a program in one language - the source language - and translate it to an equivalent program in another language - the target language. An important role of the compiler is to detect any errors in the source program during the translation process  

## Structure of a compiler  
There are two parts involved in the translation of a program in the source language into a semantically equivalent target program: analysis and synthesis. The analysis part breaks up the source program into constituent pieces and imposes a grammatical structure on them. It then uses this structure to create an intermediate representation of the source program. The analysis part also collects information about the source program and stores it in a data structure called a symbol table, which is passed along with the intermediate representation to the synthesis part. The synthesis part constructs the desired target program from the intermediate representation and the information in the symbol table. The analysis part is often called the front end of the compiler and the synthesis part is called as the back end. 

## Phases of a compiler  
There are 5 phases of a compiler listed down below:  
1-Lexical Analysis  
2-Parsing  
3-Semantic Analysis  
4-Code Optimization  
5-Code Generation  

Our project has been built as a series of 3 incremental phases, each contributing a key part of the compiler.

| Phase   | Objective                                                                                                                                              |
|---------|----------------------------------------------------------------------------------------------                                                          |
| Phase-1 | Select a mini language and finding its specifications                                                                                                  |
| Phase-2 | A flex code file (well documented and commented) the takes as input a program in the language we selected in phase 1 and outputs its tokens with video |
| Phase-3 | Write YACC code that uses your code from phase 1 and translates a program written in programming language we chose in phase 1 to python code.          |  

## Phase 1  
### Languagae Specification:  
Mini C is a simple language C-like programming language which is used for coding and can be designed for implementation purpose for education (basically it is a software through which we can learn compilation).  
It does not contain the main function for entry point like C, C# or java, all code is on top-level (like Javascript or Python)and it will executed if its inside in the C main.It contains loops, variables,if-else statements, arithmetic i-e {+, -, /, *, %} and comparison i-e {=, ==, >, <,>=, <=, !=},logical {&&, ||, !} operator and and concatenation of string.The user defined functions are not supportable in it.  
The language specifications for Mini C can be found here:  
1- http://compilersatkiet.22web.org/lang(2).pdf?i=1  
2- http://www2.cs.arizona.edu/~debray/Teaching/CSc453/DOCS/cminusminusspec.html  
The Languagae Selected:  
The selected language is mini C.

### Accepted Data Types:  
String  
Bool  
Int (signed 32 bit)  
Double (64 bit IEEE 754 Floating Point)

### Expression for Input/Output/Built-in Statements:  
Print a string (to sdout)  
Convert a number or boolean to string  
Read a number (from stdin)  
Some Scopes:
Nested Scopes do support the variables and they work the same like as in other languages i-e Java, C. {} can be nested in it and the variables are only define at the end of scope also the variables re-declaration only exist in parents scopes.
 
### Example Code For our Project  
### Simple if (nesting not allowed)  
if then  
Endi

### Switch Statement (nesting not allowed)  
Switch()  
Cases  
Value 1:  
Break;  
 Value n:  
break;  
Endcase

### Repetition Statement (nesting not allowed)  
A. Repeat  
        Until ()  
B. While (relational expression)  
Endwhile  
C. For = start value, end value, inc/dec  
………  
Endfor

### I/O Statement  
a. Input ;  
b. Output ;

### Program Structure  
Decleration:  
Start  
End



