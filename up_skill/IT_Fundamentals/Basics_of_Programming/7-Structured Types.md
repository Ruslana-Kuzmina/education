# Structured Types / Dinamic Data Structures

## Array. Passing Arrays

### Arrays in C

If we plan to use simple variables in programming, then we need three variables
of the int data type, and the C program is as follows:

```C
#include <stdio.h>

int main() {
   int hulk_movie;
   int ironMan_movie;
   int spiderMan_movie;

   hulk_movie = 12;
   ironMan_movie = 9;
   spiderMan_movie = 10;

   printf("%d movies with Hulk.\n", hulk_movie);
   printf("%d movies with Iron Man.\n", ironMan_movie);
   printf("%d movies with Spider Man.\n", spiderMan_movie);
}
```

The result:

12 movies with Hulk.
9 movies with Iron Man.
10 movies with Spider Man.

At first glance, everything is simple. But what if you need to count movies for
all superheroes from any MCU (Multipoint Control Unit). The number of superheroes
an range from several to thousands. For this purpose, programming languages use
a complex data type — an array, which is an ordered collection of a fixed size
comprising elements of the same data type. An array is used to store a set of data,
but it is often more useful to think of an array as a collection of variables of
the same type. And the array declaration for our example might looks as follows:

`int superhero_movies[3] = {12,9,10};`

In this line of code, you can see the following parts:

int - Declares the base type of the array elements (integer, real, char)

superhero_movies - Declares the name of the array

[3] - The number of elements in an array is called its size. The **size** of an
array is usually given after the name in square brackets, which indicates the number
of elements in the array. When describing arrays, square brackets are a syntax
element, not an indication of an optional construct. It is preferable to enter
the sizes of arrays from the keyboard as values of integer variables or to set
them using named constants, since if we need to change it, with this approach it
is enough to adjust the value of the constant in just one place in the program.

{...} - Sets a list of initial values of an array; if necessary, initializes data
when declaring. It may be absent. The number of values in curly braces {} cannot
be greater than the number of elements that we declare for the array in square
brackets [].

`type arrayName [ arraySize ];`

In C, the size of an array, together with the type of its elements, determines
the amount of memory required to accommodate the array, which is performed at
compile time, so the size of the array is specified only by a constant or a constant
expression. You cannot specify an array of variable size; there is a separate
mechanism for this called **dynamic memory allocation** (this is described in the
subsequent topic).

Each element of an array is determined by an array identifier and its ordinal number
— the **index**. The index is an integer, starting from 0, at which the array
element is accessed. Therefore, an array belongs to random access data structures.
An array can have several indexes. In this case, the array is called **multidimensional**,
and the number of indices of one element of the array is its dimension.

The following C code expands on our original example and shows two ways to write
values to an array (immediately upon initialization and when entering values from
a keyboard). In this case, instead of referring to each element of the array by
a unique name, we refer to an element of the array by the common name of the array
and highlight the required element by its ordinal number, enclosed in square brackets.
We also calculate the total number of movies for all of the listed superheroes.

```C
#include <stdio.h>

int main() {
   int superhero_movies [10] = {12,9,10};
   superhero_movies[3] = 11;
   int totalMovies = 0, i;
   for (i = 4; i < 10; i++) {
       printf("Enter the number of movies with superhero №%d: ", i + 1);
       scanf("%d", &superhero_movies[i]);
   }
   for (i = 0; i<10; i++) {
       totalMovies += superhero_movies[i];
   }
   printf("\nThe total number of movies with superheroes is %d.\n", totalMovies);
}
```

The output:

Enter the number of movies with superhero №5: 8
Enter the number of movies with superhero №6: 7
Enter the number of movies with superhero №7: 6
Enter the number of movies with superhero №8: 2
Enter the number of movies with superhero №9: 13
Enter the number of movies with superhero №10: 14

The total number of movies with superheroes is 92.

In the C language, in order to improve the performance of a program, there is no
mechanism for controlling the overflow of array indices. If necessary, such a
mechanism must be explicitly programmed.

Since we use loops to go through an array, it is convenient to divide a program
into separate functions, for example, `inputArray()`, `outputArray()`, `findElement()`
in an array, and so on. When performing some action on an array, the array can be
used as an argument to a function as shown in the example of the following function
prototype:

