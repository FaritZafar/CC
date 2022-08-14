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
| Phase-2 | A flex code file (well documented and commented) that takes as input a program in the language we selected in phase 1 and outputs its tokens with video |
| Phase-3 | Write YACC code that uses your code from phase 1 and translates a program written in programming language we chose in phase 1 to python code.          |  

## Phase 1  
In Phase 1 we selected a language and researched on it and found its specifications which helped us in designing our compiler  

### Languagae Specification:  
Mini C is a simple language C-like programming language which is used for coding and can be designed for implementation purpose for education (basically it is a software through which we can learn compilation).  
It does not contain the main function for entry point like C, C# or java, all code is on top-level (like Javascript or Python)and it will executed if its inside in the C main.It contains loops, variables,if-else statements, arithmetic i-e {+, -, /, *, %} and comparison i-e {=, ==, >, <,>=, <=, !=},logical {&&, ||, !} operator and and concatenation of string.The user defined functions are not supportable in it.  
The language specifications for Mini C can be found here:  
1- http://compilersatkiet.22web.org/lang(2).pdf?i=1  
2- http://www2.cs.arizona.edu/~debray/Teaching/CSc453/DOCS/cminusminusspec.html  
The Languagae Selected:  
The selected language is mini C.

### Accepted Data Types:  
* String  
* Bool  
* Int (signed 32 bit)  
* Double (64 bit IEEE 754 Floating Point)

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

## Phase 2  
Phase 2 required that we write flex code (well documented and commented) that takes as input a program in the language we selected in phase 1 and outputs its tokens with video  
Phase 2 folder contains 3 files i.e.  
|Files         |
|------------  |
|1-Flex Code   |
|2-Symbol Table|
|3-Tokens      |  

The mechanism through which this program works is that we have called the files "Symbol Table" and "Tokens" which contain the code that we have written, in our "Flex Code" and in turn the "Flex Code" file is giving us output in the term of tokens.  

### Description of Grammar  

'a' ~~ is a terminal symbol.  
a+ ~~ one or more occurrences of a  
a* ~~ zero or more occurrences of a  
a? ~~ zero or one occurrences of a.  
a | b = alternative (a or b).  
() ~~ group, for example (a |b) c (a b)  

### Flex Code  
Flex code file have the lexeme patterns and the token classes. We have two methods to set input strings to the executable, first from the standard input in the cl(command line), second from a text file. In flex code file we have inherited files i.e. Symbol Table and Tokens and executed it to give us output as tokens.The flex code, symbol table and tokens files can be found in the "Phase 2" folder of our project and are also displayed below:  
[Flex Code.txt](https://github.com/FaritZafar/CC/files/9333006/Flex.Code.txt)  
[Symbol Table.txt](https://github.com/FaritZafar/CC/files/9333012/Symbol.Table.txt)  
[Tokens.txt](https://github.com/FaritZafar/CC/files/9333013/Tokens.txt)

The Video of compiling our code and showing the output is displayed below:  


https://user-images.githubusercontent.com/77563804/184530899-8e930da6-1ecf-4108-aacb-675e5787f1dd.mp4



### GCC Compilation  
By flex, compile the c file that is generated that will create the main executable named x.out on the linux, x.exe on the windows, and write -o to override the executable default file name.  

### The problems we face:  
### In Language grammar interpreting:  
It took a long time to understand the Mini-C language grammar,but as soon as we study things from our course and internet the things start making sense and become understandable.  
### In the scanner with parser integration:
It was very difficult to find flex and yacc programs integration so we found an easy example on our website of course and we took help from it.  
### Elimination of the grammar conflicts in parser:
At the initial implementation of parser we faced huge number of conflicts in grammar because there are many places where we have clear grammar without (fuzzy rules) but the yacc cannot handle it because it generates LALR(1) parsers by default with limited look ahead ability.  
By specifying the associativity property of different operators, we resolve many shift/reduce issues in the yacc program, and by opening and closing curly braces {} the remaining conflicts were eliminated and also we resolve some statements by using various precedence rules to associate else with the nearest if.  

## Phase 3  
Write YACC code that uses code from phase 1 and translates a program written in programming language we selected in phase 1 to python code.  

### About YACC  
YACC (yet another compiler-compiler) is an LALR(1) (LookAhead, Left-to-right, Rightmost derivation producer with 1 lookahead token) parser generator. YACC was originally designed for being complemented by Lex.  
Some important points to highlight about YACC are listed below:  
Input: A CFG- file.y  
Output: A parser y.tab.c (yacc)  
* The output file "file.output" contains the parsing tables.  
* The file "file.tab.h" contains declarations.  
* The parser called the yyparse ().
* Parser expects to use a function called yylex () to get tokens.
