CS 322
======

Midterm Review

IA32 instructions
-----------------

* Read values from memory in to registers
* Operate on values in register
* write values from registers out to memory
* registers faster than memory


Addressing Modes
---------------

Register Access (reg): 

* value in a register

Memory access (mem): 
* value in memory location at address var
* 8(%eax) the value in memory location at the address formed by adding 8

Immediate (immed): 
* $15 constant value
* $var: address of memory location var

Instructions
------------

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

Registers
---------

* instruction pointer (eip) holds addr of next instruction


Flags
-----

* records details of last operation such as (was the result zero, was the result positive, did a carry occur, etc)
* 