`void display(int array[size])`

or

`void display(int array [])`

It is not important for a function to know how many elements there are in an array,
but it needs to know how large the elements are since in that case, it can figure
out where each element is (multiplying the number of bytes per element by the index
of the desired element).

When calling a function, only the name of an array is used as an argument:

`display(superhero_movies);`

The array name is the address of the array in memory. Using addresses for array
arguments is similar to using reference arguments, in which the values of the array
elements are not duplicated (copied) in a function. Instead, the function works
on the original array, although it references it using a different name. This system
is used for arrays because they can be very large; duplicating an array for each
function that calls it can take a lot of time and space in memory.

#### Arrays in Python

Python does not have a concept of Arrays. However, Python provides another data
structure called a list, which is an ordered collection of items that enables an
easy use of a set of data that provides similar functionality as arrays in any other
language. Also, to work with arrays in Python, you can use special libraries, like
the *NumPy* library for a high-performance array implementation that aims to provide
an array object that is up to 50x faster than traditional Python lists. The lists
are covered in the topic "7.3 Lists. Stack. Queue. Binary tree".

## Structures, Union, Enum in C

### Structures

In programming, it is sometimes convenient to use one name to designate a group
of variables; as a rule, all these variables are somewhat related. For this, it
is advisable to use structures that provide the ability to store a large number
of different values united by one common name.

**Structures** are usually used when there is a lot of data in a program and they
need to be grouped together - for example, such data can be used to store records
o friends. Let us imagine this in the form of a structure, that is, all the necessary
information about each of our friends should be stored in the structure - name,
address, phone number, date of birth, and so on. To define a structure, the `struct`
keyword is used and the syntax for declaring is as follows:

```C
struct structureName
   {
       type varName1;
     …
       type varNameN;

   } structureVariable, …;
```

structureName - represents an arbitrary identifier to which the same rules for
naming variables are applied; it is optional and can be omitted.

type varNameN - The description of the structure fields is done in the usual way:
the types of variables and their identifiers are indicated. If several fields are
of the same type, then they can be listed separated by commas.

structureVariable - We can combine the definition of the type of a structure and
its variables: structure_variable is a variable of the custom data type structureName.
You can declare multiple structure variables by separating them with commas (‘,’).
Or you can omit it and then the variable will not be created, and only the structure
will be defined.

A structural type is usually declared in the global scope, i.e. before the first
function is performed. Then it can be used in all functions included in a project.
Unlike a function, when defining a structure, there is a semicolon after the closing
curly brace.

For example, let us define our structure for friends:

```C
struct myFriends
{
    char name[20], phoneNumber[15], birthDate[20];
    int age;
};
```

It defines the structure named myFriends which has four elements: age (represents
an int) and name, phoneNumber, and birthDate (represents an array of type char).
All structure members are declared as ordinary variables. But unlike variables,
when defining structure members, no memory is allocated for them, and they cannot
be initialized. Basically, we are just defining a new data type.

The placement of this myFriends object in the operating memory will be schematically
presented as follows:

To start using the structure, we can define a structure object that is a variable
that will represent the data type we have created. Each time a variable of the
structure type is defined, it will be allocated the memory necessary to store its
elements. When defining a structure variable, you can immediately initialize it by
assigning values similar to initialization of arrays: values for structure elements
are passed in curly braces one by one. Define a variable maggy that will represent
the structure myFriends and initialize it:

`struct myFriends maggy = {"Maggy", "+123456789", "December 15", 25};`

If we define a set of structure variables when we define the structure, we can omit
the structure name. In this case, a compiler will still know that the variables
maggy, nick, and alice represent structures with four elements. And accordingly,
we can also work with these variables. Another thing is that we cannot set new
variables of this structure elsewhere in the program.

```C
struct
{
    char name[20], phoneNumber[15], birthDate[20];
    int age;
} maggy, nick, *alice;
```

After creating a structure variable, you can refer to its elements, i.e., get their
values or, conversely, assign them new values; they can be passed to functions as
arguments, and functions can return them as results. All the same operations can
be performed with structure elements as with variables of the same types. The structure
fields are addressed by creating compound names which are formed in two ways:

