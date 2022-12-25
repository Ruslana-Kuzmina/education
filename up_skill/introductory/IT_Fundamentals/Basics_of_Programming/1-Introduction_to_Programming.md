# Software Programming

## Computer System

A computer system is a collection of components (both hardware and software) that
function as a part of a whole.

Basic elements of a computer system:

- System interface
  A logical interface that converts a system's input into its output that is displayed
  on the user interface. A system's input can come from somewhere in the form of
  the outputs of that other system, e.g. a power button, pressing buttons on the
  keyboard.
  System interfaces require physical equipment (such as a CPU, cables, graphics,
  and memory cards), software and protocols that describe and implement methods
  for controlling the movement of data and information between systems.

- User interface
  The way how communication (the exchange of sound, voice, graphics, positions,
  typing, movement and receiving data and information) is organized between a user
  and a computer.

- Software architecture
  A set of software elements, relations among them, and properties of both elements
  and relations. It can be represented graphically through the use of flowcharts
  that illustrate how the processes work and how each component is related to another
  one.

- Component
  A group of modules that perform related functions. Components can function independently
  and can be interchanged or placed into new systems.

- Data
  Information used and outputted by the system.

- Modules
  Parts of one system that perform specific tasks. Each module has its own specific
  role which precisely defines its purpose. There are hardware and software modules.

### System and Software Programming

**System programming** is a process of development of programs that allow computer
hardware to interact with a user and execute software applications. System programmers
are focused on designing "low-level" system programs that enable interaction
between hardware and software applications. They work closely with computer resources
and machine languages and are focused on the system's productivity and providing
the best experience by reducing load time or increasing the efficiency of operations.
Interpreters, compilers, operating system, drivers, loaders, assemblers.

**Software Programming** is a process of development of computer code that enables
the computer software to function. Software programmers use the system programs
(and are, therefore, limited by them to some extent) to create a large set of applications
and services. They create programs that interact directly with users and/or other
applications.
Internet banking, fitness trackers, video streaming, food blogs, ticket sales.

#### Computer Program

A **program** is a set of detailed instructions that are passed to a computer when
it is necessary for the computer to perform a task.

Problem - Idea - Algorithm - Program - Execution

## Programming Languages

Similar to natural languages, e.g., English, a programming language also has words,
symbols, and rules of grammar called **syntax**. Different programming languages
have their own syntax rules and are designed for different types of programs.

Each of the different programming languages can be broken into one or more of the
following most common types (paradigms) of languages:

- **Low level** is a programming language that provides little or no abstraction
  from programming concepts and is very close to writing actual machine instructions.
  The main two examples of low-level languages are machine learning and assembly
  language.
  - **Generation Mashine Code**
    Machine language: The exact machine language for a program or an action can differ
    depending on an operating system that dictates how a compiler writes a program
    or an action into machine language.
    - a collection of binary digits or bits that a computer reads and interprets
    - the only language a computer is capable of understanding
    - directly run on a CPU (central processing unit)
    - not portable
  - **Generation Assembly**
    Assembly language (e.g. Apple, Linux, Mips, Intel, etc.):
    - less error-prone
    - there is a one-to-one relationship between what it tells a computer to do,
      and what a computer does. Replaces 1s and 0s with English instructions. Therefore,
      coding is easier than using a machine language
    - often one line of an assembly program contains a maximum of one instruction
      for a computer

- **High level** is a portable computer programming language that isn't limited
  by a computer, designed for a specific job, and is easier to understand. It is
  more like a human language and less like a machine language. The amount of abstractions
  provided defines the level of a programming language. The first high-level languages
  were introduced in the 1950s. These include BASIC, COBOL, FORTRAN, Java, Pascal,
  Perl, PHP, Python, Ruby, and Visual Basic.)
  - **Generation Imperative**
    Imperative programming is a programming paradigm that uses statements that
    change a program's state. Imperative programming focuses on describing how a
    program operates.
    An imperative program consists of commands for the computer to perform.
    - object-oriented languages
    - procedural languages
  - **Generation Data Query Analysis and Reporting**
    Declarative programming is a programming paradigm - a style of building the
    structure and elements of computer programs - that expresses the logic of a
    computation without describing its control flow. In other words, it is a language
    that declares what needs to be done rather than how to do it.
    - logic
    - database query
    - functional

