Compiler Construction - Project 
===============================

# Compiler for Mini C to Python
This is a mini compiler for a subset of the C language built as part of our Compiler Construction course (110072).  

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

It has been built as a series of 3 incremental phases, each contributing a key part of the compiler.

| Phase   | Objective                                                                                                                                              |
|---------|----------------------------------------------------------------------------------------------                                                          |
| Phase-1 | Select a mini language and finding its specifications                                                                                                  |
| Phase-2 | A flex code file (well documented and commented) the takes as input a program in the language we selected in phase 1 and outputs its tokens with video |
| Phase-3 | Write YACC code that uses your code from phase 1 and translates a program written in programming language we chose in phase 1 to python code.          |           


### Team Members

| Student ID     | Student Name                |
| -------------  | -------------               |
| 63095          | Farit Zafar (Group Leader)  | 
| 63006          | Sumair Ansar                |
| 63761          | Humaira Noor                | 
| 63052          | Ibadullah                   |
| 63064          | Ashar akhtar                | 