- Using the member operation (.) from the value (name of the structure variable)
  to the field: maggy.name or (*alice).name
- Using a structure pointer operator (->): (&maggy)->name or alice->name

Structures can be nested, that is, the structure field can be the structure described
earlier (the description must precede with respect to the main structure). For example,
in the structure myFriends, we represent the birthDate with the internal date
structure. Then the template of such a construction will look as follows:

```C
struct date {
  int month, day, year;
};

struct myFriends {
  char name[20], phoneNumber[15];
  struct date birthDate;
  int age;
} maggy;
```

Then you can refer to the fields of the nested structure as maggy.birthDate.month,
maggy.birthDate .day., and maggy.birthDate.year.

We can also declare arrays of structures as `struct myFriends friendsList[50].`

```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct date
{
  int month, day;
};

struct myFriends
{
  char name[20], phoneNumber[15];
  struct date birthDate;
  int age;
};

void outputList(struct myFriends);

int main(void)
{
    struct myFriends friendList[3];
    strcpy(friendList[0].name,"Maggy");
    strcpy(friendList[0].phoneNumber,"+123456789");
    friendList[0].birthDate.month = 12;
    friendList[0].birthDate.day = 15;
    friendList[0].age = 25;

    for (int i = 1; i < 3; i++) {
        printf("Name: ");
        scanf("%s", friendList[i].name);
        printf("Phone number: ");
        scanf("%s", friendList[i].phoneNumber);
        printf("Birth date: month ");
        scanf("%d", &friendList[i].birthDate.month);
        printf(" and date ");
        scanf("%d", &friendList[i].birthDate.day);
        printf("Age: ");
        scanf("%d", &friendList[i].age);
    }

    for (int i = 0; i < 3; i++){
       outputList(friendList[i]);
    }
    return 0;
}

void outputList(struct myFriends list)
{
    printf("\n %s – %4s birthday %d-%d, age %d",list.name, list.phoneNumber,
    list.birthDate.month, list.birthDate.day, list.age);
}
```

The result:

Name: Nick
Phone number: +123456789
Birth date: month 06 and date 25
Age: 29
Name: Alice
Phone number: +123456789
Birth date: month 10 and date 18
Age: 27

Maggy – +123456789 birthday 12-15, age 25
Nick – +123456789 birthday 6-25, age 29
Alice – +123456789 birthday 10-18, age 27

Structures comprise different types of data. However, Java and Python do not exactly
operate with the same thing as a structure in C. The struct module in Python is
used to convert native Python data types, such as strings and numbers, into a string
of bytes, and vice versa.

### Union

Another user-defined data type in C is unions, which is entered using the union
keyword.

A **union* is a variable that can contain (at different times) objects of different
types and sizes. A union can be viewed as a structure, all elements of which have
zero offset from the beginning. With this arrangement, different elements occupy
the same area in memory. Thus, unions provide the ability to access the same area
of memory using variables of different types. The purpose of the union program
is to have a variable that stores values of several base types.

The general form of a union declaration is similar to a structured type:

```C
union unionName
{
    type varName1;
     …
    type varNameN;

};
```

Unions are used for the following purposes:

- to initialize an object if only one of many objects is active at a time

- to interpret the representation of one data type as another one

The differences between structures and unions in C are as follows:

- A structure allocates memory for every variable of it separately, while a union
  allocates a single shared storage space for all of its variables which will be
  the size of its biggest data member.
- Manipulations made on one member will **not** affect the other members in structures.
  Considering that in unions, only a single member is allocated at a time, manipulations
  made on one member will **affect** the other members.

Like other data types, a union is a specific object that has been allocated memory
space. Not only single variables but also arrays or structures can be used as union
elements. The size of the memory allocated for a union is determined by the size
of the largest unit in the union.

```C
union word {
    int nom;
    char str [20];
};
```

To refer to a union member, the same constructs are used as when referring to a
structure member:

- To access a union variable, (.) Dot operator is used.
- To get the address of a union variable, a pointer * is used.

