# Phase 2  
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
[Flex Code.txt](https://github.com/FaritZafar/CC/files/9333006/Flex.Code.txt)  
[Symbol Table.txt](https://github.com/FaritZafar/CC/files/9333012/Symbol.Table.txt)  
[Tokens.txt](https://github.com/FaritZafar/CC/files/9333013/Tokens.txt)  

### GCC Compilation  
By flex, compile the c file that is generated that will create the main executable named x.out on the linux, x.exe on the windows, and write -o to override the executable default file name.  

The Video of compiling our code and showing the output is displayed below:  


https://user-images.githubusercontent.com/77563804/184530899-8e930da6-1ecf-4108-aacb-675e5787f1dd.mp4


### Screen Shots  
ScrennShot 1:  
![image](https://user-images.githubusercontent.com/77563804/184532153-0ce0c45a-4001-4e65-8d84-250914be793d.png)  

ScreenShot 2:  
![image](https://user-images.githubusercontent.com/77563804/184532173-0e165275-4753-4788-a6bd-4a269e376401.png)  

  
