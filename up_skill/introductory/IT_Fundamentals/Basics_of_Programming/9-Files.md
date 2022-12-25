# Files

## Introduction to Files

A **computer file** is a computer resource that has its own name and extensions
for discretely writing data to a computer storage device. File names have two parts
separated by a period: the file name and the extension. Files are usually organized
into a **file system** that keeps track of the location of files on a disk and allows
us to access them. Or, in other words, it is a collection of software tools for
accessing files. There are quite a few file systems, and naming conventions for
files may differ slightly. Files can be edited and transferred over the Internet
to a computer system. Using computer programs, a person can open, read, modify,
save, close, copy a computer file any number of times.

Some types of files can store several types of information at once. For example,
an **archive** is a file that contains one or more other files and/or folders as
well as metadata. Archives are used to combine many files of various types into
a single container file for the convenience of storing and transferring information,
or simply to compress data. To create archives and work with them, archiving programs
are used. Archives can maintain the folder structure, contain service information
for detecting and correcting errors, comments, and other information. In some archive
formats, data can be encrypted using a password. So, among the most popular in the
Windows environment are ZIP, RAR, 7z, and in macOS - the SIT format.

For example, consider the differences between using a file and using an array:

- Files, unlike arrays, are external resources. This helps to save data before a
  program closes, or read such saved data when starting a program.

- Usually, stack and dynamic memory, where a program allocates arrays, are significantly
  less than the storage available for saving files.

- You have to use file system tools to work with files. Usually, a programming
  language provides a special API to do this. A file must be opened to read/write
  data, and closed after that to let other programs safely work with it.

- Every time you read/write files, the file system performs operations, like hard
  drive memory access. This means that operating data from files takes more time
  than operating arrays.

- Arrays contain sets of values of some data type provided by a programming language
  or a developer. Files are limited and contain bytes or characters (which are
  effectively the same bytes). This means that you have to transform bytes sequences
  to the values of a needed datatype and vice versa when reading/writing files.
  Fortunately, most languages have built-in tools to help you with that.

Files are classified by the type of components:

- text files:

  - A text file is a sequence of characters or a collection of variable-length
    character strings.
  - Text files can be viewed and edited via text editors.
  - The examples of known text file extensions are: *.txt, *.bat, *.c, *.py, *.java
  - Special characters are used to indicate a line terminator.

- binary files:

  - A binary file is a sequence of bytes that corresponds to the representation
    of some data without splitting into lines with the possibility of direct access
    (random access) to any part of it.
  - A binary file is a sequence of data, the structure of which is defined by a program.
  - The examples of known binary file extensions include: *.bin, *.jpg, *.mov,
    *.gif, *.zip

Files are classified by the method of accessing them:

- files of sequential

- arbitrary access

A text file is a kind of binary file and consists of bits. Just a different data
recording format. Without the knowledge of the code page, you won't be able to normally
read a text file.

To work with any file, the main operations that need to be done are:

- **Opening the file** so that you can refer to it. When you open the file, some
  errors can occur, such as the file may not exist, it may be the wrong type of
  the file, you may not have permission to work with the file, etc. You should take
  into account all these errors.

- **Directly processing the file data** (writing, reading, searching, etc.). It
  should also be remembered here that we are not working with random access memory
  but with a buffered stream, which adds its own specifics.

- **Closing the file**. Since the file is an external resource to the program,
  if it is not closed, it will continue to be in memory, possibly even after the
  program is closed (for example, you probably tried to delete an open file or
  make changes, etc.), or some data may not be written. In addition, sometimes it
  is necessary not to close, but to "reopen" the file in order, for example, to
  change the access mode.

Do not open binary files (such as jpeg, exe, doc) in text mode as this may lead
to the files being corrupted.

An internal logical name is assigned to each file in a program, which is used later
when referring to it. The logical name (a file identifier) is a pointer to the file,
i.e. to a memory area that contains all the necessary information about the file
in C or the object of a library class in Java, Python, and JavaScript. The format
for declaring a file name or a path to it depends on the syntax of the language
and will be discussed below.

## Opening - Closing a File

in C

The format for declaring a pointer to a file in C is as follows:

`FILE *pointerName;`

FILE is a structured type described in the `stdio.h` library, which is associated
with a physical file and contains all the necessary information to work with it
(a pointer to the current position in the file, access type, etc.).

Before starting to work with a file, i.e. to be able to read or write information
to a file, it must be opened for access.

`fopen(char *fileName, char *mode);`

**fopen()** - It is a file opening function that, when the file is successfully
opened, returns a pointer to a **FILE** structure, called a file pointer. The value
returned by the function must be saved and used to reference the open file. If
there was an error opening the file, **NULL** is returned.