Unions in C are rarely used compared to structs because they do not store all variables
at the same time. But the use of unions allows you to create machine-independent
code. Since a compiler keeps track of the actual sizes of the variables that make
up a union, the dependency on a computer is reduced. There is no need to worry about
the size of integers or floats, symbols, or anything else. Therefore, unions are
often used when you need to convert types because you can access the data stored
in a union in very different ways.

```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

union test {
    int a;
    double b;
    char s[5];
};

int main()
{
  union test symb;
  symb.a = 4;
  printf("\n Integer a = %d, Sizeof(symb.a) = %d", symb.a, sizeof(symb.a));
  symb.b = 1.5;
  printf("\n Double b = %lf, Sizeof(symb.b) = %d", symb.b, sizeof(symb.b));
  strcpy(symb.s, "city");
  printf("\n String a = %s, Sizeof(symb.s) = %d", symb.s, sizeof(symb.s));
  printf("\n Sizeof(symb) = %d", sizeof(symb));
  return 0;
}
```

The result:

 Integer a = 4, Sizeof(symb.a) = 4
 Double b = 1.500000, Sizeof(symb.b) = 8
 String a = city, Sizeof(symb.s) = 5
 Sizeof(symb) = 8

### Enum

Another user-defined data type in C is enum which are entered using the enum key
word and the means of creating a data type by specifying a limited set of values.

The definition of an enumerated data type is as follows:

`enum enumName { varName1, …, varNameN};`

An example of describing a type enum is provided below:

```C
enum {
         su = 1, mo, tu, we, th, fr, sa
} week;
```

Each enumerator is automatically assigned an integer value based on its position
in the enumeration list. By default, the first enumerator is assigned an integer
0 (in our example, it’s 1), and each subsequent one is one more than the previous
one.

```C
#include <stdio.h>
#include <stdlib.h>

enum year {
    jan = 1, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec
};

int main()
{
    enum year month;
    int today, end;
    month = may;
    printf("May %dth month\n",month);
    printf("Enter current month:\n");
    scanf("%d", &today);
    month = jan;
    end=dec;
    printf("January – %d month of a year, now month %d and %d month(s) to the end
    of the year", month, today, end-today );
    return 0;
}
```

The result:

May 5th month
Enter current month:
4
January – 1 month of a year, now month 4 and 8 month(s) to the end of the year

## Working with dynamic memory in C

Pointers are most commonly used when dealing with dynamic memory, which is sometimes
also called the heap. Heap is free memory in which you can allocate space during
program execution according to your needs. Access to the allocated areas of dynamic
memory is created only through pointers. The lifetime of dynamic objects lasts from
the point of creation until the end of the program or until the memory is explicitly
freed.

In C, the following library functions for manipulating dynamic memory are used,
and they are located in the alloc.h or malloc.h libraries:

`void *malloc (unsigned n)` — allocates a memory area to allocate a block of size
bytes; returns a pointer to the allocated memory area.

`void *calloc (unsigned n, unsigned size)`; — allocates memory to accommodate
objects with an appropriate size in bytes and filling the resulting area with a
zero; returns a pointer to the allocated memory area.

`void *realloc (void *b, unsigned n)` — resizes the block located at address to
a new value and copies (if necessary) the contents of the block; returns a pointer
to the reallocated memory area; when an error occurs (for example, there is not
enough memory), these functions return NULL which means there is no address (zero
address).

`void free (void *b)` — frees the memory block pointed to by b.

## Lists. Stack. Queue. Binary tree

Until now, the main component of the data was an array (a regular array, an array
of pointers). If you try to build a data structure based only on pointers (the
concept of dynamic memory allocation), you get a chain (a sequence) of elements
containing pointers to each other. In the simplest scenario, it can be linear (a
list), in more complex cases - branching (trees, graphs). The listed structures
contain a set of records of the same kind, limited in size or unlimited, ordered
or unordered. The data stored in these records are usually logically related to
each other, for example, the names of students of the same group, etc. In the program
text, such a relationship can be expressed in the fact that all such elements
are stored in the same array as a contiguous block of memory. Its components, in
turn, at some level of detail are objects with a static structure, that is, they
belong to one of the main data types.

