Windows Assembly Language Lab Exercises
======

For starters please install [FASM] (http://www.flatassembler.net/fasmw17121.zip) 

We will be going through a selection of lessons from [Xorpd's Windows assembly course] (https://github.com/xorpd/asm_prog_ex) so please ensure you at a minimum, pull down the training.inc file so the examples will assemble properly.

To get warmed up on syntax and such we will begin by going through the lesson labeled [3_Basic_Fasm] (https://github.com/xorpd/asm_prog_ex/tree/master/3_basic_fasm/4_exercises). Inside you will find three sections read code, write code, and fix code. All three sections are simple and easy and as such should be completed to help you get a feel for fasm and also the helper functions available. *In the write code section question 2 may be skipped*

Most of the following lessons will be from the write code section of the exercises but please do not be afraid to look at the read code sections to get an idea of how to properly structure your assembly. Just because we are only specifically going through a small subset does not mean you cannot independently go through more. 

**PRO-TIP** : This is an excellent oppurtunity to become familar with WinDBG and the plethora of options available within it. When your code does not work debug it and use the resources available to get WinDBG set up just how you like it. You can use IDA on the binaries FASM creates to see offsets and such. [WinDBG cheat sheet] (https://github.com/xorpd/asm_prog_ex/blob/master/5_becoming_independent/1_debugging/4_windbg_cheatsheet/windbg_cheatsheet.txt) Note: FASM modules do not opt into ASLR so the value you see in IDA will be the value you will use in WinDBG. 

The first 3 exercises can be written however you want. Meaning no calling convention neccessary and variables can be passed via register. Starting at lesson 4 all programs need to follow the CDECL calling convention meaning variables are passed on the stack and the caller cleans up the stack. This also means you can destroy eax, ecx, edx but must take care to restore the others.

All written code should be put into a folder for turning in. Anything not finished should be done at home and turned in next week

Lessons:
-------
  1. [4_Basic_Assembly/Basic_Conditionals] (https://github.com/xorpd/asm_prog_ex/blob/master/4_basic_assembly/0_branching/2_basic_conditional_branching/ex/2_write_code/write_code.txt)
      * Writing modular programs is not simply for high level languages
      * Ex. For part 0 writing a function that calculates if a # is even or odd can make things simple and easier to read rather then
        doing the calculation inside of the loop.
      * Part 2 of write code *Fibonacci Sequence* may be skipped
  2. [4_Basic_Assembly/Signed_Operations] (https://github.com/xorpd/asm_prog_ex/blob/master/4_basic_assembly/1_signed_operations/ex/2_write_code/write_code.txt)
      * Only section 0 adding 4 bytes of a number together
  3. [4_Basic_Assembly/Signed_Memory] (https://github.com/xorpd/asm_prog_ex/blob/master/4_basic_assembly/3_memory/5_ex/2_write_code/write_code.txt)
      * Section 0
  4. [4_Basic_Assembly/SubRoutines_and_the_Stack] (https://github.com/xorpd/asm_prog_ex/blob/master/4_basic_assembly/5_subroutines_and_the_stack/2_call_ret/ex/3_write_code/write_code.txt) 
      * Sections 0 and 2
  5. [5_Becoming_Independent] (https://github.com/xorpd/asm_prog_ex/tree/master/5_becoming_independent/1_debugging/6_ex/1_debug_code)
      * Debug and fix any two programs from this section. Please annotate the program and yes some of them work out of the box but they all have bugs.
  6. Implement these C standard library functions
      * strlen, strchr, memcpy, memset, strcmp, strset

## WinDBG

User interface

http://sandsprite.com/blogs/index.php?uid=7&pid=51

Commands

http://briolidz.wordpress.com/2013/11/17/windbg-some-debugging-commands/

Memory Scanning Techniques

http://blogs.msdn.com/b/dsnotes/archive/2012/02/21/windbg-search-for-a-string.aspx


Viewing Page Permissions

http://msdn.microsoft.com/en-us/library/windows/hardware/ff561519%28v=vs.85%29.aspx