The difference between **procedural** and **object-oriented programs** is discussed
in the table below:

|Procedural:                                       |Object-oriented:                           |
|Programs are written as sequences of instructions |Programs are an interaction of functions   |
|                                                  |between objects                            |
|--------------------------------------------------|-------------------------------------------|
|Top-down approach                                 |Bottom-up approach                         |
|Code is independent                               |Code is modular                            |
|Data is not secure                                |Data can be secur                          |
|It doesn’t have a proper way for hiding data      |Helps in wrapping data and functions in a  |
|                                                  |class                                      |
|Difficult to reuse                                |Can be extended for reuse                  |
|BASIC, C, FORTRAN, and Pascal                     |Java                                       |

### Is C or C++ a Low-level or a High-level Language?

The programming languages C and C ++ are considered **middle-level** languages.
They provide minimal abstraction at the lowest possible performance and efficiency
costs. These abstractions, such as classes, macros, and lambda functions, allow
programmers to use complex functionality without writing overly complex code that
would be required with machine code. For this reason, C and C++ are considered
lower-level languages where abstractions are required to keep code easy for reading
and maintaining, but where maximum performance is paramount.

There are hundreds of programming languages, which can be used to write computer
programs.

C

- a general-purpose, procedural computer programming language
- was originally developed at Bell Labs by Dennis Ritchie between 1972 and 1973
  to construct utilities running on Unix
- supports structured programming, lexical variable scope, and recursion, with a
  static type system
- provides constructs that map efficiently to typical machine instruction
- forms (or is the basis) of Java, C ++, C #, etc.

Java

- a class-based, object-oriented programming language that is designed to have as
  few implementation dependencies as possible
- was originally developed by James Gosling at Sun Microsystems (which has since
  been acquired by Oracle) and released in 1995 as a core component of Sun Microsystems'
  Java platform
- developers can write once, run anywhere (WORA)
- is used for many things, including mobile applications, software development,
  and large systems development
- the latest versions are Java 15, released in September 2020, and Java 11, a currently
  supported long-term support (LTS) version, released on September 25, 2018. Java
  9, 10, 12 and 13 are workable but no longer supported.

Python

- an interpreted, high-level, and general-purpose programming language
- was conceived in the late 1980s, and its implementation was started in December
  1989 by Guido van Rossum at CWI in the Netherlands as a successor to ABC capable
  of exception handling and interfacing with the Amoeba operating system
- is used in a variety of significant spheres from data science and machine learning
  to web development
- Python interpreters are available for many operating systems
- a great first language to learn

C++

- a general-purpose, object-oriented, compiled programming language
- created by Bjarne Stroustrup as an extension of the C programming language,
  or "C with Classes"
- is used in a wide range of industries, including VR, software and game development,
  robotics, and scientific computing; can be commonly used for platform specific
  applications, for complex and difficult to debug web applications
- is standardized by the International Organization for Standardization (ISO).

C#

- a general-purpose, multi-paradigm programming language
- encompasses strong typing, lexically scoped, imperative, declarative, functional,
  generic, object-oriented (class-based), and component-oriented programming disciplines
- is developed by Microsoft within its .Net Framework initiative led by Anders Hejlsberg
- is used to develop a game using the Unity game engine. It also can be used for
  a wide variety of applications, including enterprise software, mobile apps, and
  more
- the most recent version is 9.0, which was released in 2020 in .NET 5.0.

JavaScript

- a high-level, often just-in-time compiled, and multi-paradigm, front-end and
  back-end friendly language
- was developed in September 1995 by a Netscape programmer Brandan Eich in just
  10 days
- was originally named Mocha, but quickly became known as LiveScript and, later,
  JavaScript enables interactive web pages and is an essential part of web applications
- is used for creating web and mobile applications, game development.

PHP