Note that the lists in Java and Python and the lists as data structures are
completely different lists.

### Non-Primitive or User-Defined Data Structure Classification

### Lists in C

Linked **lists** are linearly grouped datasets. A linked list is an essential data
structure that allows dynamic memory allocation with less risk of buffer overflows.
They are made up of nodes that contain data (a variable, an object of a class,
or a structure) and pointers (a pointer to a neighboring node in the list).

Remember the following concepts:

- A pointer * contains the address of the memory area that stores certain data
  (for pointers, a null value is also allowed).
- & must always point to a specific address.
- A data structure is a way of grouping information that can be implemented in
  any programming language.

Linked lists have certain advantages and disadvantages over arrays (their main
alternative in the world of linear data structures).

#### Advantages of Linled Lists

- Since linked lists do not require data to be stored in a single contiguous block
  of memory, you can place and c items in a linked list as you like. Pointers
  contain a reference to any memory location, and you don't need to move a lot
  of data to add a new node.
- The size of a structure is limited only by the available amount of machine memory.

#### Disadvantages of Linked Lists

- Searching a linked list, adding an object in the middle, and removing such an entry
  are much less efficient. We would have to go from the head node all the way to
  the one we need. The more items in the list, the more transitions you have to make.
- Linked lists require a little more memory since they store pointers in addition
  to data.
- Work with pointers requires, as a rule, higher qualifications from a programmer.

#### Classification of Linked Lists

We can implement a linked list with structures in C and its declaration is as follows:

```C
struct node
{
    int data_element;
    struct node *next;
};
```

Let us consider an example of a singly linked list in C. Imagine a children's game
in which a leader thinks of a number and whispers it to the first child. The first
child whispers this number to the second child and so on, until the number is reported
to the last in the chain. Children win if the correct intended number reaches the
last child.

```C
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

struct node
{
    int data_element;
    struct node *next;
};

void displayNode(struct node *n) // Function to display the linked list
{
    while (n != NULL) {
        printf("%d\n", n->data_element);
        n = n->next;
    }
}
int main()
{
    printf("Children's game\n");
    /* Linked list with 4 children*/
    struct node *first = NULL;
    struct node *second = NULL;
    struct node *third = NULL;
    struct node *fourth = NULL;
    first = (struct node*)malloc(sizeof(struct node)); /* Dynamic memory
    allocation */
    second = (struct node*)malloc(sizeof(struct node));
    third = (struct node*)malloc(sizeof(struct node));
    fourth = (struct node*)malloc(sizeof(struct node));
    int number1=0;
    printf("The leader thinks \n");
    scanf("%d", &number1);
    first->data_element = number1; // Assigning data to the first node
    first->next = second; // Linking the first node with the second node
    int number2=number1+5;
    second->data_element = number2; // Assigning data to the second node
    second->next = third; // Linking the second node with the third node
    number2+=4;
    third->data_element = number2; // Assigning data to the third node
    third->next = fourth; // Linking the third node with the fourth node
    number2-=9;
    fourth->data_element = number2; // Assigning data to the fourth node
    fourth->next = NULL; // Since fourth is the last node, it does not point to
    any other data element.
                         // NULL denotes the termination of the linked list
    displayNode(first);
    if (number1==number2)
    printf("Children win! \n");
    else
    printf("The leader wins \n");
    return 0;
}
```

The result:

Children's game
The leader thinks 5874
5874
5879
5883
5874
Children win!

*Adding* an object to a linked list begins by creating a new node. The data is
copied inside the node. Then the insertion point is found. A new node's pointer
to the next object is changed to point to the next node after it. Finally, the
node before the new node changes its pointer to point to the new node.

When *deleting* an object from a linked list, the node in front of the deleted
node changes in order to point to the next node after the deleted object. The
deleted object can then be safely erased.

In class-based programming, lists are typically provided as instances of subclasses
of the generic list class and are passed through separate iterators.

Many programming languages provide support for list data types and have special
syntax and semantics for lists and list operations. A list can often be created
by writing the items sequentially, separated by commas, semicolons and/or spaces,
within a pair of delimiters such as parentheses '()', square brackets '[]', curly
braces '{}', or angle brackets '<>'. Some languages may allow list types to be indexed
or sliced like array types; in that case, the data type is more accurately described
as an array.