**char *fileName** - It specifies the physical location (path) and the name of the
file to open. If the path to the file is not specified, its location will be the
current folder. For example: "D:\\test\\test.txt" - a file named **test**, with the
**txt** extension, located on the hard drive in the work folder. The backslash "\"
is written twice as a special character in a string.

**char *mode** - It is the file access type that can take the values shown in the
table below.

File Access Type Table:

"r" - Opens a file for reading. If the file is in read mode, the data is not deleted
if the file already exists on the system. If there is no such file, then an error
occurs.

"w" - Opens a file for writing. If the file exists, then its contents are lost. If
the file does not exist at all, a new file is created.

"a" - Opens a file to write to the end of the file (append). If the file does not
exist, then it is created. The previously added file content does not change.

"r+" - Opens a file for reading and writing from the beginning. The file must exist.

"w+" - Opens a file for reading and writing. If the file exists, then its contents
are lost.

"a+" - Opens a file for reading and writing at the end of the file, appending
to the file. If the file does not exist, then it is created.

Combinations of the above literals can also be appended with:

"t" – opens a file in text mode

"b" – opens a file in binary mode

The following access modes are possible: "w + b" or "wb +", "rw +", "w + t",
"rt +", etc. If the mode is not specified, then a file is opened in **text** mode.
After you finish working with a file, access to it must be closed using the function
`fclose()`. To do this, we need to pass a pointer to **FILE** to the specified
function which was received when it was opened by the `fopen()` function. The
`fclose()` function returns 0 if a file was successfully closed, and EOF (end of
file) if an error has occurred while closing a file.

`fclose(fileName);`

After closing a file, the same file pointer can also be used with other files or
to the same file, opened with a different mode.

The following function has been introduced to close multiple files:

`void fcloseall(void);`

For instance, consider the example in which we open a text file to record information
about ourselves in the future:

```C
#include <stdio.h>
#include <stdlib.h>

int main()
{
    FILE  *fileName = fopen("my_information.txt", "w+t");
    if(fileName == NULL)
    {
        printf("Error. Could not open or unable to create a file.\n");
        return 0;
    } else
        printf("The file is opened successfully.\n");

    //some block of code

    fclose(fileName);
    return 0;
}
```

And the result is:

`The file is opened successfully.`

In this case, a file with the fileName pointer in the current folder
named my_information.txt opens for writing.

Python

In Python, files are also divided into text and byte (binary) files. Text files
contain character data and strings; binary files are presented as streams of bytes.
For example, image files are read byte by byte.

Working with binary files is a little more complicated, and they are often handled
using special Python modules. Therefore, we will consider basic methods for text
files.

Before starting to work with a file, i.e. to be able to read or write information
to a file, it must be opened for access using the built-in open() function. The
**open()** function has many parameters.

For now, 3 arguments are important to us.

`open(file, mode, encoding)`

**open()** - A file open function. The open() function returns a file-type object.
It must be either immediately associated with a variable so as not to lose it, or
read immediately. If it cannot be found, you will receive an IOError notification.

**file** - A file name or a name with an address if the file is not located in the
directory where the script is located.

**encoding** - This argument specifies the encoding in the text mode of reading
a file.

**mode** - It is a file access type in which a file is opened. Values are shown
in the table below.

File Access Type Table:

'r' - Opens a file for reading. If the file is in read mode, the data is not deleted
if the file already exists on the system. If there is no such file, then an error
occurs. If the file is open in read mode, then writing to it is impossible, it
cannot be written or changed.

'w' - Opens a file for writing. If the file exists, then its contents are lost. If
the file does not exist at all, a new file is created. If the file is open in write
mode, then data can only be written to it, it cannot be read.

'x' - Creates a new file for writing. If the name of an existing file is specified,
an exception will be generated. No data loss will occur in an existing file.

'a' - Opens a file to write to the end of the file (append). If the file does not
exist, then it is created. The previously added file content does not change.

'r+' - Opens a file for reading and writing from the beginning. The file must exist.

'w+' - Opens a file for reading and writing. If the file exists, then its contents
are lost.

'a+' - Opens a file for reading and writing at the end of the file, appending to
the file. If the file does not exist, then it is created.

Combinations of the above literals can also be appended with:

"t" – opens a file in text mode, can be omitted
"b" – opens a file in binary mode

The following access modes are possible: 'wb', 'rb', 'wb+', 'rb+', etc. If the mode
is not specified, then a file is opened in 'rt' mode.

After working with a file, access to it must be closed using the function close().
This method of the file object discards all unwritten information and closes the
file object, after which no more writing can be made.

`file_object.close()`

After closing a file, the same file pointer can also be used with other files or
to the same file, opened with a different mode. Also, Python automatically closes
a file when the reference object of a file is reassigned to another file.

