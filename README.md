CS 322
======

Midterm Review / Final Review

Lecture 1 / 2
--------------

* abstract syntax provides way to represent structure of programs
* interpreter/evaluaters can document the semantics of a language
* compilation goal is to translate between two languages while preserving semantics

IA32 instructions:

* Read values from memory in to registers
* Operate on values in register
* write values from registers out to memory
* registers faster than memory


Addressing Modes:

Register Access (reg): 

* value in a register

Memory access (mem): 
* value in memory location at address var
* 8(%eax) the value in memory location at the address formed by adding 8

Immediate (immed): 
* $15 constant value
* $var: address of memory location var

Instructions:

* movl: copy data from src to dest
* xchgl: exchange data between two locations
* jmp: transfer control and start executing instrutions at address
* addl: addition
* subl: subtraction
* imull: multiplication
* andl: bitwise and
* orl:  bitwise or
* xorl: bitwise xor
* jz: jump if zero flag set
* jnz: jump if zero flag not set
* je: same as jz
* jne: same as jnz
* jl: less than
* jnl: not less than
* jg: greater than
* jng: not greater than
* cmpl: compare values, only modifies flags
* negl: negate
* notl: complement
* incl: increment
* decl: decrement
* idiv: division implicit destination (edx:eax)
* call: calling a function
* ret: returning from a function

Division:

* multiple results (quotient and remainder)
* special registers (eax, edx)
* can raise an exception

Registers:

* instruction pointer (eip) holds addr of next instruction


Flags:

* records details of last operation such as (was the result zero, was the result positive, did a carry occur, etc)

Stack:

* esp (stack pointer) register
* special instructions like push, pop, call, ret
* temporary/scrath space
* supports calling and returning from functions

Memory Layout:

    program | data | free | stack
                   esp ---^

Stack Operations:

* pushl: push value onto stack
* pop: value of the stack

CISC:

* single instruction can execute multiple low-level operations
* RISC - "reduced instruction set computers" - require multiple instruction to simulate on CISC instruction

Summary:

To generate good code

* select approriate instructions
* make good use of registers and avoid memory access
* avoid registers already in use
* keep number of jumps low

Lecture 3
---------

Register Allocation: the process of arranging intermediate values to be held in registers rather than memory
Register Pressure: programs that require larger number of registers

Can be mediated by:

 * using registers carefully
 * using register spilling

Lecture 4
---------

Functions: resuable code
Procedure: doesn't return, used for effect only
Method: related to object/class

Calling Conventions

* how params are passed
* how functions return
* what happens to local vars
* etc

Base Pointer

* not modified by code like the stack pointer (esp) is
* must be saved and restroyed at the start/end of every function

Building The Stack Frame:

* caller: pushes args and executes a call instruction, which pushes the return addr
* calle: saves old base pointer and sets a new value, then decrements the stack pointer to reserve space for any local vars

* prologue: beginning part of a fuction that bulds the stack frame
* epilogue: dismantles the stack frame, leave and ret instruction
* fuction result is stored in %eax
* Adds additional overhead, and reserves %epb

System V IA32 Application Binary Interface:

* stack must be word aligned (multiples of 4)
* fuction args must be pushed in reverse order
* callee saves: ebp, ebx, edx, esi
* caller saves: ecx, edx
* return structure larger than 4 bytes, caller allocates space, passes extra arg, callee removes addr from stack and returns addr in eax






