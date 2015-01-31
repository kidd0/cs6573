# Assembly Exercises

### Overview
The purpose of this assignment is to brush up on your assembly language skills. Most of this assignment has been adapted from [xorpd](https://github.com/xorpd)'s excellent [asm_prog_ex](https://github.com/xorpd/asm_prog_ex) repository.

This is an excellent opportunity to become familar with WinDBG and the plethora of options available within it. When your code does not work debug it and use the resources available to get WinDBG set up just how you like it. You can use IDA on the binaries FASM creates to see offsets and other information. Note: FASM modules do not opt into ASLR so the value you see in IDA will be the value you will use in WinDBG. 

The first 4 exercises can be written however you want, meaning that no calling conventions are neccessary and variables can be passed via register. Starting at lesson 4 all programs need to follow the CDECL calling convention meaning variables are passed on the stack and the caller cleans up the stack. This also means you can destroy eax, ecx, edx but must take care to restore the others.

### Prerequisites
* Windows
* [FASM](http://www.flatassembler.net/fasmw17121.zip) 

### Lessons
Only the `write` and `debug` code folders are required. None of the `read` code sections are required. Work through folders 1-6 and complete the assignments.

* 1_basic_fasm: some background to get familiar with FASM
* 2_branching: you can skip question 2 (the one about Fibonacci)
* 3_signed_operations: only do question 0
* 4_signed_memory: only do question 0
* 5_call_ret: only do questions 0 and 2
* 6_becoming_independent: debug and fix any two programs from this section
* 7_stdlib: implement these standard library functions: strlen, strchr, memcpy, memset, strcmp, strset

### WinDBG
* [User interface](http://sandsprite.com/blogs/index.php?uid=7&pid=51)
* [Commands](http://briolidz.wordpress.com/2013/11/17/windbg-some-debugging-commands/)
* [Memory Scanning Techniques](http://blogs.msdn.com/b/dsnotes/archive/2012/02/21/windbg-search-for-a-string.aspx)
* [Viewing Page Permissions](http://msdn.microsoft.com/en-us/library/windows/hardware/ff561519%28v=vs.85%29.aspx)