### Stack

This represents the idea of a stack. A stack is an ordered set of elements in which
the placement of new ones and the removal of existing ones occur at one end, called
a top. A stack implements the LIFO semantics which stands for Last In First Out.
When adding and removing from a stack, the last added item will be the first one
to be removed. Stacks have a wide range of uses in algorithms. For example, they
are used in language parsing as well as runtime memory management which relies on
a call stack.

There are several ways to implement a stack:

- using a one-dimensional array
- using a linked list
- using an object-oriented programming class

A stack needs only three operations:

- push() that adds an element to a stack
- pop() that removes an element from a stack
- top() that gives the most recent element on a stack without removing it
  (peek() in Java).

These containers are a part of the standard libraries in most languages. Internally
a stack is often implemented as a dynamic array. As you recall from this data
structure, the fastest operations on dynamic arrays are adding and removing elements
from the end. Since a stack always adds and removes from the end, usually push and
pop of objects on a stack are incredibly fast.

Let us take a look at several stack implementations.

```C
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>
#define nMax 100 //we use the concept of a symbolic constant

struct stack {
  int elem[nMax];
  int top;
};

void init(struct stack *stk) {
  stk->top = 0;
}

void push(struct stack *stk, int val) {
  if(stk->top < nMax) {
    stk->elem[stk->top] = val;
    stk->top++;
  } else
      printf("The stack is full, the number of elements is: %d !\n", stk->top);
}

int pop(struct stack *stk) {
  int elem;
  if((stk->top) > 0){
    stk->top--;
    elem = stk->elem[stk->top];
    return elem;
  } else {
      printf("The stack is empty.\n");
    return 0;
  }
}

int getCount(struct stack *stk) {
  return stk->top;
}

int isempty(struct stack *stk) {
  if(stk->top == 0)
    return 1;
  else return 0;
}

void displayStk(struct stack *stk) {
  int i;
  i=stk->top; // i - number of elements in stack
  if(isempty(stk) == 1) return;
  do {
    i--;
    printf("%d\n", stk->elem[i]);
  }while(i>0);
}

int main() {
  struct stack *stk;
  int i,n;
  int elem;
  stk = (struct stack*)malloc(sizeof(struct stack));
  init(stk);
  printf("Enter the number of items in the stack: ");
  scanf("%d", &n);
  for(i=0; i<n; i++) {
    printf("Enter an element %d: ", i);
    scanf("%d", &elem);
    push(stk,elem);
  }
  printf("Size of the stack is % d\n", getCount(stk));
  displayStk(stk);
  do {
    printf("Pop an element %d, ", pop(stk));
    printf("%d items left on the stack\n", getCount(stk));
  } while(isempty(stk) == 0);
  getchar(); getchar();//we use this function to wait for a keypress
  return 0;
}
```

The result:

Enter the number of items in the stack: 3
Enter an element 0: 2
Enter an element 1: 3
Enter an element 2: 4
Size of the stack is 3
4
3
2
Pop an element 4, 2 items left on the stack
Pop an element 3, 1 items left on the stack
Pop an element 2, 0 items left on the stack

### Queue

A **queue** in programming is implemented as in real life when you need to perform
some actions in the order they are received, performing them sequentially. It doesn't
matter where you stand in a queue, usually first come, first served. Then, the next
person in the queue is served and also leaves. Other people join the queue and stand
at the end of it. When working on a computer, the simplest example of a queue is
the line for printing documents. You send documents to print, and a printer prints
them in the order of the received requests: from the first one to the last one.

A queue implements FIFO (First In First Out) semantics.

There are several ways to implement a queue:

- using a one-dimensional array
- using a linked list
- using an object-oriented programming class

A queue needs a few operations:

- `push_Back ()` that adds an item to the end of a queue
- `pop_Front()` that removes an item from the front of a queue

There are several types of queues:

- Double Ended Queue or Deque
  It is used when you need to add or remove items from both ends of a queue.
  In this case, a couple more operations are added: Push_Front() and Pop_Back().
  Since elements can come in and out from either end, the queue must be able to
  grow and become shorter from the beginning and from the end.

