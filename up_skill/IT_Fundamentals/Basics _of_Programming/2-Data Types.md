# Data Types

## Symbols and Words

As you know, the program consists of a sequence of instructions coded in strict
accordance with the rules that make up the syntax of the language.

The following basic errors can be made when creating programs:

- Algorithm - are the result of a discrepancy between the constructed algorithm
  and the course of obtaining the result of the task

- Semantic - when there is a misinterpretation of the meaning (semantics) of the
  operators of the selected programming language

- Logical - are divided into algorithm errors and semantic errors

- Syntax - due to a violation of the rules of program writing

The alphabet of any language is a set of **symbols** – those indivisible signs
necessary for writing all texts in the given language:

- Each of the set of values defined by one byte (from 0 to 255) is assigned a symbol
  on the computer character generator table.
- According to the IBM encoding,
  - characters with codes from 0 to 127, which form the first half of the character
    generator table, are built according to the ASCII standard and are the same for
    all computers;
  - the second half of the characters (codes 128 – 255) may differ and they are usually
    used to locate the characters of the national alphabet;
  - codes 176 – 223 are reserved for pseudo-graphic characters;
  - codes 240 – 255 - for special characters.

The standard alphabet of programming languages we are considering comprises:

- Uppercase and lowercase letters of the Latin alphabet and underscore (code 95)
- Arabic numerals from 0 to 9
- special characters, whose meaning and rules of use will be considered in the text
- whitespace (separator) characters: space, tab, line feed, carriage return, new
  page and new line

**Tokens** (or elementary constructions) of the language are formed from the symbols
of the alphabet (the minimum significant units of the text in the program) and are
the so-called building blocks or the basic components.

The following basic errors can be made when creating programs:

- Key (reserved) world

- Identifiers
  In a simple language, identifiers are user-defined words to name variables, classes,
  functions, arrays, structures, labels, etc. The punctuation like ! @ $ % & * and
  keywords cannot be used as variable names (or identifiers) as they are part of
  the programming language syntax.

- Operators
  An operator is a special symbol that is used to perform a mathematical or logical
  operation. There are three types of operators: unary, binary, and ternary.

- Constants
  A constant is a value which does not change during program execution.

- Strings
  A string is always an array of several characters (size of a string) having null
  character '\0' at the end of the string. This null character denotes the end of
  the string. Strings are often enclosed in double quotes, while characters are
  enclosed in single quotes.

- Delimiters
  - brackets (, ), {, }, [, ],<, >
  - a period
  - a comma
  - a semicolon
  - an asterisk - used to create a pointer variable in C/C++
  - **whitespace** - some characters which are frequently used but they are invisible
    in your program and these characters are spaces, tabs (\t), new lines(\n))

For example, a newline character (\n) sets the active position to the beginning
of the next line, a carriage return (\r) moves the active position to the beginning
of the current line.

It should be noted that these escape sequence characters do not necessarily work
with all display devices (whitespace). For example, the form feed (\f) and vertical
tab (\v) characters produce odd symbols on a PC screen instead of any cursor movement,
but they work as described if sent to a printer instead of to the screen.

A **lexeme** is a sequence of characters in the source program that matches the pattern
for a token and is identified by the lexical analyzer as an instance of that token.
Some authors term this a "token", using "token" interchangeably to represent
the string being tokenized, and the token data structure resulting from putting
this string through the tokenization process.

Another basic element of a programming language – a **comment** – is not a token.
Any characters allowed on the given computer can be used inside a comment, since
the compiler ignores them, and these comments are used to make the programs
user-friendly and easy-to-understand.

In any language, comments are limited to the pairs of characters /* and */, and
in C ++/Java/Js, a variant of the comment was introduced that begins with the characters
// and ends with a newline character. In Python, the # character is used to start
a comment and it continues until the end of the line.