- a widely-used server-side scripting language
- was originally created by a Danish-Canadian programmer Rasmus Lerdorf in 1994
- a better choice for building dynamic web applications and working well with
  databases and HTML.

R

- a statistical programming language
- is widely used among statisticians and data miners for answering questions with
  data analysis, developing statistical software, and creating data visualizations
- the project was conceived in 1992, with an initial version released in 1995 and
  a stable beta version (v1.0) on February 29, 2000.

SWIFT

- a multi-paradigm, compiled programming language
- developed by Apple Inc. and the open-source community, first released in 2014
- a must if you plan to develop applications for iOS and MacOS.

Kotlin

- an open-source, cross-platform, statically typed, general-purpose programming
  language with type inference
- targets the JVM, Android, JavaScript, and Native
- is popular for web development, Android development, and more.

### Factors for Selecting the Programming Language

- Size (memory, ROM)
- Portability (can be compiled for different processors)
- Tool Support (use a tool-oriented language which provides several elements and
  methods to control, work, and edit)
- Time to production (The programs must run as fast as possible. The hardware should
  not be slowed down due to slow running software)
- Ease of implementation
- Readability

## How a Computer Processes a Program: Interpretation, Compilation

**Compiled language** (C, C++, Objective-C, Swift, Fortran) is a type of programming
language which typically executes generating machine code from source code and uses
the machine code to run the program.

Advantages Complied Language:

- Pre-Compiled binaries are inherently more difficult to reverse-engineer and are
  therefore helpful to closed-source software providers who'd like to keep the I.P.
  contained in their source code private.
- Programs compiled into native code at compile time tend to be faster than those
  translated at run time, due to the overhead of the translation process.
- Once a program is translated into its own instructions (machine code), it can
  then be executed over and over again without the overhead of this translation.
  Note that the translated program is much larger than the source program.
- It has an ability to support architectures the interpreter hasn't been compiled
  for (such as embedded systems).
- Stronger optimization is possible due to a larger window of the translated code.
- Compiler can check errors for you at compile time.

Disadvantages Complied Language:

- Additional time is needed to complete the entire compilation step before running.
- There is a platform dependence of the generated binary code.

**Interpreted language** (Python, Javascript, Lisp, PHP, Perl) is a type of programming
language for which most of its implementations execute instructions directly and
freely, without previously compiling a program into machine-language instructions.

Advantages Interpreted Language:

- Programs can be executed immediately without the first compiling.
- Potentially it has a lower memory footprint because no Object Code is created.
- It supports portability if the interpreter is installed on different platforms.
- Source code can be more easily changed between program executions because there
  is no compilation step in-between.

Disadvantages Interpreted Language:

- Typical execution speed is slower compared to compiled languages.

There is also a **hybrid approach** that combines compilation and interpretation.
For example, JDK provides an interpretive compiler for Java while Java is considered
to be a compiled language. Within a hybrid approach, we use a virtual machine (VM)
as an emulation of a computer system. Virtual machines are based on computer architectures
and provide functionality of a physical computer. The hybrid approach combines robustness
with the elimination of drawbacks of the individual techniques - compilation and
interpretation. An interpretive compiler combines fast translation with moderately
fast execution, provided that:

- VM code is lower than the source language but higher than native machine code
- VM instructions have simple formats (can be quickly analyzed by an interpreter)

Source code → Compiler → Bytecode (or p-code) → Interpreter → Execution

## Development Environment

Before starting a detailed acquaintance with the basics of programming, we need
to define a development environment. A development environment is the set of processes
and programming tools used to create a program or a software product. The term may
sometimes also imply the physical environment. An **integrated development environment**
(IDE) is one in which the processes and tools are coordinated to provide developers
with an orderly interface and a convenient view of the development process (or at
least the processes of writing code, testing it, and packaging it for use). Another
widely-used term is a **computer-assisted software environment** (CASE). It is generally
used to describe a set of tools and practices that facilitate the management of
a software development project.

Environment Setup is not a part of any programming language. It just implies the
base that enables us to write a program.

Three ways to start a computer program:

- A text editor
- A compiler
- An interpreter




