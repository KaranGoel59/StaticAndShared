How To Create static and shared library in C/C++

Create header file with declaration    //calc.hpp 
Create Cpp file with code              //calc.cpp
Create a test program to use that code //main.cpp

compile the cpp

g++ -c calc.cpp
g++ -c main.cpp

create executable : g++ -o program main.o calc.o -lm  //normal

create a STATIC lib : ar crv libcalc.a calc.o

create executable with library
g++ -o main main.o libcalc.a -lm   
g++ -o main main.o -L. -lcalc -lm


SHARED lib : g++ -shared -fPIC -o libcalc.so calc.o  //PIC = position independent code

create executable with library
gcc main.o ./libcalc.so -lm

https://www.bogotobogo.com/cplusplus/libraries.php

ar
creates static libraries.
ldd
lists the shared libraries on which the object binary is dependent.
nm
lists the symbols defined in the symbol table of an object file or a static library.
objdump
to display all the information in an object binary file.
strings
list all the printable strings in a binary file.
strip
deletes the symbol table information.
c++filt
demangle low-level names into user-level names (unix/linux command).
