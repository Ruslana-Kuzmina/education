# Data Representation and Architecture

## Content
- Number Bases, a Bit, a Byte
- Negative Numbers
- Boolean Algebra
- Logic Gates and Circuits
- Fetch-Execute Cycle
- Text, Encodings, Unicode
- Colors and Images

### Number Bases, a Bit, a Byte

Our everyday numeral system of use is the decimal system. Its base is 10. It uses 10 symbols to represent numbers: 0, 1, 2, …, 9. We will study numeral systems with bases different from 10. The most important two are the binary system (base 2) and the hexadecimal system (base 16). The reason for this is that a computer does not store numbers in the decimal system. It uses the binary system to represent all data. At the very low level all data stored and processed by computers consists of zeros and ones.

#### Decimal System
Let us revise what the decimal system is. We use 10 digits to represent numbers. Each of the digits has a value. If we write them in order, we finally reach 9 and we do not have a separate symbol to represent the next number. What we do is we write a "1" followed by a "0", indicating that we have one ten. We continue in the same way with 11, 12, and so on. When we reach 19 (one ten and nine), for the next number we use a "2" in place of "1" and replace a "9" with a "0" again. So, we get 20 (two tens).

#### Binary System
In the binary system, we use only two symbols: 0 and 1. We start counting with 0 followed by 1, and we immediately run out of symbols. Like in the decimal system, we write a "1" followed by a "0" for the next number, only now we indicate that we have one of twos because our base is 2. The next number is 11, meaning that we have one of twos and one. The next is 100, meaning that we have one of four. Why four? Like in the decimal system, every position further to the left is base times bigger. So, the 3rd position value is two by two.

#### Hexadecimal System
Another important numeral system is hexadecimal (or hex in short). Its base is 16. So, it must have 16 symbols. The first 10 are the same as in the decimal system: 0, 1, … 9. The next 6 symbols are the first 6 letters of the English alphabet: A – 10, B – 11, C – 12, D – 13, E – 14, F – 15.

In order to convert from the decimal system to the system with the base **B**, divide the number by the **B** . The remainder is the rightmost digit in the base **B**. Next, divide the quotient by **B**. The remainder is the second rightmost digit in the base **B** . Continue dividing until the quotient is zero.

The binary system is used by almost all modern computers because elementary cells to store data on a computer have only two states. Let us see how many cells we need to represent the data.If we have only one cell, there are only two possible states, we represent them as 0 or 1. Such an elementary cell is called a **bit**. If we have two cells, we can store 4 states or a number from 0 to 3. In case of three cells, we can store 8 states or a number from 0 to 7. Each additional cell multiplies the number of possible states by 2.

In case of 8 cells, the number of states is 2*8 = 256. The group of 8 cells has a special name, a **byte**.
To write the number stored in a byte, we can use the binary system and write 8 digits. However, it is more convenient to use the hexadecimal system. Note that 4 bits have exactly 16 states, the same number as the base of the hexadecimal system. So, we can write one byte using two hex digits.Most of the programming languages have a convention to use prefix **0x** to indicate numbers written in the hexadecimal system. Numbers without any prefix are in the decimal system.

### Negative Numbers

#### The Sign Bit

#### The Two's Complement
- Positive numbers
You need to add 0, using 8 bits, the leftmost bit is reserved for the sign and the other 7 bits represent the positive binary number.
- Negative numbers
**Convert a negative decimal number to two's complement**
  - Convert the number to binary as if it were positive.
  - Invert all bits. That is, write 1's instead of 0’s and write 0's instead of 1's.
  - Add 1 to the result.
  Let us convert −87 to two's complement. We discard the sign and write 87 = 0101 0111. Next, we invert all bits and get 1010 1000. Finally, add 1 to 1010 1000 to get 1010 1001. So, the two's complement of −87 is 1010 1001.