- Priority Queue
  It looks like a regular queue but you can prioritize certain items in the queue.
  In life, for example, a group of people that can jump the queue is designated.
  Thus, the most important items are processed in FIFO order first, and then items
  with lower priority are processed by FIFO. And the process repeats until the
  elements with the lowest priority are processed in FIFO order. When a new item
  is added with a higher priority than the rest of the queue, it is immediately
  moved to the front of the queue.

```C
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <malloc.h>
#define QMAX 100

struct queue {
    int qItem[QMAX];
    int last, first;
};

void init(struct queue *q) {//initialization of the queue
    q->first = 1;
    q->last = 0;
}

void pushBack(struct queue *q, int x) {//placing element x at the end of the
   queue q
    if(q->last < QMAX-1)
    {
        q->last++;
        q->qItem[q->last]=x;
    }else
        printf("The queue is full!\n");
}

int isempty(struct queue *q) {//returns 1 if the queue is empty and 0 otherwise
    if(q->last < q->first)
        return 1;
    else
        return 0;
}

void print(struct queue *q) {
    int count;
    if(isempty(q)==1) {
        printf("The queue is empty!\n");
    }
    for(count = q->first; count<= q->last; count++)
        printf("%d ",q->qItem[count]);
}

int popFront(struct queue *q) {//remove element x from queue q;
    int x;
    if(isempty(q)==1) {
        printf("The queue is empty!\n");
        return(0);
    }
    x = q->qItem[q->first];
    q->first++;
    return x;
}

int popFrontAll(struct queue *q) {
  int x, count;
  if(isempty(q)==1) {
    printf("The queue is empty!\n");
    return 0;
  }
  x = q->qItem[q->first];
  for(count = q->first; count < q->last; count++) {
    q->qItem[count] = q->qItem[count+1];
  }
  q->last--;
  return x;
}

int main() {
  struct queue *q=(struct queue*)malloc(sizeof(struct queue));
  int a;
  init(q);
  print(q);
  for(int i=0;i<8;i++) {
    printf("Enter an element: ");
    scanf("%d", &a);
    pushBack(q, a);
  }
  printf("\n");
  print(q);
  while(q->first <= q->last) {
    a = popFront(q);
    printf("\nThe element %d was removed.\n", a);
    print(q);
  }
  getchar();
  return 0;
}
```

The result:

The queue is empty!
Enter an element: 5
Enter an element: 9
Enter an element: 7
Enter an element: 52
Enter an element: 3
Enter an element: 1
Enter an element: 56
Enter an element: 6

5 9 7 52 3 1 56 6
The element 5 was removed.
9 7 52 3 1 56 6
The element 9 was removed.
7 52 3 1 56 6
The element 7 was removed.
52 3 1 56 6
The element 52 was removed.
3 1 56 6
The element 3 was removed.
1 56 6
The element 1 was removed.
56 6
The element 56 was removed.
6
The element 6 was removed.
The queue is empty!

### Binary Tree

A **tree** is a data structure, that is, a tree-like structure in the form of a
set of related nodes. It works in a similar way as graphs in mathematics.

A real tree has a root, branches, and the ends of the branches have leaves. The
tree data structure is similar to the structure of a regular tree and starts at
the root node. Each node can branch out into child nodes. If a node has no children,
then it is called a leaf node. Unlike real trees, they grow from top to bottom:
the root node is usually drawn at the top and the leaves – at the bottom.

There are three ways to traverse the tree:

Traversing the tree from top to bottom (in the direct order): A, B, C - **prefix**
form.

```C
struct tnode {
  int field; // data field
  struct tnode * left; // left child
  struct tnode * right; // right child
};
void showTree (tnode * tree) { tree traversal in prefix form
  if (tree! = NULL) {// Until An Empty Node Is Found
    printf(tree-> field); // Display the root of the tree
    showTree (tree-> left); // Recursive function for the left subtree
    showTree (tree-> right); // Recursive function for the right subtree
  }
}
```

Traversing the tree in the symmetric order (from left to right): B, A, C - infix
form.
Traversing the tree in the reverse order (bottom to top): B, C, A - postfix form.

