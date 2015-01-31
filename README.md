# CS6573

## Prerequisites
Students are expected to be familiar with the basic exploitation techniques for stack and heap overflows. They should be comfortable using assembly-level debuggers and have basic familiarity with reverse engineering.

All hands-on exercises in the course will be performed in provided virtual machines. You will need a laptop with VMware Workstation 6 or later or VMware Fusion 2 or later if using a Mac. The minimum hardware requirements for the laptop are 2GB of memory and a processor equivalent to a 2.4GHz Core2 Duo.

## Course Description
Many security professionals have mastered stack overflows and heap spraying, but these techniques are rarely sufficient when developing modern real-world exploits. Reliable exploitation on Vista and Windows 7 systems requires advanced techniques such as heap layout manipulation, return-oriented programming and ASLR information leaks. In addition, robust exploitation necessitates repairing the heap and continuing execution without crashing the process. This course focuses on teaching the principles behind these advanced techniques and will give the students hands-on experience developing and using real-world exploits.

## Course Objectives
* Review of GS, ASLR, DEP, SafeSEH, and SEHOP exploit mitigations
* Heap implementation details and manipulation of heap state on Windows
* Methods for building primitives to control heap layout in new applications
* Return-oriented programming and shellcode development
* Methods to bypass DEP and ASLR in Windows 7 and Internet Explorer 8

## Course Structure 
The course will start off with an in-depth review of the exploitation mitigations introduced in modern operating systems. Students will demonstrate their limitations through simple examples and gradually develop basic exploitation techniques into more complicated methods applicable to real-world exploitation. Unlike most other exploitation courses, we will focus on approaching exploitation as a creative problem-solving process rather than an exercise of applying cookbook techniques to common types of vulnerabilities. Most of the course will focus on the hands-on application of the material through exercises and leading the students through the development of reliable exploits for recently patched vulnerabilities in widely used software. Each student will finish the class with their own personally developed exploit for the Aurora vulnerability in Internet Explorer that evades ASLR and DEP and reliably exploits Windows 7.

Each week, students are expected to watch the lecture videos at home and come to class prepared to work on assignments (inverted lecture format). During lab periods, students will work on project milestones and outside help will be available.

## Readings
There is no required text for this course.

Optional and recommended resources include:
* Gray Hat Hacking, 4th Edition (ISBN: 978-0071832380)
* A Bug Hunter’s Diary (ISBN: 978-1593273859)
* https://trailofbits.github.io/ctf/
* http://hackertainment.net/

## Course Requirements
This course follows a semester-long case study of the analysis and exploitation of a specific vulnerability in Internet Explorer and its use in an attack campaign against Google. This process has been broken down into a series of eight required milestones, each due at a specified time during the semester and counting equally towards the final grade. Each milestone brings the exploit one step closer to fully reliable and tested on the required platform (Windows 7, Internet Explorer 8).

After completion of the Aurora exploit, we will discuss and apply:
* Next generation exploit mitigations, such as EMET and kBouncer
* Next generation exploit techniques, such as Array object overwrites
* Automated software testing strategies aka "fuzzing"
* Toolkit creation and operational tradecraft

Finally, all students are required to participate in a capture the flag competition during the semester. Students must submit proof of solutions that they have individually completed. This is graded pass/fail. Recommended competitions:
* http://bostonkeyparty.net/
* https://ctf.acm.illinois.edu/
* http://plaidctf.com/
* Others at: https://ctftime.org/event/list/upcoming

Students are allowed only two absences per semester. Students will miss considerable in-class discussion and instruction if they miss class, since the class is delivered in an inverted lecture format (lectures on video at home).

## Grading
* All assignments count equally towards 90% of your grade.
* In-class quizzes, based on lectures, count for 10% of your grade.
* CTF participation is pass/fail (must prove participation in at least one).
* Attendance is pass/fail.
* There are no exams.

