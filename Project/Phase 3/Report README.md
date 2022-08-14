Compiler Construction - Project 
===============================

# Compiler for Mini C to Python
This is a mini compiler for a subset of the C language built as part of our Compiler Construction course (110072).

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

# Phase 1  
he language specifications for Mini C can be found here:  
1- http://compilersatkiet.22web.org/lang(2).pdf?i=1  
2- http://www2.cs.arizona.edu/~debray/Teaching/CSc453/DOCS/cminusminusspec.html  
# Example Code For our Project  
## Simple if (nesting not allowed)  
if then  
Endi

## Switch Statement (nesting not allowed)  
Switch()  
Cases  
Value 1:  
Break;  
 Value n:  
break;  
Endcase

## Repetition Statement (nesting not allowed)  
A. Repeat  
        Until ()  
B. While (relational expression)  
Endwhile  
C. For = start value, end value, inc/dec  
………  
Endfor

## I/O Statement  
a. Input ;  
b. Output ;

## Program Structure  
Decleration:  
Start  
End