A binary tree works according to the rule that child nodes which are smaller than
a root node keep on the left side, and child nodes which are greater than a root
node keep on the right side. The same rule is applied for child nodes that are
sub-trees themselves. Let us consider an example:

```C
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <malloc.h>

struct tnode {
    int item;
    int count;
    struct tnode *left;
    struct tnode *right;
};

struct tnode *addTree (struct tnode *p, int val)// Function for adding a node to
the tree
{
    if (p == NULL) {
        p = (struct tnode *) malloc (sizeof (struct tnode));
        p->item =val;
        p-> count = 1;
        p-> left = p-> right = NULL;
        }else if (val < p->item){
            p-> left = addTree (p-> left, val);
        }else{
            p-> right = addTree (p-> right, val);
            p->count++;
        }
    return p;
}
// Function for deleting a subtree
void freemem (struct tnode * tree) {
  if (tree!= NULL) {
      freemem (tree-> left);
      freemem (tree-> right);
      free (tree);
    }
}

void displayTreeInf (struct tnode *p) {// Function to display the tree in infix form
  if (p!= NULL) {
    displayTreeInf(p-> left);
    printf ("%d - %d \n", p-> count, p-> item);
    displayTreeInf(p-> right);
  }
}
int main () {
  struct tnode *root;
  int val=0;
  root = NULL;

    root = addTree (root, 8);
    root = addTree (root, 6);
    root = addTree (root, 2);
    root = addTree (root, 1);
    root = addTree (root, 3);
    root = addTree (root, 7);
    root = addTree (root, 11);
    displayTreeInf(root);
    freemem (root);
    getchar ();
    return 0;
}
```

The result:

1 - 1
2 - 2
1 - 3
2 - 6
1 - 7
2 - 8
1 - 11

While tree theory is convenient, it has some disadvantages as well:

- Storage space
  The simplest way to represent a tree is to build a linked list, but it turns
  out to be the worst way because each time an object is placed, it takes up a
  small part of additional resources for pointers.

- Speed of Crawling
  When a program needs one piece of data, the cache loads that item as well as the
  items next to it. When no data has been loaded into very fast memory (this is
  called a "cache miss"), the program pauses and waits for the data to be loaded.

There are balanced and unbalanced trees. There are red-black trees, AVL trees, and
many other types. Trees are used in many algorithms. In the "Sorting Methods" submodule,
consider an example of sorting array elements using a tree. In practice, most standard
libraries do not directly implement tree-based containers. While trees are very
useful and fundamental, there are better containers. There are more complex data
structures that have the advantages of a tree (stability and shape). More advanced
data structures are usually a combination of data tables and lookup tables.

Calculate the number of grades A, B, C, D, and F for the test in a class of 15 people.

```C
#include <stdio.h>

int main()
{
    char array[15];
    int amount_A=0;
    int amount_B=0;
    int amount_C=0;
    int amount_D=0;
    int amount_F=0;
    printf("Enter the grades for the test:\n");
    for(int i = 0; i < 15; i++)
    {
        printf("Enter the grade of student %d\n",i+1);
        scanf( "%c", &array[i]);
        getchar();
        if(array[i]=='a'||array[i]=='A')
            amount_A++;
        if(array[i]=='b'||array[i]=='B')
            amount_B++;
        if(array[i]=='c'||array[i]=='C')
            amount_C++;
        if(array[i]=='d'||array[i]=='D')
            amount_D++;
        if(array[i]=='f'||array[i]=='F')
            amount_F++;
    }
    printf("Number of A grades = %d\nNumber of B grades = %d\nNumber of C grades
    = %d\nNumber of D grades = %d\nNumber of F grades = %d\n",amount_A,amount_B,
    amount_C,amount_D,amount_F);
  return 0;
}
```

```Python
grades = input("Enter the grades for the test: ").split()

for grade in sorted(set(grades)):
    print("Number of ratings {} = {}".format(grade, grades.count(grade)))
```

Result:

Enter the grades for the test: A A A A A F F D C A F F C A A
Number of ratings A = 8
Number of ratings C = 2
Number of ratings D = 1
Number of ratings F = 4