### Assignments
1.	Binary bomb lab, due in class 2
2.	Identify exploit mitigations, due in class 3
3.	Analyze & exploit ActiveX vulnerabilities, due in class 4
4.	Analyze Aurora vulnerability, due in class 5
5.	Aurora heap manipulation, due in class 6
6.	Exploit Aurora w/o DEP, due in class 7
7.	Exploit Aurora w/ DEP, due in class 8
8.	Exploit Aurora w/ dynamic ROP, due in class 9
9.	Advanced mitigations discussion – class 9
10.	Advanced techniques for browser exploits, due in class 10
11.	Fuzzer development, due in class 12
12.	Toolkit creation, due in class 13

## Course Outline
1. Introduction
  1. Course Logistics, Equipment Requirements, and Syllabus
  2. History of Vulnerability Disclosure / Ethics / Law
  3. Case Study: Aurora Campaign Analysis
  4. Reversing Lab
2.	Memory Corruption Vulnerabilities and Exploit Mitigations
  1.	Classification of memory corruption
  2.	Exploiting memory corruption
  3.	Exploitation mitigations
  4.	Exercise: Identifying active exploitation mitigations in an application
3.	Vulnerability Analysis
  1.	Vulnerability Analysis
  2.	Analysis Tools
  3.	Crash Triage
  4.	Debugger-level view of various memory corruption classes
  5.	Exercise: Analyzing vulnerabilities in a sample ActiveX Control
    1.	Stack buffer overflow
    2.	SEH frame overwrite
    3.	Heap buffer overflow
    4.	Uninitialized heap data vulnerability
    5.	Use-after-free vulnerability
  6.	Captured “Aurora” exploit analysis (IE6/XP)
  7.	Exercise: Analyze “Aurora” vulnerability on IE8/Windows 7
  8.	JavaScript development for browser exploit developers
  9.	Exercise: Improve Aurora exploit trigger determinism
4.	(Optional) Classic Memory Corruption Exploitation Techniques
  1.	Stack buffer overflow and return address overwrite
  2.	Stack buffer overflow and SEH frame overwrite
  3.	Heap buffer overflow and vtable pointer overwrite
  4.	Bypassing DEP using NtSetProcessInformation()
  5.	Bypassing Permanent DEP using WriteProcessMemory()
5.	Heap Manipulation
  1.	Heap implementation details (XP, Vista, and 7)
  2.	Heap exploitation patterns
  3.	Exercise
    1.	Draw a map of the heap
    2.	Use-after-free
    3.	Put two blocks next to each other
  4.	Custom Heaps
  5.	Building primitives for heap manipulation in new applications
  6.	Exercise: “Fuzzing” JavaScript operations to find a heap manipulation primitive for Aurora exploit
  7.	Exercise: Adding deterministic heap manipulation to “Aurora” exploit
6.	Return-Oriented Exploitation
  1.	Introducing return-oriented exploitation
  2.	Return-oriented programming
  3.	BISC (Borrowed Instruction Synthetic Computer)
  4.	Bypassing Permanent DEP
  5.	Exercises: Writing borrowed-instruction programs
    1.	Execute INT3
    2.	Call Win32 API function through Import Address Table using static arguments
    3.	Get and store value of ESP
    4.	Call sequence of Win32 API functions through IAT using dynamic arguments
    5.	Payload stager: Make traditional machine code payload executable and execute it
    6.	Threaded stager: execute repair code, run payload in new thread, execute continuation code in original thread
  6.	Exercise: Integrating return-oriented payload stage into Aurora exploit
7. Advanced Exploit Mitigations
  1. The Enhanced Mitigation Experience Toolkit (EMET)
  2. kBouncer: Efficient and Transparent ROP Mitigation
  3. ROPGuard: Runtime Prevention of ROP Attacks
  4. Exercise: Paper review and class discussion
8. Advanced Exploit Techniques
  1. Bypassing ASLR without ROP via JIT
  2. CVE-2012-492 and the Time() Technique
  3. Modifying the BSTR length/null terminator
  4. Modifying the Array object
  5. Exercise: Eliminate your heap spray and incorporate the Time() technique
9. Fuzzers
10. Toolkit Creation and Operational Tradecraft
