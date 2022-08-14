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

### Flex Code  
Flex code file have the lexeme patterns and the token classes. We have two methods to set input strings to the executable, first from the standard input in the cl(command line), second from a text file. In flex code file we have inherited files i.e. Symbol Table and Tokens and executed it to give us output as tokens. The code of "Flex Code" file is displayed below:  

/* Parsing the Code */
%{
/* Libraries Included */
#include <stdlib.h>
#include <stdio.h>
#include "symboltable.h"
#include "tokens.h"

/* Declaring the variable */
entry_t** symbol_table;
entry_t** constant_table;
int cmnt_strt = 0;

%}
/* Conditions and their names with variables */
letter [a-zA-Z]
digit [0-9]
ws  [ \t\r\f\v]+
identifier (_|{letter})({letter}|{digit}|_){0,31}
hex [0-9a-f]

/* Exclusive states */
%x CMNT
%x PREPROC

%%
  /* Keywords commonly used in language */
"int"                             {printf("\t%-30s : %3d\n",yytext,INT);}
"long"                            {printf("\t%-30s : %3d\n",yytext,LONG);}
"long long"                       {printf("\t%-30s : %3d\n",yytext,LONG_LONG);}
"short"                           {printf("\t%-30s : %3d\n",yytext,SHORT);}
"signed"                          {printf("\t%-30s : %3d\n",yytext,SIGNED);}
"unsigned"                        {printf("\t%-30s : %3d\n",yytext,UNSIGNED);}
"for"                             {printf("\t%-30s : %3d\n",yytext,FOR);}
"break"                           {printf("\t%-30s : %3d\n",yytext,BREAK);}
"continue"                        {printf("\t%-30s : %3d\n",yytext,CONTINUE);}
"if"                              {printf("\t%-30s : %3d\n",yytext,IF);}
"else"                            {printf("\t%-30s : %3d\n",yytext,ELSE);}
"return"                          {printf("\t%-30s : %3d\n",yytext,RETURN);}

{identifier}                      {printf("\t%-30s : %3d\n", yytext,IDENTIFIER);
                                  insert( symbol_table,yytext,IDENTIFIER );}
{ws}                              ;
[+\-]?[0][x|X]{hex}+[lLuU]?        {printf("\t%-30s : %3d\n", yytext,HEX_CONSTANT);
									insert( constant_table,yytext,HEX_CONSTANT);}
[+\-]?{digit}+[lLuU]?              {printf("\t%-30s : %3d\n", yytext,DEC_CONSTANT);
									insert( constant_table,yytext,DEC_CONSTANT);}
"/*"                              {cmnt_strt = yylineno; BEGIN CMNT;}
<CMNT>.|{ws}                      ;
<CMNT>\n                          {yylineno++;}
<CMNT>"*/"                        {BEGIN INITIAL;}
<CMNT>"/*"                        {printf("Line %3d: Nested comments are not valid!\n",yylineno);}
<CMNT><<EOF>>                     {printf("Line %3d: Unterminated comment\n", cmnt_strt); yyterminate();}
^"#include"                       {BEGIN PREPROC;}
<PREPROC>"<"[^<>\n]+">"            {printf("\t%-30s : %3d\n",yytext,HEADER_FILE);}
<PREPROC>{ws}                       ;
<PREPROC>\"[^"\n]+\"              {printf("\t%-30s : %3d\n",yytext,HEADER_FILE);}
<PREPROC>\n                       {yylineno++; BEGIN INITIAL;}
<PREPROC>.                        {printf("Line %3d: Illegal header file format \n",yylineno);}
"//".*                            ;

\"[^\"\n]*\"     {

  if(yytext[yyleng-2]=='\\') /* check if it was an escaped quote */
  {
    yyless(yyleng-1);       /* push the quote back if it was escaped */
    yymore();
  }
  else
  insert( constant_table,yytext,STRING);
 }

\"[^\"\n]*$                     {printf("Line %3d: Unterminated string %s\n",yylineno,yytext);}
{digit}+({letter}|_)+	        {printf("Line %3d: Illegal identifier name %s\n",yylineno,yytext);}
\n                              {yylineno++;}
"--"			                {printf("\t%-30s : %3d\n",yytext,DECREMENT);}
"++"			                {printf("\t%-30s : %3d\n",yytext,INCREMENT);}
"->"			                {printf("\t%-30s : %3d\n",yytext,PTR_SELECT);}
"&&"			                {printf("\t%-30s : %3d\n",yytext,LOGICAL_AND);}
"||"			                {printf("\t%-30s : %3d\n",yytext,LOGICAL_OR);}
"<="			                {printf("\t%-30s : %3d\n",yytext,LS_THAN_EQ);}
">="			                {printf("\t%-30s : %3d\n",yytext,GR_THAN_EQ);}
"=="			                {printf("\t%-30s : %3d\n",yytext,EQ);}
"!="		                    {printf("\t%-30s : %3d\n",yytext,NOT_EQ);}
";"			                    {printf("\t%-30s : %3d\n",yytext,DELIMITER);}
"{"                             {printf("\t%-30s : %3d\n",yytext,OPEN_BRACES);}
"}"                             {printf("\t%-30s : %3d\n",yytext,CLOSE_BRACES);}
","			                    {printf("\t%-30s : %3d\n",yytext,COMMA);}
"="			                    {printf("\t%-30s : %3d\n",yytext,ASSIGN);}
"("			                    {printf("\t%-30s : %3d\n",yytext,OPEN_PAR);}
")"			                    {printf("\t%-30s : %3d\n",yytext,CLOSE_PAR);}
"["                             {printf("\t%-30s : %3d\n",yytext,OPEN_SQ_BRKT);}
"]"                             {printf("\t%-30s : %3d\n",yytext,CLOSE_SQ_BRKT);}
"-"			                    {printf("\t%-30s : %3d\n",yytext,MINUS);}
"+"			                    {printf("\t%-30s : %3d\n",yytext,PLUS);}
"*"			                    {printf("\t%-30s : %3d\n",yytext,STAR);}
"/"		                        {printf("\t%-30s : %3d\n",yytext,FW_SLASH);}
"%"			                    {printf("\t%-30s : %3d\n",yytext,MODULO);}
"<"			                    {printf("\t%-30s : %3d\n",yytext,LS_THAN);}
">"			                    {printf("\t%-30s : %3d\n",yytext,GR_THAN);}
.                               {printf("Line %3d: Illegal character %s\n",yylineno,yytext);}

%%

int main()
{
  yyin=fopen("testcases/test-case-5.c","r");
  symbol_table=create_table();
  constant_table=create_table();
  yylex();
  printf("\n\tSymbol table");
  display(symbol_table);
  printf("\n\tConstants Table");
  display(constant_table);
  printf("NOTE: Please refer tokens.h for token meanings\n");
}  

### GCC Compilation  
By flex, compile the c file that is generated that will create the main executable named x.out on the linux, x.exe on the windows, and write -o to override the executable default file name.
