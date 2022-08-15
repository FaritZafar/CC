# Phase 2  
Phase 2 required that we write flex code (well documented and commented) that takes as input a program in the language we selected in phase 1 and outputs its tokens with video  
This folder contains 3 files i.e.  
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

[Flex Code.txt](https://github.com/FaritZafar/CC/files/9333735/Flex.Code.txt)  
[Symbol Table.txt](https://github.com/FaritZafar/CC/files/9333012/Symbol.Table.txt)  
[Tokens.txt](https://github.com/FaritZafar/CC/files/9333013/Tokens.txt)  

The Symbol Table and Tokens files contain data that we have inherited in our flex code file while our flex code file contains "Operators", "Keywords" that we have compiled and provided the result in form of "Tokens".  

### Compilation Mechanism  
The mechanism through which we have compiled our code is the same that we did for the Assignment Number 2 of our course i.e. there are several commands that neeed to be run on CMD (Command Line Interface) of our Operating System (Ubuntu) and the commands are as follows:  
* flex lexer.l  
* gcc lex.yy.c -lfl  
* ./a.out  

### GCC Compilation  
By flex, compile the c file that is generated that will create the main executable named x.out on the linux, x.exe on the windows, and write -o to override the executable default file name.  

The Video of compiling our code and showing the output is displayed below:  



https://user-images.githubusercontent.com/77563804/184546452-a8af027c-ec21-4f65-9917-4b5a113abf71.mp4





### Screen Shots  
ScrennShot 1:  
![SS1](https://user-images.githubusercontent.com/77563804/184546579-3748c673-bae1-4c35-899d-83a550562c20.PNG)


ScreenShot 2:  
 ![SS2](https://user-images.githubusercontent.com/77563804/184546465-4b6227ee-9cd5-44f2-a656-dafcf01c7ce4.PNG)


  
