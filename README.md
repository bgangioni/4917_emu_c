# Readme file for 4917_emu_c
*by Bruno Angioni*
*started on: August 11, 2018*

In 2008 UNSW uploaded a series of recordings from
their Computer Science class CS1, taught by Richard Buckland

A brief part of the course makes use of a microprocessor emulator
to teach Assembly basics. I don't know wether such processor exists
but I intend to create a usable emulator in C, as a personal project.

## Specifications
4 bit microprocessor

16-byte memory for code and values

2 1-byte registers (R0 and R1)

Instructions will be read from the file passed as argument.

It must be a text file with the following format:

XX XX XX XX

XX XX XX XX

XX XX XX XX

XX XX XX XX

...where XX represents 00, 01, 02 .. 13, 14, 15

...which in turn represent either instructions or data.

These space separated values are considered to be the memory, and they are numbered 0 to 15.

## Set of Instructions
8 1-byte instructions

8 2-byte instructions

### 1-byte:
    0 = Halt
    1 = Add (R0 = R0 + R1)
    2 = Substract (R0 = R0 - R1)
    3 = Increment R0
    4 = Increment R1
    5 = Decrement R0
    6 = Decrement R1
    7 = Ring Bell

### 2-byte (second byte is called \<data\>) :
    8 = Print <data> as output
    9 = Load value at address <data> into R1
    11 = Store R0 into address <data>
    12 = Store R1 into address <data>
    13 = Jump to address <data>
    14 = Jump to address <data> if R0 == 0
    15 = Jump to address <data> if R0 != 0