For instance, consider the example in which we open a text file and print the file
name to the console:

```Python
my_file = open("My_information.txt", "w")
print ("Name of the opened file:", my_file.name)
my_file.close()
```

The result:

Name of the opened file: My_information.txt
Note: a function file.name returns the name of the file.

Another way to close a file is by using the with statement, which closes the file
when the block inside the with statement is exited. In this case, we don't need to
explicitly call the close() method. It is done internally.

## Functions for Writing to or Reading Data from a File

The main actions while working with files are writing and reading information.

All actions for reading and writing data to a file can be divided into three groups:

- Character-by-character input-output operations.
- Operations of line input-output.
- Input/output operations in blocks.

Let us consider the examples of functions for writing to or reading data from a file
in C, Python.

### C

There are many functions in the C library in order to open, read, write, search,
and close a file. A list of file functions is given below.

#### Work with Text Files

To work with text files, the most commonly used functions are `fprintf(), fscanf()`,
`fgets(), fputs()`. The parameters and actions of these functions are similar to
the previously discussed `printf(), scanf(), gets(), and puts()` functions. The
difference is that `printf()` and others work with a monitor screen and a keyboard
by default, while `fprintf()` and others work with a file whose pointer is one of
the parameters. In C, when you write to a file, newline characters '\n' must be
explicitly added. The stdio.h library offers the necessary functions to write to
or read data from a file.

#### Writing to a File

`fputc(char, filePointer)`: It writes a character into the file pointed to by a
`filePointer`.

`fputs(str, filePointer)`: It writes a string into the file pointed to by a `filePointer`

`putw(int, filePointer)`: It writes an integer into the file pointed to by a `filePointer`

`fprintf(filePointer, str, variableLists)`: It writes data into the file pointed
to by a `filePointer`.

#### Reading Data from a File

`fgetc(filePointer)`: It returns the next character from the file pointed to by
a filePointer, i.e. it reads the character from the file. When the end of the file
has been reached, the EOF is sent back.

`fgets(buffer, n, filePointer)`: It reads n-1 characters from the file and stores
the string in a buffer in which the NULL character '\0' is appended as the last
character.

`getw(filePointer)`: It reads an integer from the file.

`fscanf(filePointer, type_specifiers, variables)`: It reads data from the file,
and parses and analyzes the data. While reading characters from the file, it assigns
the input to a list of variable pointers variables using type specifiers. Note
that as with scanf, fscanf stops reading a string when a space or a newline is
encountered.

```C
#include <stdio.h>
#include <stdlib.h>

struct myInfo
{
    char name[40];
    int age;
};

int main()
{
    struct myInfo info;
    FILE *fileName;

    if(!(fileName = fopen("My_information.txt", "w+t")))
    {
        printf("Error. Could not open or unable to create a file.\n");
        return 0;
    } else
      {
        printf("The file was opened successfully.\n");
      }

    printf("Enter full name: ");
    fgets(info.name, sizeof(info.name), stdin);
    fflush(stdin);
    for ( int i = 0; i < sizeof(info.name); i++ )
    {
        if ( info.name[i] == '\n' )
        {
            info.name[i] = '\0';
            break;
        }
    }
    printf("Enter your age: ");
    scanf("%d", &info.age);
    fprintf(fileName, "You name: %s and your age: %d years", info.name, info.age);

    fclose(fileName);

    printf("\nYour information:\n");
    if(!(fileName = fopen("My_information.txt", "r+t")))
    {
        printf("Error. Could not open the file\n");
        return 0;
    }
    char buff[225];
    while(fscanf(fileName, "%s", buff)!=EOF)
    {
        printf("%s ", buff );
    }

    fclose(fileName);
    return 0;
}
```

The result:

The file was opened successfully.
Enter full name: Tom Hardy
Enter your age: 43
Your information:
Your name: Tom Hardy and your age: 43 years.

By looking at the `My_information.txt` file with any text editor, you can make sure
that the data located in it is the same as on the screen.

Text files store data as text. This means that if, for example, we write our age
as a two-digit number to a file, then 2 characters are written, and this is 2 bytes
of data, despite the fact that the number is an integer type. In addition, the output
and input of data are formatted, that is, every time we read a number from a file
or write to a file, the number is converted to a string.

#### Work with Binary Files

Above, we looked at the example in which we used a structure. In this case, it is
better to process such information using binary files which can be read and written
in blocks.

##### Writing to a File Binary Files

`fwrite(buff, size, n, filePointer)`: It writes to the file filePointer n blocks
of size bytes, each from the memory area, with the address buff.

##### Reading Data From a File

`fread(buff, size, n, filePointer)`: It reads from the file filePointer n blocks
of size bytes, each into the memory area whose address is buff. If successful,
the function returns the number of blocks read.

Every open file has a hidden pointer to the current position in it. When the file
is opened, this pointer is set to the position specified by the file mode, and all
operations in the file will be performed with data starting at that position. With
each reading from (writing to) the file, the pointer is shifted by the number of
bytes read (written). This is sequential data access. When it is necessary to read
or write data in an arbitrary order, this can be done by setting the pointer to
some given position in the file using the `fseek()` function.

`int fseek(FILE * filePointer, long offset, int whence);`

The `offset` parameter specifies the number of bytes by which the pointer should
be offset according to the `whence` parameter. The values of the whence parameter
are shown below:

SEEK_SET - 0 - The offset is performed from the beginning of the file.
SEEK_CUR - 1 - The offset is performed from the current cursor position.
SEEK_END - 2 - The offset is performed from the end of the file.

The offset value can be either positive or negative, but you cannot move beyond
the beginning of the file.

Let us modify our previous example and demonstrate how to work with binary files.

```C
#include <stdio.h>
#include <stdlib.h>

struct myInfo
{
    char name[40];
    int age;
};

int main()
{
    struct myInfo info;
    FILE *fileName;

    if(!(fileName = fopen("My_information.bin", "wb+")))
    {
        printf("Error. Could not open or unable to create a file.\n");
        return 0;
    } else
        printf("The file was opened successfully.\n");

    printf("Enter full name: ");
    fflush(stdin);
    gets(info.name);

    printf("Enter your age: ");
    scanf("%d", &info.age);

    fwrite(&info, 1,sizeof(info), fileName);
    fclose(fileName);

    printf("\nYour information:\n");
    if(!(fileName = fopen("My_information.bin", "rb+")))
    {
        printf("Error. Could not open the file\n");
        return 0;
    }
    fread(&info, sizeof(info), 1,fileName);
    printf("You name: %s and your age: %d years \n", info.name, info.age);

    fclose(fileName);
    return 0;
}
```

The result:

The file was opened successfully.
Enter full name: Tom Hardy
Enter your age: 43
Your information:
Your name: Tom Hardy and your age: 43 years

#### in Python

As you already know, to write data to a file in Python, we need to open it in one
of the possible write modes w, append or exclusively create x; and to read a file,
we have to open the file in read mode r. Various built-in methods are available
for this.

##### Writing to a File in Python

`write(str)`: It writes a string or a sequence of bytes to a file (for binary files)
and returns the number of characters written to the file.

`writelines(lines)`: It writes a list of lines without delimiters (such as line breaks)
to a file.

##### Reading Data from a File in Python

`read(size)`: It reads from a file the size amount of data and returns a newline
as '\n'. If the size parameter is not specified, it reads up to the end of the file
and returns the data that was read. Upon reaching the end of the file, with further
reading we get an empty string.

`readline()`: It reads a string from the specified position to the end of the string
from the file object and returns it. It reads at most n bytes/characters if specified.

We can read a file line-by-line using a for loop. This is both efficient and fast.

For instance, consider the example in which we open a text file, write to and read
the information from the file:

```Python
with open("my_information.txt",'w',encoding='utf-8') as my_file:
    my_file.write("Name is Tom Hardy.\n")
    my_file.write("I am an English actor and producer.\n")
    my_file.write("I am active in charity work.\n")
with open("my_information.txt",'r',encoding='utf-8') as my_file:
    print(my_file.readline())
    print(my_file.readlines())
```

The result:

Name is Tom Hardy.

['I am an English actor and a producer.\n', 'I am active in charity work.\n']

As in C, Python has the current cursor in the file (position), and all operations
with data in the file will be performed starting from that position. We can change
the current position in the file using the `seek(offset[, from])` method. The offset
argument indicates the number of bytes to be moved. The from argument specifies the
reference position from where the bytes are to be moved:

SEEK_SET - 0 - The offset is performed from the beginning of the file. The offset
should be zero or positive.

SEEK_CUR - 1 - The offset is performed from the current cursor position. The offset
may be negative.

SEEK_END - 2 - The offset is performed from the end of the file. The offset is
usually negative.

And to find out the current position, we can use the `tell()` method.

Let us look at changing the position of the cursor in our example:

```Python
with open("my_information.txt",'w',encoding=  'utf-8') as my_file:
    my_file.write("Name is Tom Hardy.\n")
    my_file.write("I am an English actor and a producer.\n")
    my_file.write("I am active in charity work.\n")
with open("my_information.txt",'r',encoding='utf-8') as my_file:
    print(my_file.readline())
    my_file.seek(0, 0)
    print(my_file.readlines())
```

The result:

Name is Tom Hardy.

['Name is Tom Hardy.\n', 'I am an English actor and a producer.\n',
'I am active in charity work.\n']

In this case, the first line will be displayed twice.






