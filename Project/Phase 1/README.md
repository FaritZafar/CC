# Language Specifictions:  
The language specifications for Mini C can be found here:  
1- http://compilersatkiet.22web.org/lang(2).pdf?i=1  
2- http://www2.cs.arizona.edu/~debray/Teaching/CSc453/DOCS/cminusminusspec.html  

## The Languagae Selected:
The selected language is mini C.

## Languagae Specification:
Mini C is a simple language C-like programming language which is used for coding and can be designed for implementation purpose for education (basically it is a software through which we can learn compilation). Our selected mini language is exactly not a replica of what is specified in the document as we had to tweak it according to our needs because of several reasons. One being that some specifications and samples were not of C language explicitly. 

## Designing C language:
We used Flex to perform lexical analysis on a subset of the C programming language.
Flex is a lexical analyzer generator that takes in a bunch of descriptions of  tokens that are possible and
produces a C document that performs lexical analysis and distinguishes the tokens.
Here we define the construction and functionality of the scanner:
This document is separated into the accompanying sections:

 ● Functionality: Contains a description of our Flex program and the range of tokens that it can recognize and the strategies for error handling.
 
 ● Symbol table and Constants table: Contains an outline of the design of the image and constants table which contain information on the  lexemes recognized during the    lexical analysis.
 
 ● Organisation of Code: Contains a descriptive knowledge of the documents used for lexical analysis.
 
 ● Source Code: Contains the source code used for lexical analysis.  

### Accepted Data Types:  
* String  
* Bool  
* Int (signed 32 bit)  
* Double (64 bit IEEE 754 Floating Point)

### Expression for Input/Output/Built-in Statements:  
* Print a string (to sdout)  
* Convert a number or boolean to string  
* Read a number (from stdin)  
* Some Scopes:
* Nested Scopes do support the variables and they work the same like as in other languages i-e Java, C. {} can be nested in it and the variables are only define at the end of scope also the variables re-declaration only exist in parents scopes. 

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


