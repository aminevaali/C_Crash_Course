# Working with files in C

C lets you open a file, write in it, read from it, append to it and finally close the file.

## Required library

To work with files in c you need to include `stdlib.h` in your program

```C
#include <stdlib.h>
```

## How to open a file?

Your user space program can't access files directly. And must grant permission from the operating system to access a file. Thus there is a function named `fopen(filePath, mode)` that asks the OS and opens a file in your program. `filePath` is the relative or absolute path of the file. and `mode` is the way our program treats with that file.


e.g. Making a file named `myFile.txt` with the content of "Hello World"
```C
#include <stdio.h>
#include <stdlib.h> // this library provides utilities to work with files
#include <string.h> // this is necessary to use strlen() function

int main()
{
    FILE *fptr; // making a pointer to file
    fptr = fopen("C:/Users/Amin/Desktop/myFile.txt", "w"); // assigning the file pointer value to fptr
    const char strToWrite[20] = "Hello World"; // making a string to write in the file
    fwrite(strToWrite, sizeof(char), strlen(strToWrite), fptr); // writing the string in the file pointed by fptr
    fclose(fptr); // closing the file after writing in it
    return 0;
}
```