- **Convert Two's Compliment to Decimal**
  - Subtract 1 from the number as if it were a usual binary number.
  - Invert all bits.
  - Convert the binary number to decimal.
  - Write a minus sign in front of the number.
  Let us convert 1010 1001 back to decimal. First, we subtract 1 from 1010 1001 to get 1010 1000. Next, invert all bits, 0101 0111. Convert 0101 0111 to decimal, 0101 01112 = 87. Finally, we add a minus sign in front of the number, −87.

## Boolean Algebra

Boolean algebra is a branch of mathematics that deals with variables having only two possible values, 1 and 0, or "true" and "false". The main difference between Boolean algebra and elementary algebra is that Boolean algebra deals with logical operations, whereas elementary algebra deals with arithmetic operations. Why is it important to us? First, as we will learn later, modern computers and their one of the most important parts, CPU, are built of billions very simple circuits called **logic gates**. These logic gates are physical implementations of Boolean functions. Second, all programs contain many conditional statements, which allow the program to perform different actions depending on whether a condition is seen as true or false. These conditional statements are also Boolean functions.

Key Facts About Boolean Algebra:
- Variables can have only two values. The values are truth values, "true" and "false". It is often denoted as 1 and 0, respectively.
- There are three basic operations in Boolean Algebra:
  - A AND B. This operation results in true value only if both A and B are true.
  - A OR B. This operation results in true value only if at least one of A or B is true.
  - NOT A. This operation negates the value of A. If A is true, then NOT A is false, and if A is false, then NOT A is true.

  The operations can be expressed using the so-called **truth tables**. A truth table lists all possible combinations of values of variables and the result of operations. The truth tables for the basic operations in Boolean Algebra are provided below.
  AND = *
  OR = +

### Double Negation Law
NOT (NOT A) = A

### De Morgan's Laws
NOT (A or B) = (NOT A) and (NOT B)
NOT (A and B) = (NOT A) or (NOT B)

## Logic Gates and Circuits

We have learned so far that all information is stored as binary. To process this data, we need circuits which work with two levels of signals: high (corresponding to 1) and low (corresponding to 0). These circuits implement Boolean functions or operators, and they are called **logic gates**

The XOR operation gives 1 when exactly one of the inputs is 1. The XNOR may be expressed as NOT (A XOR B). If we look closely at XOR truth table, it represents binary addition of 1-bit numbers. Note that we discard the carry in case of 1 + 1. XOR gates can be used to implement addition on a computer.

| A | B | AND | OR | XOR | XNOR |
|---|---|-----|----|-----|------|
| 0 | 0 | 0   | 0  | 0   | 0    |
| 0 | 1 | 0   | 1  | 1   | 0    |
| 1 | 0 | 0   | 1  | 1   | 0    |
| 1 | 1 | 1   | 1  | 0   | 0    |


### Logic Circuits

Simple logic gates can be combined to build logic circuits. XOR gate implements addition of two bits, but we also need to know if the carry occurs; that is, we need a gate which would give 1 only if both inputs are 1. We already have such a gate; it is AND gate. So, we can combine XOR and AND gates to build a logic circuit called the **half adder**. It has two outputs, one for the sum and the other one to indicate whether a carry has occurred.

## Fetch-Execute Cycle

In this topic we will outline on a basic level what the CPU does. It is obvious that it somehow performs some instructions but let us have a closer look at it.

The CPU has so-called **registers** which are essentially a few bytes of very fast memory. The size of registers depends on computer architecture; modern processors have 64-bit registers. Each CPU has the following registers:
- Program counter. This register contains the address of the current instruction in RAM (Random Access Memory).
= Instruction register. This register contains the instruction currently being executed.
= Data registers. These registers are used to store results of operations.
= There are many other registers in modern complex CPUs but let us keep it simple.

The CPU also has a clock generator that generates pulses with predefined intervals of time. It is used to synchronize different parts of a processor. Each time a clock pulse occurs, millions of small circuits in the processor change their state and process signals. All at the same time.

Fetch-Execute cycle or Fetch-Decode-Execute cycle or Instruction cycle is a three-stage process:
