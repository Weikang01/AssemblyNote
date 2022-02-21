### Some representative types of applications:

* Business application for single platform
* Hardware device driver
* Business application for multiple platforms
* Embedded system

### Virtual Machine Example: JVM

* JVM, the main component of Java architecture and the part of JRE. Provides the cross platform functionality to java.
* A software process that converts the compiled Java byte code to machine code.
* Byte code is an intermediary language between Java source and the host system

### .NET CL

* **Common Language Runtime** (CLR) is the virtual machine of Microsoft's .NET framework, responsible for managing the execution of .NET programs.
* <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155303769.png" alt="image-20220128155303769" style="zoom:50%;" />

### Programming language analogy:

* Each computer has a native machine language (language L0) that runs directly on its hardware
* A more human-friendly language is usually constructed above machine language, called Language L1

### Programs written in L1 can run two different ways:

* Interpretation - L0 program interprets and executes L1 instructions on by one
* Translation - L1 program is completely translated into an L0 program, which then runs on the computer hardware

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220114085041188.png" alt="image-20220114085041188" style="zoom:50%;" />

# **Specific Machine Levels**

### High-Level Language (level 4)

* Application-oriented languages
  * C++, Java, Pascal, Visual Basic...
* powerful statements that translate into multiple assembly language instructions
* Programs compile into assembly language (Level 4)

### Assembly Language (level 3)

* Instruction mnemonics (such as ADD, SUB, and MOV)
* Have a one-to-one correspondence to machine language
* Programs are translated into Instructions Set Architecture Level - machine language (Level 2)
* Assembly language programs are translated (assembled) in their entirety into machine language before they begin to execute

### Instruction Set Architecture (ISA) (Level 2)

* Also known as conventional machine language
* First level at which users can write programs
  * The programs consist of binary values called machine language.
  * Each machine-language instruction is executed
    * Directly by the computer's hardware
    * or by a program embedded in the microprocessor chip called a microprogram
  * Executed by Level 1 (Digital Logic)

### Digital Logic Hardware (Level 1)

CPU, constructed from digital logic gates

System bus

Memory

Implemented using bipolar transistors

### Data Representation

* Binary Numbers
  * Translating between binary and decimal
* Binary Addition
* Integer Storage Sizes
* Hexadecimal Integers
  * Translating between decimal and hexadecimal
  * Hexadecimal subtraction
* Signed Integers
  * Binary subtraction
* Character Storage

### Digits for the Numbering in Hardware and Software Manuals

| System          | Base | Possible Digits                 |
| --------------- | ---- | ------------------------------- |
| **Binary**      | 2    | 0 1                             |
| **Octal**       | 8    | 0 1 2 3 4 5 6 7                 |
| **Decimal**     | 10   | 0 1 2 3 4 5 6 7 8 9             |
| **Hexadecimal** | 16   | 0 1 2 3 4 5 6 7 8 9 A B C D E F |

### Binary Numbers

* Computer stores instructions and data in memory as collections of electronic charges on/off
* Digits are 1 and 0, called bit
  * 1 = true
  * 0 = false
* **Bits** are numbered sequentially starting at zero on the right side and increasing toward the left.
  * MSB - most significant bit
  * LSB - least significant bit

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155334167.png" alt="image-20220128155334167" style="zoom: 50%;" />

**Binary Numbers**

Each digits (bit) is either 1 or 0

Each bit represents a power of 2  ![image-20220128155345833](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155345833.png)

## Translating Binary to Decimal

* Weighted positional notation shows how to calculate the decimal value of each binary bit:

  $dec = (D_{n-1}\times{2^{n-1}})+(D_{n-2}\times{2^{n-2}})+\dots+(D_1\times{2^1})+(D_0\times{2^0})$

* D = binary digit, 0 or 1

* binary 00001001 = decimal 9:

  $(1\times2^3)+(1\times2^0)=9$

## Translating Binary to Decimal

Horner's rule: [Horner's method - Wikipedia](https://en.wikipedia.org/wiki/Horner's_method)

​	$dec = ((\dots((D_{n-1}\times2)+D_{n-2})\times2)+\dots+D_1)\times2+D_0$

​	$10001001_b=128+8+1-137_b$

​	$dec = ((\dots(1\times2)+0)\times2)+\dots+0)\times2+1$

Good for code implementation

Example: $10010101101_b\rightarrow1197_d$

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155403841.png" alt="image-20220128155403841" style="zoom:60%;" />

## Translating Unsigned Decimal to Binary

Repeatedly divide the decimal integer by 2. Each remainder is a binary digit in the translated value:

| Division | Quotient | Remainder |
| -------- | -------- | --------- |
| 37/2     | 18       | 1         |
| 18/2     | 9        | 0         |
| 9/2      | 4        | 1         |
| 4/2      | 2        | 0         |
| 2/2      | 1        | 0         |
| 1        | 0        | 1         |

​	37=100101

### Binary Addition

>    00001100
>
> +10001010
>
>   10010110

## Integer Storage Sizes

**Standard sizes**:

* byte: 8
* word: 16
* doubleword: 32
* quadword: 64

Ranges of Unsigned Integers.

| Storage Type        | Range (low-high)                | Powers of 2       |
| ------------------- | ------------------------------- | ----------------- |
| Unsigned byte       | 0 to 255                        | 0 to $(2^8-1)$    |
| Unsigned word       | 0 to 65,535                     | 0 to $(2^{16}-1)$ |
| Unsigned doubleword | 0 to 4,294,967,295              | 0 to $(2^{32}-1)$ |
| Unsigned quadword   | 0 to 18,446,744,073,709,551,615 | 0 to $(2^{64}-1)$ |

The Dec range is: 0 to $(2^n)-1$ where if the number of bits

## Hexadecimal Integers

### Binary values are represented in hexadecimal.

Binary, Decimal and Hexadecimal Equivalents.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128124337845.png" alt="image-20220128124337845" style="zoom:67%;" />

## Translating Binary to Hexadecimal

* Each hexadecimal digit corresponds to 4 binary bits.
* Example: Translate the binary integer 1,0110,1010,0111,1001,0100 to hexadecimal:

Try to separate: 0001,0110,1010,0111,1001,0100

| 1    | 6    | A    | 7    | 9    | 4    |
| ---- | ---- | ---- | ---- | ---- | ---- |
| 0001 | 0110 | 1010 | 0111 | 1001 | 0100 |

### Converting Hexadecimal to Decimal

* Multiply each digit by its corresponding power of 16:

  ​	$dec=(D_3\times16^3)+(D_2\times16^2)+(D_1\times16^1)+(D_0\times16^0)$

* Hex 1234 equals $(1\times16^3)+(2\times16^2)+(3\times16^1)+(4\times16^0)$, or decimal 4660.

* Hex 3BA4 equals $(3\times16^3)+(11\times16^2)+(10\times16^1)+(4\times16^0)$, or decimal 15268.

  * Horner's rule: $(((((3\times16)+11)\times16)+10)\times16)+4$

## Converting Decimal to Hexadecimal

| Division | Quotient | Remainder |
| -------- | -------- | --------- |
| 422/16   | 26       | 6         |
| 26/16    | 1        | A         |
| 1/16     | 0        | 1         |

decimal 422 = 1A6 hexadecimal

## Hexadecimal Addition

Divide the sum of two digits by the number base (16). The quotient becomes the carry value, and the remainder is the sum digit.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155514737.png" alt="image-20220128155514737" style="zoom:67%;" />

## Hexadecimal Subtraction

When a borrow is required from the digit to the left, add 16 (decimal) to the current digit's value:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155556781.png" alt="image-20220128155556781" style="zoom:67%;" />

## Signed Integers

The highest bit indicates the sign. 1 = negative, 0 = positive

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155627099.png" alt="image-20220128155627099" style="zoom:67%;" />

If the highest digit of a hexadecimal integer is > 7, the value is negative. Examples: 8A, C5, A29D, B1234567

## Forming the Two's Complement

> Negative numbers are stored in two's complement notation
>
> Represents the additive Inverse

| Starting value                             | 00000001            |
| ------------------------------------------ | ------------------- |
| **Step 1: reverse the bits**               | 11111110            |
| **Step 2: add 1 to the value from Step 1** | 11111110 + 00000001 |
| **Sum: two's complement representation**   | 11111111            |

* Note that 00000001 + 11111111 = 0000000-
* Two's Complement operation is **<u>reversible</u>**. Two's Complement of 11111111 is 00000001.

## Binary Subtraction

When subtracting A – B, convert B to its two's complement
Add A to (–B)

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155716452.png" alt="image-20220128155716452" style="zoom:67%;" />

## Learn How To Do the Following:

* Form the two's complement of a hexadecimal for ($-27197_d$)
  * $6A3D_h\rightarrow95C2_h+1\rightarrow95C3_h$
* Convert **signed** binary to decimal
  * $11110000_b\rightarrow00001111+1\rightarrow-16_d$
* Convert **signed** decimal to binary
  * $-43_d\rightarrow(-43_d\rightarrow 00101011_b, 11010100_b+1)\rightarrow11010101_b$
* Convert **signed** decimal to hexadecimal
  * $-43_d\rightarrow D5_h$
* Convert **signed** hexadecimal to decimal
  * $D5_h\rightarrow (2A_h+1 = 2B_h) -43_d$

## Range of Signed Integers

The highest bit is reserved for the sign. This limits the range:

from $-2^{n-1}$  to $2^{n-1}-1$

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160447449.png" alt="image-20220128160447449" style="zoom:67%;" />

## Character Storage

**Character sets: mapping of characters to integers**

* **Standard ASCII (0-127)**

  * **ASCII**: American Standard Code for Information Interchange
  * Unique 7-bit integer is assigned to each character

* **Extended ASCII (0-255)**

  * The extra bit is used on various computers to create a proprietary character set
  * IBM use values 128 through 255 represent graphics symbols and Greek characters

* **ANSI (0-255)**

  * ANSI: American National Standards Institute
  * The first 128 characters correspond to the letters and symbols on a standard U.S. keyboard.
  * The second 128 characters represent special characters such as letters in international alphabets, accents, currency symbols, and fractions.

* [ASCII - Wikipedia](https://en.wikipedia.org/wiki/ASCII)

* **Unicode (0-65,535)**

  * Universal way of defining characters and symbols
  * Represent a wide variety of international languages in computer software.
  * Defines codes for characters, symbols, and punctuation used in all major languages
  * European alphabetic scripts, Middle Eastern right-to-left scripts, and many scripts of Asia

* **Null-terminated String**

  * It is a string of characters followed by a single byte containing zero.
  * Array of characters followed by a null byte
  * The C and C++ languages use null terminated strings, and many DOS and Windows functions require strings to be in this format.

  # Boolean Algebra

* Based on symbolic logic, designed by George Boole

  * http://en.wikipedia.org/wiki/George_Boole

* Boolean expressions created from:

  * NOT, AND, OR

  <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160340029.png" alt="image-20220128160340029" style="zoom:67%;" />

## Operator Precedence

Examples showing the order of operations:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160406503.png" alt="image-20220128160406503" style="zoom:67%;" />

# **General Concepts**

## Basic microcomputer design

clock synchronizes CPU operations
control unit (CU) coordinates sequence of execution steps
ALU performs arithmetic and bitwise processing

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154440857.png" alt="image-20220128154440857" style="zoom:67%;" />

## Clock

* Synchronizes all CPU and BUS operations
* Machine (clock) cycle measures time of a single operation
* Clock is used to trigger events
* A cycle duration is the reciprocal of the clock's speed
  * 1 GH: cycle duration 1 billionth of a second, 1 nanosecond
* Wait state, empty cycle

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154430042.png" alt="image-20220128154430042" style="zoom:67%;" />

## Instruction Execution Cycle

Figure: Simplified Pentium CPU Block Diagram.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154332081.png" alt="image-20220128154332081" style="zoom:67%;" />

## Instruction Execution Cycle

* Fetch
* Decode
* Fetch operands
* Execute
* Store output

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154417436.png" alt="image-20220128154417436" style="zoom:67%;" />

## Reading from Memory

Multiple machine cycles are required when reading from memory, because it responds much slower than the CPU. The steps are:

1. Place the address of the value you want to read on the address bus.
2. Assert (changing the value of) the processor's RD (read) pin.
3. Wai one clock cycle for the memory chips to respond.
4. Copy the data from the data bus into the destination operand.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154320496.png" alt="image-20220128154320496" style="zoom:67%;" />

## Cache Memory

High-speed expensive static RAM both inside and outside the CPU.

* Level-1 cache: inside the CPU
* Level-2 cache: outside the CPU

**Cache hit**: when data to be read is already in cache memory
**Cache miss**: when data to be read is not in cache memory.
**Online reading**: How Computer Memory Works

* http://computer.howstuffworks.com/computer-memory4.htm

# How a Program Runs

* As soon as the program begins running, it’s called a Process
* A process has its memory and may contains multiple Threads

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154253792.png" alt="image-20220128154253792" style="zoom: 67%;" />

## Multitasking

* OS can run multiple programs at the same time.
* Multiple threads of execution within the same program.
* Scheduler utility assigns a given amount of CPU time to each running program.
* Rapid switching of tasks
  * gives illusion that all programs are running at once
  * the processor must support task switching.

## Round-Robin Scheduler

Task switching: Context, Priority

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154540365.png" alt="image-20220128154540365" style="zoom:80%;" />

# IA-32 Processor Architecture

* Short for **"Intel Architecture, 32-bit"**
* Modes of operation
* Basic execution environment
* Floating-point unit
* Intel Microprocessor history

## Modes of Operation

* Protected mode
  * native mode (Windows, Linus)
* Real-address mode
  * native MS-DOS
* System management mode
  * power management, system security, diagnostics
* Virtual-8060 mode
  * hybrid of Protected
  * each program has its own 8089 computer
  * allows the execution of real mode applications that are incapable of running directly in protected mode while the processor is running a protected mode operating system.

## Basic Execution Environment

* Addressable memory
* General-purpose registers
* Index and base registers
* Specialized register uses
* Status flags
* Floating-point, MMX, XMM registers

## Addressable Memory

* Protected mode
  * The range of memory is 4 GB
  * 32-bit address
* Read-address and Virtual-8086 modes
  * 1 MB space
  * 20-bit address

## General-Purpose Registers

Named storage locations inside the CPU, optimized for speed.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154626197.png" alt="image-20220128154626197" style="zoom:80%;" />

## Accessing Parts of Registers

Use 8-bit name, 16-bit name, or 32-bit name

Applies to EAX, EBX, ECX, and EDX

![image-20220128154652399](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154652399.png)

## Index and Base Registers

Some registers have only a 16-bit name for their lower half:

| 32-bit | 16-bit |
| ------ | ------ |
| ESI    | SI     |
| EDI    | DI     |
| EBP    | BP     |
| ESP    | SP     |

## Some Specialized Register Uses

* **General-Purpose**
  * EAX - accumulator
  * ECX - loop counter
  * ESP - stack pointer
  * ESI, EDI - index registers
  * EBP - extended frame pointer (stack)
* **Segment**
  * CS - code segment
  * DS - data segment
  * SS - stack segment
  * ES, FS, GS - additional segments
* **EIP - instruction pointer**
  * IP for 16-bit
* **EFLAGS**
  * status and control flags
  * each flag is a single binary bit

## Status Flags

* The **Carry** flag (CF) is set when the result of an ***unsigned*** arithmetic operation is too large to fit into the destination.
* The **Overflow** flag (OF) is set when the result of a ***signed*** arithmetic operation is too large or too small to fit into the destination. 
* The **Sign** flag (SF) is set when the result of an arithmetic or logical operation generates a negative result.
* The **Zero** flag (ZF) is set when the result of an arithmetic or logical operation generates a result of zero.
* The **Auxiliary Carry** flag (AC) is set when an arithmetic operation causes a carry from bit 3 to bit 4 in an 8-bit operand.
* The **Parity** flag (PF) is set if the lease-significant byte in the result contains an even number of 1 bits. Otherwise, PF is clear. In general, it is used for error checking when there is a possibility that data might be altered or corrupted.
  * If the result of the last operation were 26 (11010 in binary), the parity flag would be 0 since the number of set bits is odd. Similarly, if the result where 10 (1010 in binary) then the parity flag would be 1.

## Floating-Point, MMX, XXM Registers

* Eight 80-bit floating-point data registers
  * ST(0), ST(1),...,ST(7)
    * <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154717444.png" alt="image-20220128154717444" style="zoom:80%;" />
  * arranged in a stack
  * used for all floating-point arithmetic
* Eight 64-bit MMX registers
  * a single instruction, multiple data [(SIMD) instruction set architecture][https://en.wikipedia.org/wiki/SIMD]
  * MMX instructions operate in parallel on the data values contained in MMX registers
* Eight 128-bit XMM registers for single-instruction multiple-data(SIMD) operations

# CISC and RISC

* CISC - complex instruction set
  * large instruction set
  * high-level operations
  * requires microcode interpreter
  * examples: Intel 80x86 family
* RISC - reduced instruction set
  * simple, atomic instructions
  * small instruction set
  * directly executed by hardware
  * examples:
    * ARM (Advanced RISC Machines)
      * [ARM Assembly Language Programming][http://www.peter-cockerell.net/aalp/html/frames.html]

# IA-32 Memory Management

## Real-address mode

* 1 MB RAM maximum addressable
* Application programs can access any area of memory
* Single tasking
* Supported by MS-DOS operating system

## Calculating linear addresses

## Protected mode

* 4 GB addressable RAM
  * (00000000 to FFFFFFFFh)
* Each program assigned a memory partition which is protected from other programs
* Designed for multitasking
* Supporting by Linux & MS-Windows

## Paging

* Supported directly by the CPU
* Divides each segment into 4096-byte blocks called **pages**
* Sum of all programs can be larger than physical memory
* Part of running program is in memory, part is on disk
* **Virtual memory manager** (VMM) - OSS utility that manages the loading and unloading of pages
* **Page fault** - issued by CPU when a page must be loaded from disk

## 64-Bit Processors

### 64-Bit Operation Modes

* Compatibility mode - can run existing 16-bit and 32-bit applications (windows supports only 32-bit apps in this mode)
* 64-bit mode - Windows 64 uses this

### Basic Execution Environment

* addresses can be 64 bits (48 bits, in practice)
* 16 64-bit general purpose registers
* 64-bit instruction pointer

# 64-Bit General Purpose Registers

32-bit general purpose registers:

* EAX, EBX, ECX, EDI, ESI, EBP, ESP, R8D, R9D, R10D, R11D, R12D, R13D, R14D, R15D

64-bit general purpose registers:

* RAX, RBX, RCX, RDX, RDI, RSI, RBP, RSP, R8, R9, R10, R11, R12, R13, R14, R15

# 64-bit Processors

**Intel64**

* 64-bit linear address space
* Intel: Pentium Extreme, Xeon, Celeron D, Pentium D, Core 2, and Core i7

**IA-32e Mode**

* Compatibility mode for legacy 16- and 32-bit applications
* 64-bit Mode uses 64-bit addresses and operands

# Components of an IA-32 Microcomputer

* **Motherboard**
* **Video output**
* **Memory**
* **Input-output ports**

## Motherboard

* CPU socket External cache memory slots
* Main memory slots
* BIOS chips
* Sound synthesizer chip (optional)
* Video controller chip (optional)
* IDE, parallel, serial, USB, video, keyboard, joystick, network, and mouse connectors
* PCI(Peripheral Component Interconnect) but connectors (expansion cards)

![image-20220121090517439](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220121090517439.png)

## Video Output

* Video controller
  * on motherboard, or on expansion card
  * AGB (accelerated graphics port technology)
* Video memory (VRAM)
* Video CRT Display
  * uses raster scanning
  * horizontal retrace
  * vertical retrace
* Direct digital LCD monitors
  * no raster scanning required

### Sample Video Controller (ATI Corp.)

* 128-bit 3D graphics performance powered by RAGE™ 128 PRO 
* 3D graphics performance 
* Intelligent TV-Tuner with Digital VCR 
* TV-ON-DEMAND™ 
* Interactive Program Guide 
* Still image and MPEG-2 motion video capture 
* Video editing 
* Hardware DVD video playback 
* Video output to TV or VCR 

![image-20220128155012767](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155012767.png)

## Memory

* ROM
  * read-only memory
* EPROM
  * erasable programmable read-only memory, ultraviolet light
* Dynamic RAM (Random Access Memory) (DRAM)
  * inexpensive; must be refreshed constantly
* Static RAM (SRAM)
  * expensive; used for cache memory; no refresh required
* Video RAM (VRAM)
  * dual ported; optimized for constant video refresh
* CMOS RAM
  * complementary metal-oxide semiconductor
  * system setup information

## Input-Output Ports

* USB (universal serial bus)
  * intelligent high-speed connection to devices
  * 480 megabits/second (2.0), 12 mb/s (1.0)
  * USB hub connects multiple devices
  * ***enumeration***: computer queries devices
  * supports ***hot*** connections
* Parallel
  * short cable, high speed
  * common for printers
  * bidirectional, parallel data transfer
  * Intel 8255 controller chip
* Serial
  * RS-232 serial port
  * one bit at a time
  * uses long cables and modems
  * 16550 UART (universal asynchronous receiver transmitter)
  * programmable in assembly language

# Device Interfaces

* ATA (***advanced technology attachment***) host adapters
  * intelligent drive electronics (hard drive, CDROM)
* SATA (Serial ATA)
  * inexpensive, fast, bidirectional
* FireWire
  * high speed (800MB/sec), many devices at once
* Bluetooth
  * small amounts of data, short distances, low power usage
* Wi-Fi (Wireless Ethernet)
  * IEEE 802.11 standard, faster than Bluetooth

# Levels of Input-Output

* Level 3: High-level language function
  * examples: C++, Java
  * portable, convenient, not always the fastest
* Level 2: Operating system
  * Application Programming Interface (API)
  * extended capabilities, lots of details to master
* Level 1: BIOS
  * drivers that communicate directly with devices
  * OS security may prevent application-level code from working at this level

## Displaying a String of Characters

When a HLL program displays a string of characters, the following steps take place:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155102877.png" alt="image-20220128155102877" style="zoom:67%;" />

## Programming levels

Assembly language programs can perform input-output at each of the following levels:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155126030.png" alt="image-20220128155126030" style="zoom:80%;" />

# Mnemonics and Operands

* Instruction Mnemonics
  * memory aid
  * examples: MOV, ADD, SUB, MUL, INC, DEC
* Operands
  * constant
  * constant expression
  * register
  * memory (data label)
* Constants and constant expressions are often called **immediate values**

# Integer Constants

* Optional leading + or - sign
* Binary, decimal, hexadecimal, or octal digits
* Common radix characters:
  * h - hexadecimal
  * d - decimal
  * b - binary
  * r - encoded real
    * [sign] integer.[integer]\[exponent]
    * 2., +3.0, -44.2E+05, 26.E5
    * At least one digit and a decimal point are required
* Examples: 30d, 6Ah, 42, 1101b

Hexadecimal beginning with letter: **0**A5h

* r - encoded real: to write a real number, at least we need to type a number and a dot "."
* hexadecimal: beginning with 0

# Integer Expressions

### Operators and precedence levels:

| Operator | Name              | Precedence Level |
| -------- | ----------------- | ---------------- |
| ( )      | parentheses       | 1                |
| +, -     | unary plus, minus | 2                |
| *, /     | multiply, divide  | 3                |
| MOD      | modulus           | 3                |
| +, -     | add, subtract     | 4                |

### Examples:

| Expression          | Value |
| ------------------- | ----- |
| 16 / 5              | 3     |
| - (3 + 4) * (6 - 1) | -35   |
| -3 + 4 * 6 - 1      | 20    |
| 25 mod 3            | 1     |

# Character and String Constants

* Enclose character in single or double quotes
  * 'A', "x"
  * ASCII character = 1 byte
* Enclose strings in single or double quotes
  * "ABC"
  * 'xyz'
  * Each character occupies a single byte
* Embedded quotes:
* 'Say "Goodnight," Gracie'

# Reserved Words and Identifiers

* Reserved words cannot be used as identifiers
  * Instruction mnemonics, such as MOV, ADD, and MUL
  * Register names
  * Directives, which tell MASM how to assemble programs
  * Attributes, which provide size and usage information for variables and operands. Examples are BYTE and WORD
  * Operators, used in constant expressions (+, -, *, ...)
  * Predefined symbols, such as @data, which return constant integer values at assembly time
  * See MASM reference in Appendix A
    * Microsoft Macro Assembler Reference
  * Identifiers
    * 1-247 characters, including digits
    * not case sensitive
    * first character must be a letter, _, @, ? or $

# Directives

* Commands that are recognized and acted upon by the assembler

  * Not part of the Intel instruction set
  * Used to declare code, data areas, select memory model, declare procedures, etc.
  * not case sensitive

* Different assemblers have different directives

  * NASM not the same as MASM, for example

* The .DATA directive identifies the area of a program containing variables:

  ```assembly
  .data
  ```

* The .STACK directive identifies the area of a program holding the runtime stack, setting its size:

  ```assembly
  .stack 100h
  ```

* Example:

  ```assembly
  myVar DWORD 26	; DWORD directive
  mov eax, myVar	; MOV instruction
  ```

The DWORD directive tells the assembler to reserve space in the program for a doubleword variable.

The MOV instruction, on the other hand, executes at runtime, copying the contents of myVar to the EAX register.

# **Instructions**

* Assembled into machine code by assembler
* Executed at ***runtime*** by the CPU
* We use the Intel IA-32 instruction set
* An instruction contains:
  * Label			(optional)
  * Mnemonic	(required)
  * Operand	   (depends on the instruction)
  * Comment	 (optional)
  * [Label:] Mnemonic Operand(s) [; Comment]

# Labels

* Act as place markers

  * marks the address (offset) of code and data

* Follow identifier rules

* Data label

  * Data Labels A data label identifies the location of a variable, providing a convenient way to reference the variable in code. The following, for example, defines a label named count:

    ```assembly
    count DWORD 100
    ```

  * must be unique

* Code label

  * in the code area of a program (where instructions are located) (followed by colon)

  * target of jump and loop instructions

  * example

    ```assembly
    target:
    	mov ax, bx
    	...
    	jmp target
    ```

# Mnemonics and Operands

## Instruction Mnemonics

* memory aid
* examples:
  * mov Move (assign) one value to another
  * add Add two values
  * sub Subtract one value from another
  * mul Multiply two values
  * jmp Jump to a new location
  * call Call a procedure

## Operands

* Assembly language can have between zero and three operands

  * constant

  * constant expression

  * register

  * memory (data label)

  * Constants and constant expressions are often called ***immediate values***

    | Example | Operand Type                     |
    | ------- | -------------------------------- |
    | 96      | Constant (***immediate value***) |
    | 2 + 4   | Constant expression              |
    | eax     | Register                         |
    | count   | Memory                           |

# Instruction Format Examples

* No operand

  ```assembly
  std	; set Carry flag
  ```

* One operand

  ```assembly
  inc eax	; register
  inc myByte	; memory
  ```

* Two operands

  ```assembly
  add ebx, ecx	; register, register
  sub myByte, 25	; memory, constant
  add eax, 36*25	; register, constant-expression
  mov count,ebx	; move EBX to count
  ```

* Three operands

  ```assembly
  imul eax,ebx,5	; EBX multiplied by 5, and the result stored in EAX.
  ```

# Comments

* Comments are good!
  * explain the program's purpose
  * when it was written, and by whom
  * revision information
  * tricky coding techniques
  * application-specific explanations
* Single-line comments
  * begin with semicolon (;)
* Multi-line comments
  * begin with COMMENT directive and a programmer-chosen character
  * end with the same programmer-chosen character

```assembly
; this is a single line comment
COMMENT $
	this is a multiline comment
$
```

```assembly
; AddTwo.asm
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO, dwExitCode:DWORD
.code
main PROC
	mov eax, 5	; move 5 to the EAX register
	add eax, 6	; add  6 to the EAX register
	
	INVOKE ExitProcess, 0
main ENDP
END main
```

## Example Output

**Showing registers and flags in the debugger:**

```output
EAX = 0000000B EBX = 7EFDE000 ECX = 00000000 EDX = 0040100A ESI = 00000000 EDI = 00000000 EIP = 00401054 ESP = 0018FF8C EBP = 0018FF94 EFL = 00000202 

OV = 0 UP = 0 EI = 1 PL = 0 ZR = 0 AC = 0 PE = 0 CY = 0 
```

## 16-bit FLAGS Register

| **Bit** | **11** | **10** | **9**  | **8** | **7**  | **6**  | **5** | **4**  | **3** | **2**  | **1** | **0**  |
| ------- | ------ | ------ | ------ | ----- | ------ | ------ | ----- | ------ | ----- | ------ | ----- | ------ |
| **Txt** | **OF** | **DF** | **IF** |       | **SF** | **ZF** |       | **AF** |       | **PF** |       | **CF** |
| **VS**  | **OV** | **UP** | **EI** |       | **PL** | **ZR** |       | **AC** |       | **PE** |       | **CY** |

Bit0: CF - Carry Flag 					Bit1: always a 1 
Bit2: PF - Parity Flag 					Bit3: always a 0 
Bit4: AF - Auxiliary (Carry) 			Bit5: always a 0 
Bit6: ZF - Zero Flag 					  Bit7: SF - Sign Flag 
Bit8: TF - Trap Flag (no use)		 Bit9: IF - Interrupt Flag 
Bit10: DF - Direction Flag 			 Bit11: OF – Overflow

# Suggested Coding Standards

### Some approaches to capitalization

* capitalize nothing
* capitalize everything
* capitalize all reserved words, including instruction mnemonics and register names
* capitalize only directives and operators

### Other suggestions

* descriptive identifier names
* spaces surrounding arithmetic operators
* blank lines between procedures

### Indentation and spacing

* code and data labels - no indentation
* executable instructions - indent 4-5 spaces
* comments: right side of page, aligned vertically
* 1-3 spaces between instruction and its operands
  * ex: mov ax, bx
* 1-2 blank lines between procedures

### Program Template

```assembly
; Program Template

; Description:
; Author:
; Creation Date:
; Revisions:
; Date:
; Modified by:

; Template.asm
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO, dwExitCode:DWORD
.code
main PROC
	; write your code here
	INVOKE ExitProcess, 0
main ENDP
END main
```

## Assemble-Link Execute Cycle

* The following diagram describes the steps from creating a source program through executing the compiled program.
* If the source code is modified, Steps 2 through 4 must be repeated.
* The assembler contains a **preprocessor** to process directives, etc.

![image-20220128161826130](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161826130.png)



# Listing File

* Listing file suitable for printing, and contains a copy of the program's
  * source code,
  * with line numbers,
  * offset addresses,
  * segment names,
  * translated machine code,
  * and a symbol table
* Use it to see how your program is compiled
* Example: addSub.lst

# Map File

* Information about each program segment:
  * starting address
  * ending address
  * size
  * segment type
* Example: addSub.map (16-bit version)

# The NOP Instruction

* It takes up 1 byte of program storage and doesn't do any work. It is sometimes used by compilers and assembler
* Code alignment: Align the code to even-address boundaries
* Check from a list file
* Debug from Disassembly window:

```disassembly
00000000 66 8B C3 mov ax, bx
00000003 90 nop				; align next instruction
00000004 8B D1 mov edx, ecx
```

# Intrinsic Data Types

* Describes a set of values that can be assigned to variables and expressions of the given type.
* BYTE, SBYTE
  * 8-bit unsigned integer; 8-bit signed integer
* WORD, SWORD
  * 16-bit unsigned & signed integer
* DWORD, SDWORD
  * 32-bit unsigned & signed integer
* QWORD
  * 64-bit integer
* TBYTE
  * 80-bit integer
* REAL4
  * 4-byte IEEE short real
* REAL8
  * 8-byte IEEE long real
* REAL10
  * 10-byte IEEE extended real

# Data Definition Statement

* A data definition statement sets aside storage in memory for a variable.
* May optionally assign a name (label) to the data
* Syntax:
  * [name] directive initializer [,initializer]...
  * **value1 BYTE 10**
* All initializers become binary data in memory

# Defining BYTE and SBYTE Data

Each of the following defines a single byte of storage:

```assembly
value1 BYTE 'A'			; character constant
value2 BYTE 0			; smallest unsigned byte
value1 BYTE 255			; largest unsigned byte
value1 SBYTE -128		; smallest signed byte
value1 SBYTE +127		; largest signed byte
value1 BYTE ?			; unitialized byte
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
; * MASM does not prevent you from initializing a BYTE with a
;	negative value, but it's considered poor style.
; * If you declare a SBYTE variable, the Microsoft debugger
;	automatically display its value in decimal with a leading
;	sign.
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
```

## Defining Byte Arrays

Examples that use multiple initializers:

```assembly
list1 BYTE 10, 20, 30, 40
list2 BYTE 10, 20, 30, 40
	  BYTE 50, 60, 70, 80
list3 BYTE ?, 32, 41h, 00100010b
list4 BYTE 0Ah, 20h, 'A', 22h	; different radixes
```

# Defining Strings

* A string is implemented as an array of characters

  * For convenience, it is usually enclosed in quotation marks
  * It often will be null-terminated (null byte containing 0)

* Examples:

  ```assembly
  str1 BYTE "Enter your name", 0
  str2 BYTE 'Error: holting program', 0
  str3 BYTE 'A', 'E', 'I', 'O', 'U'
  greeting BYTE "Welcome to the Encryption Demo program "
  		BYTE "created by Kip Irvine.", 0
  ```

### To continue a single string across multiple lines, end each line with a comma:

```assembly
menu BYTE "Checking Account", 0dh, 0ah, 0dh, 0ah,
	"1. Create a new account", 0dh, 0ah,
	"2. Open an existing account", 0dh, 0ah,
	"3. Credit the account", 0dh, 0ah,
	"4. Debit the account", 0dh, 0ah,
	"5. Exit", 0dh, 0ah,
	"Choice> ", 0
```

End-of-line character sequence:

* 0Dh = carriage return
* 0Ah = line feed

CR/LF: When written to standard output, they move the cursor to the left column of the line following the current line.

```assembly
str1 BYTE "Enter your name:		", 0Dh, 0Ah,
	BYTE "Enter your address:	", 0

newLine BYTE 0Dh, 0Ah, 0
```

# Using the DUP Operator

Use DUP to allocate (create space for) an array or string. Syntax: counter DUP (argument)

Counter and argument must be constants or constant expressions

```assembly
var1 BYTE 20 DUP(0)			; 20 bytes, all equal to zero
var2 BYTE 20 DUP(?)			; 20 bytes, uninitialized
var3 BYTE 4 DUP("STACK")	; 20 bytes: "STACKSTACKSTACKSTACK"
var4 BYTE 10,3 DUP(0), 20	; 5 bytes
```

# Defining WORD and SWORD Data

Define storage for 16-bit integers

* or double characters
* single value or multiple values

```assembly
word1 WORD 65535			; largest unsigned value
word2 SWORD -32768			; smallest signed value
word3 WORD ?				; uninitialized, unsigned
word4 WORD "AB"				; double characters
myList WORD 1,2,3,4,5		; double characters
array WORD 5 DUP(?)			; uninitialized array
```

# Defining DWORD and SDWORD Data

### Storage definitions for signed and unsigned 32-bit integers:

```assembly
val1 DWORD 12345678h		; unsigned
val2 SDWORD -2147483648		; signed
val3 DWORD 20 DUP(?)		; unsigned array
val4 SWORD -3,-2,-1,0,1		; signed array
```

# Defining QWORD TBYTE, Real Data

Storage definitions for quadwords, tenbyte values, and real numbers:

```assembly
quad1 QWORD      1234567812345678h
val1  TBYTE      100000000123456789Ah
rVal1 REAL4      -2.1
rVal2 REAL8      2.3E-260
rVal3 REAL10     4.6E+4096
ShortArray REAL4 20 DUP(0.0)
```

# Little Endian Order

All data types larger than a byte store their individual bytes in reverse order. The least significant byte occurs at the first (lowest) memory address.

Example:

```assembly
val1 DWORD 12345678h
```

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161617586.png" alt="image-20220128161617586" style="zoom:67%;" />

# Big Endian Order

All data types larger than a byte store their individual bytes in "usual" order. The most significant byte occurs at the first (lowest) memory address.

Example:

```assembly
val1 DWORD 12345678h
```

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161640775.png" alt="image-20220128161640775" style="zoom: 67%;" />

# Adding Variables to AddSub

* [Irvin Libraries][http://asmirvine.com/gettingStartedVS2019/index.htm]

```assembly
; This program adds and subtracts 32-bit unsigned
; integers and stores the sum in a variable.
INCLUDE Irvine32.inc
.data
val1 DWORD 10000h
val2 DWORD 40000h
val3 DWORD 20000h
finalVal DWORD ?
.code
main PROC
	mov eax,val1		; start with 10000h
	add eax,val2		; add 40000h
	sub eax,val3		; subtract 20000h
	mov finalVal,eax	; store the result (30000h)
	call DumpRegs		; display the registers
	exit
main ENDP
END main
```

## Declaring Uninitialized Data

Use the .data? directive to declare an uninitialized data segment:

```assembly
.data?
```

Within the segment, declare variables with "?" initializers:

```assembly
smallArray DWORD 10 DUP(?)
```

**Advantage: the program's EXE file size is reduced.**

## Equal-Sign Directive
name = expression
* expression is a 32-bit integer (expression or constant)
* may be redefined
* name is called a symbolic constant

good programming style to use symbols

```assembly
COUNT = 500
.
.
mov ax,COUNT
```

## Redefine with Equal-Sign

```assembly
count = 5
mov al, count

...
count = 100
mov al, count

...

Count = “This is a count!”
```

## Calculating the Size of a Byte Array

current location counter: $

* subtract address of list
* difference is the number of bytes

```assembly
list BYTE 10,20,30,40
ListSize = ($ - list)
```

## Calculating the Size of a Word Array

Divide total number of bytes by 2 (the size of a word)

* ($ - list) is byte count

```assembly
list WORD 1000h,2000h,3000h,4000h
ListSize = ($ - list) / 2
```

## Calculating the Size of a Doubleword Array

Divide total number of bytes by 4 (the size of a doubleword)

```assembly
list DWORD 1,2,3,4
ListSize = ($ - list) / 4
```
# EQU Directive
* Define a symbol as either a number or text expression.
* Cannot be redefined
```assembly
PI EQU <3.1416>
pressKey EQU <"Press any key to continue...",0>
.data
prompt BYTE pressKey
```
```assembly
Matrix1 EQU 10*10
Matrix2 EQU <10*10>
.data
M1 word Matrix1 ; M1 word 100
M2 word Matrix2 ; M2 word 10*10
```
# TEXTEQU Directive
* Define a symbol as either an integer or text expression.
* Called a **text macro**
* Can be redefined
```assembly
continueMsg TEXTEQU <"Do you wish to continue (Y/N)?">
rowSize = 5
.data
prompt1 BYTE continueMsg
count TEXTEQU %(rowSize * 2)		; evaluates the expression
setupAL TEXTEQU <mov al,count>

.code
setupAL		; generates: "mov al,10"
```

# 64-Bit Programming

MASM supports 64-bit programming, although the following directives are not permitted:

* INVOKE, ADDR, .model, .386, .stack

## 64-Bit Version of AddTwoSum

```assembly
; AddTwoSum_64.asm - Chapter 3 example.
ExitProcess PROTO
.data
sum DWORD 0
.code
main PROC
	mov eax, 5
	add eax, 6
	mov sum, eax
	mov ecx, 0
	call ExitProcess
main ENDP
END
```

# Data Transfers, addressing, and arithmetic

## Operand Types

* **Immediate** – a constant integer (8, 16, or 32 bits)
  * value is encoded within the instruction
* **Register** – the name of a register
  * register name is converted to a number and encoded within the instruction
* **Memory** – reference to a location in memory
  * memory address is encoded within the instruction, or a register holds the address of a memory location

### Instruction Operand Notation

![image-20220211083457978](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220211083457978.png)

### Direct Memory Operands

* A direct memory operand is a **named reference** to storage in memory
* The named reference (**label**) is automatically **dereferenced** by the assembler

```assembly
.data
var1 BYTE 10h
.code
mov al,var1		; AL = 10h
mov al,[var1]	; alternate format, AL = 10h
```

### MOV Instruction

* Move from source to destination. Syntax:

  ```assembly
  ; MOV destination,source
  ```

* No more than **one memory** operand permitted

* **CS**, **EIP**, and **IP** cannot be the destination

* No **immediate** to segment reg moves

* Both operands must be the **same** size.

```assembly
; MOV reg,reg
; MOV mem,reg
; MOV reg,mem
; MOV mem,imm
; MOV reg,imm

.data
count BYTE 100
wVal  WORD 2
.code
	mov bl,count
	mov ax,wVal
	mov count,al
```

The following code are incorrect:

```assembly
.data
bVal  BYTE   100
bVal2 BYTE   ?
wVal  WORD   2
dVal  DWORD  5
.code
	mov ds,45		; immediate move to DS not permitted
	mov esi,wVal	; size mismatch
	mov eip,dVal	; EIP cannot be the destination
	mov 25,bVal		; immediate value cannot be destination
	mov bVal2,bVal	; memory-to-memory move not permitted
```

### Zero Extension

> When you copy a **smaller** value into a **larger** destination, the **MOVZX** instruction fills (extends) the upper half of the destination with **zeros**.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211084806343.png" alt="image-20220211084806343" style="zoom:67%;" />

```assembly
.data
val BYTE 10001111b

.code
movzx ax, val 
```

* The destination must be a **register**.
* The source **cannot** be **immediate**.

### Sign Extension

> The **MOVSX** instruction fills the upper half of the destination with a copy of the source operand's sign bit.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211084823553.png" alt="image-20220211084823553" style="zoom:67%;" />

```assembly
mov bl,10001111b
movsx ax, bl
```

​    The destination must be a **register**.
​    The source **cannot** be **immediate**.

### XCHG Instruction

> **XCHG** exchanges the values of two **operands**. At least one operand must be a **register**. **No immediate** operands are permitted.

```assembly
.data
var1 WORD 1000h
var2 WORD 2000h
.code
xchg ax,bx		; exchange 16-bit regs
xchg ah,al		; exchange 8-bit regs
xchg var1,bx	; exchange mem, reg
xchg eax,ebx	; exchange 32-bit regs

xchg var1,var2	; error: two memory operands
```

### Direct-Offset Operands

> A **constant offset** is added to a **data label** to produce an effective address (**EA**). The address is **dereferenced** to get the value inside its **memory** location.

```assembly
.data
arrayB BYTE 10h,20h,30h,40h
.code
mov al,arrayB+1			; AL = 20h
mov al,[arrayB+1]		; alternative notation
```

A **constant** offset is added to a data label to produce an effective address (EA). The address is dereferenced to get the value inside its memory location.

```assembly
.data
arrayW  WORD 1000h,2000h,3000h	; word has 2 byte
arrayD  DWORD 1,2,3,4			; dword has 4 byte
.code
mov ax,[arrayW+2]		; AX = 2000h
mov ax,[arrayW+4]		; AX = 3000h
mov eax,[arrayD+4]		; EAX = 00000002h

; Will the following statements assemble?
mov ax,[arrayW-2]		; 
mov eax,[arrayD+16]		; the assembler just retrieves a byte of memory outside the array.
```

Write a program that rearranges the values of three doubleword  values in the following array as: 3, 1, 2.

```assembly
.data
arrayD DWORD 1,2,3
```

* Step1: copy the first value into EAX and exchange it with the value in the second position.

```assembly
mov eax,arrayD			; 1 => eax
xchg eax,[arrayD+4]		; 1, 1, 3    eax=2
```

* Step 2: Exchange EAX with the third array value and copy the value in EAX to the first array position.

```assembly
xchg eax,[arrayD+8]		; 1, 1, 2    eax=3
mov arrayD,eax			; eax => arrayD
```

#### Evaluate this . . .

* We want to write a program that adds the following three bytes:

  ```assembly
  .data
  myBytes BYTE 80h,66h,0A5h
  ```

* What is your evaluation of the following code?

  ```assembly
  mov al,myBytes
  add al,[myBytes+1]
  add al,[myBytes+2]
  ```

* What is your evaluation of the following code?

  ```assembly
  mov ax,myBytes
  add ax,[myBytes+1]
  add ax,[myBytes+2]
  ```

Another approach:

```assembly
.data
myBytes BYTE 80h,66h,0A5h
```

* How about the following code. Is anything missing?

  ```assembly
  movzx ax,myBytes
  mov   bl,[myBytes+1]
  add   ax,bx
  mov   bl,[myBytes+2]
  add   ax,bx			; AX = sum
  ; Yes: Move zero to BX before the MOVZX instruction.
  ```

### Addition and Subtraction

* INC and DEC Instructions
* ADD and SUB Instructions
* NEG Instruction
* Implementing Arithmetic Expressions
* Flags Affected by Arithmetic
  * Zero
  * Sign
  * Carry
  * Overflow

### INC and DEC Instructions

* Add 1, subtract 1 from destination operand
  * operand may be register or memory
* INC destination
  * Logic: destination <= destination + 1
* DEC destination
  * Logic: destination <= destination – 1

```assembly
.data
myWord  WORD 1000h
myDword DWORD 10000000h
.code
	inc myWord 	; 1001h
	dec myWord	; 1000h
	inc myDword	; 10000001h

	mov ax,00FFh
	inc ax	; AX = 0100h
	mov ax,00FFh
	inc al	; AX = 0000h
```

Show the value of the destination operand after each of the following instructions executes:

```assembly
.data
myByte BYTE 0FFh, 0
.code
	mov al,myByte	; AL = FFh
	mov ah,[myByte+1]	; AH = 00h
	dec ah	; AH = FFh
	inc al	; AL = 00h
	dec ax	; AX = FEFFh
```

### ADD and SUB Instructions

* **ADD** destination, source
  * Logic: destination <= destination + source
* **SUB** destination, source
  * Logic: destination <= destination – source
* Same operand **rules** as for the MOV instruction

```assembly
.data
var1 DWORD 10000h
var2 DWORD 20000h
.code	; ---EAX---
	mov eax,var1	; 00010000h
	add eax,var2 	; 00030000h
	add ax,0FFFFh	; 0003FFFFh
	add eax,1	; 00040000h
	sub ax,1	; 0004FFFFh
```

### NEG (negate) Instruction

**Reverses** the **sign** of an operand. Operand can be a **register** or **memory** operand. (Like converting to its **Two’s Complement**)

```assembly
.data
valB BYTE -1
valW WORD +32767
.code
	mov al,valB	; AL = -1
	neg al	; AL = +1
	neg valW	; valW = -32767
```

### NEG Instruction and the Flags

> The processor implements  NEG using the following internal operation:
>
> ```assembly
> SUB 0,operand
> ```
>
> Any **nonzero** operand causes the **Carry** flag to be set.

```assembly
.data
valB BYTE 1,0
valC SBYTE -128
.code
	neg valB	; CF = 1, OF = 0
	neg [valB + 1]	; CF = 0, OF = 0
	neg valC	; CF = 1, OF = 1
```

### Implementing Arithmetic Expressions

**HLL** compilers **translate** mathematical expressions into **assembly** language. You can do it also. For example: 

```c
Rval = -Xval + (Yval – Zval)
```

```assembly
Rval DWORD ?
Xval DWORD 26
Yval DWORD 30
Zval DWORD 40
.code
	mov eax,Xval		
	neg eax 	; EAX = -26
	mov ebx,Yval
	sub ebx,Zval 	; EBX = -10
	add eax,ebx
	mov Rval,eax 	; -36
```

Translate the following expression into assembly language. Do not permit Xval, Yval, or Zval to be modified: 

```c
Rval = Xval - (-Yval + Zval)
```

Assume that all values are signed doublewords.

```assembly
mov ebx, Yval
neg ebx
add ebx, Zval
mov eax, Xval
sub eax, ebx
mov Rval, eax
```

### Flags Affected by Arithmetic

* The ALU has a number of **status** flags that reflect the outcome of arithmetic (and bitwise) operations
  * based on the contents of the **destination** operand
* Essential flags:
  * Zero flag – set when **destination** equals **zero**
  * Sign flag – set when destination is **negative**
  * Carry flag – set when **unsigned** value is **out** of range
  * Overflow flag – set when **signed** value is **out** of range
* The **MOV instruction never affects the flags**.

## Concept Map

![image-20220211092026355](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220211092026355.png)

You can use diagrams such as these to express the relationships between assembly language concepts.

### Zero Flag (ZF)

> The Zero flag is set when the result of an operation produces **zero** in the **destination** operand.  

```assembly
mov cx,1
sub cx,1 	; CX = 0, ZF = 1
mov ax,0FFFFh
inc ax 	; AX = 0, ZF = 1
inc ax 	; AX = 1, ZF = 0
```

Remember...

* A flag is **set** when it equals 1. 
* A flag is **clear** when it equals 0.

### Sign Flag (SF)

> The Sign flag is set when the **destination** operand is **negative**. The flag is clear when the destination is positive. 

```assembly
mov cx,0
sub cx,1 	; CX = -1, SF = 1
add cx,2 	; CX = 1, SF = 0
```

The sign flag is a copy of the destination's highest bit:

```assembly
mov al,0
sub al,1            ; AL = 11111111b, SF = 1
add al,2            ; AL = 00000001b, SF = 0
```

### Overflow and Carry Flags: A Hardware Viewpoint

>  MSB = Most Significant Bit (high-order bit)
>  XOR = eXclusive-OR operation
>  NEG = Negate (same as SUB  0,operand )

* How the ADD instruction affects OF and CF:
  * CF  = (carry out of the MSB)
  * OF  = (carry out of the MSB) XOR (carry into the MSB)           
* How the SUB instruction affects OF and CF:
  * CF  = INVERT (carry out of the MSB) 
  * When a larger unsigned integer is subtracted from a smaller one
  * negate the source and add it to the destination
  * OF  = (carry out of the MSB) XOR (carry into the MSB) 

### Carry Flag (CF)

> The Carry flag is set when the **result** of an operation generates an **unsigned** value that is out of range (too **big** or too **small** for the destination operand).

```assembly
mov al,0FFh
add al,1	; CF = 1, AL = 00

; Try to go below zero:

mov al,0
sub al,1	; CF = 1, AL = FF
```

How about this, Why? 				

```assembly
mov al,2
sub al,1	; CF = 0, AL = 1
```

For each of the following marked entries, show the values of the destination operand and the Sign, Zero, and Carry flags:

```assembly
mov ax,00FFh
add ax,1	; AX= 0100h SF=0 ZF=0 CF=0
sub ax,1	; AX= 00FFh SF=0 ZF=0 CF=0
add al,1	; AL= 00h   SF=0 ZF=1 CF=1
mov bh,6Ch
add bh,95h	; BH= 01h   SF=0 ZF=0 CF=1

mov al,2
sub al,3	; AL= FFh   SF=1 ZF=0 CF=1
```

### Overflow Flag (OF)

> The Overflow flag is **set** when the signed result of an operation is **invalid** or **out** of range.

```assembly
; Example 1
mov al,+127
add al,1	; OF = 1,   AL = ??

; Example 2
mov al,7Fh	; OF = 1,   AL = 80h
add al,1
```

> The two examples are identical at the binary level because 7Fh equals +127. To determine the value of the destination operand, it is often easier to calculate in hexadecimal.

### A Rule of Thumb

When adding two integers, remember that the Overflow flag is only set when . . .

* Two positive operands are added and their sum is negative
* Two negative operands are added and their sum is positive
* Overflow never occurs when the signs of two addition operands are different.

What will be the values of the Overflow flag?

```assembly
mov al,80h
add al,92h	; OF = 1, AL=02

mov al,-2
add al,+127	; OF = 0
; Notice: -2 is 1111 1110 (254)
```

What will be the values of the given flags after each operation?

```assembly
mov ax,8000h
add ax,2	; CF =0	OF =0

mov ax,0
sub ax,2	; CF =1	OF =0

mov al,-5
sub al,+125	; CF =0	OF =1 AL =7E
```

## Data-Related Operators and Directives

* OFFSET Operator
* PTR Operator
* TYPE Operator
* LENGTHOF Operator
* SIZEOF Operator
* LABEL Directive

### OFFSET Operator

> **OFFSET** returns the distance in **bytes**, of a **label** from the **beginning** of its **enclosing** segment
>
> * Protected mode: 32 bits
> * Real mode: 16 bits
>
> <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211093920726.png" alt="image-20220211093920726" style="zoom:50%;" />
>
> The Protected-mode programs we write use only a single segment (flat memory model).

#### OFFSET Examples

Let's assume that the data segment begins at 00404000h:

```assembly
.data
bVal BYTE ?
wVal WORD ?
dVal DWORD ?
dVal2 DWORD ?

.code
mov esi,OFFSET bVal 	; ESI = 00404000
mov esi,OFFSET wVal 	; ESI = 00404001
mov esi,OFFSET dVal 	; ESI = 00404003
mov esi,OFFSET dVal2	; ESI = 00404007
```

#### Relating to C/C++

> The value returned by **OFFSET** is a **pointer**. Compare the following code written for both C++ and assembly language:

```c
// C++ version:

char array[1000];
char * p = array;
```

```assembly
; Assembly language:

.data
array BYTE 1000 DUP(?)
.code
mov	 esi,OFFSET array
```

### ALIGN Directive

* Aligns a **variable** on a **byte**, **word**, **dword**, or **paragraph** boundary
* Padding to 1, ,2, 4, or 16 bytes in data segments 
* The CPU can process data stored at even numbered addresses more quickly than those at odd-numbered addresses.

```assembly
.data
	bVal	BYTE 10h	; 0000 0000
	ALIGN 2
	wVal	WORD 20h	; 0000 0002
	bVal2	BYTE 30h	; 0000 0004
	ALIGN 4
	dVal	DWORD 50h	; 0000 0008
	bVal3	BYTE  60h	; 0000 000C
	ALIGN 4
	dVal2	DWORD 70h	; 0000 0010
```

### PTR Operator

> **Overrides** the default **type** of a label (variable). Provides the **flexibility** to access **part** of a variable.

```assembly
.data
myDouble DWORD 12345678h
.code
; mov ax,myDouble 			; error – why?

mov ax,WORD PTR myDouble			; loads 5678h

mov WORD PTR myDouble,4321h		; saves 4321h
mov EBX, myDouble
; What is myDouble now? 
```

Little endian order is used when storing data in memory 12344321h (memory 21 43 34 12)

#### Little Endian Order

* Little endian order refers to the **way** Intel stores **integers** in **memory**.
* Multi-byte integers are stored in reverse order, with the **least** significant byte stored at the **lowest** address
* For example, the doubleword 12345678h would be stored as:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211094513326.png" alt="image-20220211094513326" style="zoom:67%;" />

When integers are loaded from memory into registers, the bytes are automatically **re-reversed** into their correct positions.

#### PTR Operator Examples

```assembly
.data
myDouble DWORD 12345678h
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211094609533.png" alt="image-20220211094609533" style="zoom:50%;" />

```assembly
mov al,BYTE PTR  myDouble			; AL = 78h
mov al,BYTE PTR [myDouble+1]		; AL = 56h
mov al,BYTE PTR [myDouble+2]		; AL = 34h
mov ax,WORD PTR  myDouble			; AX = 5678h
mov ax,WORD PTR [myDouble+2]		; AX = 1234h
```

> PTR can also be used to **combine elements** of a **smaller** data type and **move** them into a **larger** operand. The CPU will automatically **reverse** the bytes.

```assembly
.data
myBytes BYTE 12h,34h,56h,78h

.code
mov ax,WORD PTR [myBytes]		; AX = 3412h
mov ax,WORD PTR [myBytes+2]		; AX = 7856h
mov eax,DWORD PTR myBytes		; EAX = 78563412h
```

Write down the value of each destination operand:

```assembly
.data
varB BYTE 65h,31h,02h,05h
varW WORD 6543h,1202h
varD DWORD 12345678h

.code
mov ax,WORD PTR [varB+2]	; a. 0502h
mov bl,BYTE PTR varD		; b. 78h
mov bl,BYTE PTR [varW+2]	; c. 02h
mov ax,WORD PTR [varD+2]	; d. 1234h
mov eax,DWORD PTR varW		; e. 12026543h
mov ax, word ptr varD+1		; f. 3456h
```

### TYPE Operator

> The **TYPE** operator **returns** the **size**, in **bytes**, of a single **element** of a data declaration.

```assembly
.data
var1 BYTE ?
var2 WORD ?
var3 DWORD ?
var4 QWORD ?

.code
mov eax,TYPE var1	; 1
mov eax,TYPE var2	; 2
mov eax,TYPE var3	; 4
mov eax,TYPE var4	; 8
```

### LENGTHOF Operator

> The **LENGTHOF** operator **counts** the number of **elements** in a single data declaration.

```assembly
.data	LENGTHOF
byte1  BYTE 10,20,30		; 3
array1 WORD 30 DUP(?),0,0	; 32
array2 WORD 5 DUP(3 DUP(?))	; 15
array3 DWORD 1,2,3,4		; 4
digitStr BYTE "12345678",0	; 9

.code
mov ecx,LENGTHOF array1	; 32
```

### SIZEOF Operator

> The **SIZEOF** operator **returns** a value that is equivalent to multiplying **LENGTHOF** by **TYPE**.

```assembly
.data							;SIZEOF
byte1  BYTE 10,20,30		 	; 3
array1 WORD 30 DUP(?),0,0		; 64
array2 WORD 5 DUP(3 DUP(?))		; 30
array3 DWORD 1,2,3,4			; 16
digitStr BYTE "12345678",0		; 9

.code
mov ecx,SIZEOF array1			; 64
```

### Spanning Multiple Lines

> A data declaration **spans multiple** lines if each line (except the last) ends with a **comma**. The LENGTHOF and SIZEOF operators include all lines belonging to the **declaration**:

```assembly
.data
array WORD 10,20,
	30,40,
	50,60

.code
mov eax,LENGTHOF array	; 6
mov ebx,SIZEOF array	; 12
```

In the following example, array identifies only the first WORD declaration. Compare the values returned by LENGTHOF and SIZEOF here to those in the previous slide:

```assembly
.data
array	WORD 10,20
	WORD 30,40
	WORD 50,60

.code
mov eax,LENGTHOF array	; 2
mov ebx,SIZEOF array	; 4
```

### LABEL Directive

* Assigns an alternate label name and type to an existing storage location
* LABEL does not allocate any storage of its own
* Removes the need for the PTR operator

```assembly
.data
dwList   LABEL DWORD
wordList LABEL WORD
intList  BYTE 00h,10h,00h,20h
.code
mov eax,dwList	; 20001000h
mov cx,wordList	; 1000h
mov dl,intList	; 00h
```

```assembly
.data
v16 label word
v32 DWORD 12345678h
.code
mov ax, v16		; ax = 5678h
mov dx, v16 +2 	; dx = 1234h

.data
val label dword
v1 WORD 5678h
v2 WORD 1234h
.code
mov eax, val	; eax = 12345678h
```

## Indirect Addressing

* Indirect Operands
* Array Sum Example
* Indexed Operands
* Pointers

### Indirect Operands

* Indirect operand can be any **32-bit general-purpose** register (EAX, EBX, ECX, EDX, ESI, EDI, EBP, and ESP) surrounded by **brackets**
* An indirect operand **holds** the **address** of a variable, usually an **array** or **string**. It can be dereferenced (just like a **pointer**).

```assembly
.data
val1 BYTE 10h,20h,30h
.code
mov esi,OFFSET val1
mov al,[esi]	; dereference ESI (AL = 10h)

inc esi
mov al,[esi]	; AL = 20h

inc esi
mov al,[esi]	; AL = 30h
```

* Use PTR to clarify the size attribute of a memory operand.
* The assembler does not know whether ESI points to a byte, word, doubleword, or some other size. 

```assembly
.data
myCount WORD 0

.code
mov esi,OFFSET myCount
inc [esi]	; error: ambiguous
inc WORD PTR [esi]	; ok
```

Should PTR be used here? 

```assembly
add [esi],20
```

yes, because [esi] could point to a byte, word, or doubleword

### Array Sum Example

> **Indirect operands** are ideal for **traversing** an array. Note that the register in brackets must be **incremented** by a value that **matches** the array type.

```assembly
.data
arrayW WORD 1000h,2000h,3000h
.code
mov esi,OFFSET arrayW
mov ax,[esi]
add esi,2	; or: add esi,TYPE arrayW
add ax,[esi]
add esi,2
add ax,[esi]	; AX = sum of the array
```

### Indexed Operands

An indexed operand adds a constant to a register to generate an effective address. There are two notational forms:

```assembly
;[label + reg]			label[reg]
```

```assembly
.data
arrayW WORD 1000h,2000h,3000h
.code
	mov esi,0
	mov ax,[arrayW + esi] 		; AX = 1000h
	mov ax,arrayW[esi]		; alternate format
	add esi,2
	add ax,[arrayW + esi]
	;etc.
```

### Index Scaling

> You can **scale** an indirect or indexed operand to the **offset** of an array element. This is done by multiplying the index by the array's **TYPE**: 

```assembly
.data
arrayB BYTE  0,1,2,3,4,5
arrayW WORD  0,1,2,3,4,5
arrayD DWORD 0,1,2,3,4,5

.code
mov esi,4
mov al,arrayB[esi*TYPE arrayB]		; 04
mov bx,arrayW[esi*TYPE arrayW]		; 0004
mov edx,arrayD[esi*TYPE arrayD]		; 00000004
```

### Pointers

> You can **declare** a pointer variable that contains the **offset** of another **variable**.

```assembly
.data
arrayW WORD 1000h,2000h,3000h
ptrW DWORD arrayW
.code
	mov esi,ptrW
	mov ax,[esi]	; AX = 1000h
```

Alternate format:

```assembly
ptrW DWORD OFFSET arrayW
```

### TYPEDEF

> lets you **create** a **user-defined** type that has all the **status** of a **built-in** type when defining variables

```assembly
PBYTE TYPEDEF PTR BYTE   		; PBYTE is a pointer to bytes
.data
ArrayB BYTE 10, 20, 30, 40, 50 
P1 PBYTE ?
P2 PBYTE ArrayB 
```

## JMP and LOOP Instructions

* JMP Instruction
* LOOP Instruction
* LOOP Example
* Summing an Integer Array
* Copying a String

### JMP Instruction

* JMP is an **unconditional** jump to a **label** that is usually within the  same **procedure**.

* Syntax: JMP target

* Logic: EIP <= target

* Example:

  ```assembly
  top:
  	.
  	.
  	jmp top
  ```

  A jump outside the current procedure must be to a special type of label called a **global label** (see Section 5.5.2.3 for details).

### LOOP Instruction

* The LOOP instruction creates a **counting** loop
* Syntax: LOOP target
* Logic:
  * ECX => ECX – 1
  * if ECX != 0, jump to target
* Implementation: 
* The assembler calculates the **distance**, in **bytes**, between the **offset** of the following instruction and the offset of the target label. It is called the relative offset.
* The relative offset is added to **EIP**.

### LOOP Example

The following loop calculates the sum of the integers 5 + 4 + 3 +2 + 1:

```assembly
00000000  66 B8 0000		mov  ax,0  
00000004  B9 00000005		mov  ecx,5

00000009  66 03 C1	L1:	add  ax,cx
0000000C  E2 FB		loop L1
0000000E
```

> When LOOP is assembled, the current location = 0000000E (offset of the next instruction).  –5 (FBh) is added to the the current location, causing a jump to location 00000009:
> 	00000009 <= 0000000E + FB

What will be the final value of AX?

```assembly
	mov ax,6
	mov ecx,4
L1:
	inc ax
	loop L1
```

Answer: 10

### Nested Loop

> If you need to code a **loop within a loop**, you must save the **outer** loop counter's ECX value. In the following example, the outer loop executes 100 times, and the inner loop 20 times.

```assembly
.data
count DWORD ?
.code
	mov ecx,100	; set outer loop count
L1:
	mov count,ecx	; save outer loop count
	mov ecx,20	; set inner loop count
L2:	.
.
loop L2	; repeat the inner loop
	mov ecx,count	; restore outer loop count
	loop L1	; repeat the outer loop
```

### Summing an Integer Array

The following code calculates the sum of an array of 16-bit integers.

```assembly
.data
intarray WORD 100h,200h,300h,400h
.code
	mov edi,OFFSET intarray	; address of intarray
	mov ecx,LENGTHOF intarray	; loop counter
	mov ax,0	; zero the accumulator
L1:
	add ax,[edi]	; add an integer
	add edi,TYPE intarray	; point to next integer
	loop L1	; repeat until ECX = 0
```

### Copying a String

The following code copies a string from source to target:

```assembly
.data
source  BYTE  "This is the source string",0
target  BYTE  SIZEOF source DUP(0)

.code
	mov  esi,0					; index register
	mov  ecx,SIZEOF source		; loop counter
L1:
	mov  al,source[esi]			; get char from source
	mov  target[esi],al			; store it in the target
	inc  esi					; move to next character
	loop L1						; repeat for entire string
```

### 64-Bit Programming

* **MOV** instruction in 64-bit mode **accepts** operands of 8, 16, 32, or **64** bits
* When you move a 8, 16, or 32-bit constant to a 64-bit register, the **upper** bits of the destination are **cleared**.
* When you move a memory operand into a 64-bit register, the results vary:
  * **32-bit** move **clears** high bits in destination
  * **8-bit** or 16-bit move **does not** affect high bits in destination
* **MOVSXD** sign **extends** a 32-bit value into a 64-bit destination register
* The **OFFSET** operator generates a **64-bit** address
* **LOOP** uses the 64-bit **RCX** register as a counter
* **RSI** and **RDI** are the most common **64-bit index** registers for **accessing** arrays.
* **ADD** and **SUB** affect the **flags** in the same way as in **32-bit** mode
* You can use **scale** factors with indexed operands.

## Summary

* Data Transfer
  * **MOV** – data transfer from source to destination
  * **MOVSX**, **MOVZX**, **XCHG**
* Operand types
  * direct, direct-offset, indirect, indexed
* Arithmetic
  * INC, DEC, ADD, SUB, NEG
  * Sign, Carry, Zero, Overflow flags
* Operators
  * OFFSET, PTR, TYPE, LENGTHOF, SIZEOF, TYPEDEF
* **JMP** and **LOOP** – branching instructions

# Procedures

## Overview

* Stack Operations
* Defining and Using Procedures
* Linking to an External Library
* The Irvine32 Library
* Program Design Using Procedures
* 64-Bit Assembly Programming

## Stack Operations

* Runtime Stack
* PUSH Operation
* POP Operation
* PUSH and POP Instructions
* Using PUSH and POP
* Example: Reversing a String
* Related Instructions

### Runtime Stack

* Imagine a stack of plates . . .

  * plates are only added to the top

  * plates are only removed from the top

  * LIFO structure

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218084025442.png" alt="image-20220218084025442" style="zoom:67%;" />

* Managed by the CPU, using two registers

  * SS (stack segment)

  * ESP (stack pointer) (SP in Real-address mode)

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218084448638.png" alt="image-20220218084448638" style="zoom:67%;" />

### PUSH Operation

* A 32-bit **push** operation **decrements** the stack pointer by **4** and **copies** a value into the **location** pointed to by the stack pointer.

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085130180.png" alt="image-20220218085130180" style="zoom:67%;" />

* Same stack after pushing two more integers:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085524268.png" alt="image-20220218085524268" style="zoom:67%;" />

  The stack grows **downward**. The area **below** ESP is always **available** (unless the stack has **overflowed**).

### POP Operation

* Copies **value** at stack[ESP] into a **register** or variable.

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085743561.png" alt="image-20220218085743561" style="zoom:67%;" />

### PUSH and POP Instructions

* PUSH syntax:
  * PUSH r/m16
  * PUSH r/m32
  * PUSH imm32
* POP syntax:
  * POP r/m16
  * POP r/m32

> Irvine32 library always pushes 32-bit value

### Using PUSH and POP

**Save** and **restore** registers when they contain **important** values. PUSH and POP instructions occur in the **opposite** order.

```assembly
INCLUDE Irvine32.inc
.data
array WORD 8,9,10,11,0FFFFh 
.code 
main PROC
	push esi		; push registers, for example esi = 10A230h
	push ecx
	push ebx
	
	mov esi,OFFSET array 		; esi = address of array
	mov ecx,LENGTHOF array ;5 
	mov ebx,TYPE array ;2 
	call DumpMem
	
	pop ebx			; restore registers
	pop ecx
	pop esi			; esi = 10A230h
main ENDP
```

#### DumpMem PROC

> Writes a range of memory to standard output in hexadecimal.
> Call arguments: 
> ESI = starting offset
> ECX = number of units
> EBX = bytes/unit (1,2,or 4) 
> Return argument: None 
> Example: Dump a word array 

```assembly
.data
array WORD 8,9,10,11,0FFFFh 
.code 
mov esi,OFFSET array 
mov ecx,LENGTHOF array ;5 
mov ebx,TYPE array ;2 
call DumpMem

```

### Example: Nested Loop

> When **creating** a nested loop, push the outer loop counter before entering the inner loop:

```assembly
	mov ecx,100	; set outer loop count
L1:		; begin the outer loop
	push ecx	; save outer loop count

	mov ecx,20	; set inner loop count
L2:		; begin the inner loop
	;
	;
	loop L2	; repeat the inner loop

	pop ecx	; restore outer loop count
	loop L1	; repeat the outer loop
```

### Example: Reversing a String

* Use a **loop** with **indexed** addressing

* **Push** each character on the stack

* Start at the beginning of the string, **pop** the stack in **reverse** order, **insert** each character **back** into the **string**

* Source code

  ```assembly
  .data
  aName byte "Abraham Lincoln",0
  nameSize = ($ - aName) - 1
  .code
  main proc
  
  ; Push the name on the stack.
  
  	mov	 ecx,nameSize
  	mov	 esi,0
  
  L1:	movzx eax,aName[esi]	; get character
  	push eax				; push on stack
  	inc	 esi
  	loop L1
  
  ; Pop the name from the stack in reverse
  ; and store it in the aName array.
  
  mov	 ecx,nameSize
  	mov	 esi,0
  
  L2:	pop  eax				; get character
  	mov	 aName[esi],al		; store in string
  	inc	 esi
  	loop L2
  
  	Invoke ExitProcess,0
  main endp
  ```

  

* Q: Why must each character be put in EAX before it is pushed?

  > Because only word (16-bit) or doubleword (32-bit) values can be pushed on the stack.

### Related Instructions

* PUSHFD and POPFD
  * push and pop the EFLAGS register
* PUSHAD pushes the 32-bit general-purpose registers on the stack 
  * order: EAX, ECX, EDX, EBX, ESP, EBP, ESI, EDI
* POPAD pops the same registers off the stack in reverse order
  * PUSHA and POPA do the same for 16-bit registers

#### PUSHFD and POPFD

* Usually we want to:

  ```assembly
  pushfd
  ;
  ; do something
  ;
  popfd
  ```

  * But problems are…
    * Skip out?
    * Unpaired ops?

* Less error-prone?

```assembly
.data
savedFlags DWORD ?
.code
pushfd
pop savedFlags 
;
; do something
;
push savedFlags 
popfd
```

## Defining and Using Procedures

* Creating Procedures
* Documenting Procedures
* Example: SumOf Procedure
* CALL and RET Instructions
* Nested Procedure Calls
* Local and Global Labels
* Procedure Parameters
* Flowchart Symbols
* USES Operator

### Creating Procedures

* **Large problems** can be **divided** into smaller tasks to make them more **manageable**

* A ***procedure*** is the ASM **equivalent** of a Java or C++ **function**

* Following is an assembly language procedure named **sample**:

  ```assembly
  sample PROC
  .
  .
  ret
  sample ENDP
  ```

### Documenting Procedures

> Suggested **documentation** for each procedure:

* A **description** of all **tasks** accomplished by the procedure.
* **Receives**: A list of **input** parameters; **state** their usage and **requirements**.
* **Returns**: A **description** of values returned by the procedure.
* **Requires**: Optional list of requirements called **preconditions** that must be **satisfied before** the procedure is called.

> If a procedure is called **without** its preconditions **satisfied**, it will  probably not produce the expected **output**.

### Example: SumOf Procedure

```assembly
;---------------------------------------------------------
SumOf PROC
;
; Calculates and returns the sum of three 32-bit integers.
; Receives: EAX, EBX, ECX, the three integers. May be
; signed or unsigned.
; Returns: EAX = sum, and the status flags (Carry,
; Overflow, etc.) are changed.
; Requires: nothing
;---------------------------------------------------------
add eax,ebx
add eax,ecx
ret
SumOf ENDP
```

To call SumOf, prepare arguments: EAX, EBX, ECX

```assembly
mov eax,10
mov ebx,20
mov ecx,30
call SumOf
WriteDec
```

### CALL and RET Instructions

* The **CALL** instruction calls a procedure 
  * **pushes** offset of next instruction on the stack
  * **copies** the address of the called procedure into **EIP**
* The **RET** instruction **returns** from a **procedure**
  * **pops** top of stack into **EIP**

#### Call-Ret Example

```assembly
main PROC
00000020 call MySub
00000025 mov eax,ebx
; 0000025 is the offset of the 
; instruction immediately 
; following the CALL
; instruction
.
.
main ENDP

MySub PROC
00000040 mov eax,edx
; 00000040 is the offset of 
; the first instruction inside
; MySub
.
.
ret
MySub ENDP
```

> The CALL instruction pushes 00000025 onto the stack, and loads 00000040 into EIP

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093546511.png" alt="image-20220218093546511" style="zoom:67%;" />

> The RET instruction pops 00000025 from the stack into EIP
>
> (stack shown before RET executes)

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093612440.png" alt="image-20220218093612440" style="zoom:67%;" />

### Nested Procedure Calls

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093648736.png" alt="image-20220218093648736" style="zoom:67%;" />

> By the time Sub3 is called, the stack contains all three return addresses:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093713901.png" alt="image-20220218093713901" style="zoom:67%;" />

### Local and Global Labels

A **local label** is **visible** only to statements **inside** the same **procedure**. A **global** label is visible **everywhere**.

```assembly
main PROC
	jmp L2	; error
L1::	; global label
	exit
main ENDP

sub2 PROC
L2:		; local label
	jmp L1	; ok
	ret
sub2 ENDP
```

### Procedure Parameters

* A good procedure might be **usable** in many **different** programs
  * but **not** if it refers to **specific** variable names
* **Parameters** help to make procedures **flexible** because **parameter** values can **change** at runtime

> The **ArraySum** procedure calculates the sum of an array. It makes two references to specific variable names:

```assembly
ArraySum PROC
	mov esi,0				; array index
	mov eax,0				; set the sum to zero
	mov ecx,LENGTHOF myarray  ; set number of elements

L1:	add eax,myArray[esi]	; add each integer to sum
	add esi,4				; point to next integer
	loop L1					; repeat for array size

	mov theSum,eax			; store the sum
	ret
ArraySum ENDP
```

This version of ArraySum returns the sum of any doubleword  array whose address is in ESI. The sum is returned in EAX:

```assembly
ArraySum PROC
; Receives: ESI points to an array of doublewords, 
;           ECX = number of array elements.
; Returns:  EAX = sum
;-----------------------------------------------------
	mov eax,0		; set the sum to zero

L1:	add eax,[esi]	; add each integer to sum
	add esi,4		; point to next integer
	loop L1			; repeat for array size

	ret
ArraySum ENDP
```

### USES Operator

* **Lists** the **registers** that will be **preserved** 

  ```assembly
  ArraySum PROC USES esi ecx
  	mov eax,0	; set the sum to zero
  	;etc.
  ```

  MASM generates the code shown in **gray**:

  ```assembly
  ArraySum PROC
  	push esi
  	push ecx
  	;.
  	;do something
  	;.
  	pop ecx
  	pop esi
  	ret
  ArraySum ENDP
  ```

### When Not To Push A Register

The sum of the **three registers** is stored in **EAX** on line (3), but the POP instruction replaces it with the starting value of **EAX** on line (4):

```assembly
SumOf PROC		; sum of three integers
    push eax	; 1
    add eax,ebx	; 2
    add eax,ecx	; 3
    pop eax		; 4
    ret
SumOf ENDP
```

## Linking to an External Library

* What is a Link Library?
* How the Linker Works

### What is a Link Library?

* A **file** containing **procedures** that have been **compiled** into **machine** code
  * **constructed** from one or more **OBJ** files
* To build a library, . . .
  * start with one or more **ASM** source **files**
  * assemble each into an **OBJ** file
  * create an **empty** library file (extension .LIB)
  * add the OBJ file(s) to the library file, using the Microsoft **LIB utility**

> Take a quick look at Irvine32.asm in the \Irvine\Examples\Lib32 folder.

### How the Linker Works

* Your programs **link** to **Irvine32.lib** using the **linker** command inside a **batch** file named **make32.bat**.

* Notice the two LIB files: Irvine32.lib, and kernel32.lib

  * the latter is part of the Microsoft **Win32 *Software Development Kit*** (SDK)

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218094803035.png" alt="image-20220218094803035" style="zoom:67%;" />

## The Irvine32 Library

### Calling Irvine32 Library Procedures

* **Call** each **procedure** using the **CALL** instruction. Some procedures require **input** arguments. The **INCLUDE** directive copies in the **procedure** prototypes (declarations).
* The following example displays "1234" on the console:

```assembly
INCLUDE Irvine32.inc
.code
	mov  eax,1234h	; input argument
	call WriteHex	; show hex number
	call Crlf		; end of line
```

### Irvine Library Help

* A Windows help file showing:
  * Irvine Library Procedures
    * Procedure Purpose
    * Calling & Return  Arguments
    * Example of usage
* Directly look up procedures
  * examples\Lib32\Irvine32.asm

### Example 1

* Clear the screen, delay the program for 500 milliseconds, and dump the registers and flags.

```assembly
.code
	call Clrscr   ; Clears console, locates cursor at upper left corner

	mov  eax,500
	call Delay   ; Pauses program execution for n millisecond interval
	call DumpRegs
```

Sample output:

```output
EAX=00000613 EBX=00000000 ECX=000000FF EDX=00000000
ESI=00000000 EDI=00000100 EBP=0000091E ESP=000000F6
EIP=00401026 EFL=00000286 CF=0 SF=1 ZF=0 OF=0
```

### Example 2

* Display a null-terminated string and move the cursor to the beginning of the next screen line.

```assembly
.data
str1 BYTE "Assembly language is easy!",0

.code
	mov  edx,OFFSET str1
	call WriteString ; Writes null-terminated string to console window
	call Crlf; Writes end of line sequence to standard output
```

* Display a null-terminated string and move the cursor to the beginning of the next screen line (use embedded CR/LF)

```assembly
.data
str1 BYTE "Assembly language is easy!",0Dh,0Ah,0

.code
	mov  edx,OFFSET str1
	call WriteString
```

### Example 3

* Display an unsigned integer in binary, decimal, and hexadecimal, each on a separate line.

```assembly
IntVal = 35	
.code
	mov  eax,IntVal
	call WriteBin	; display binary
	call Crlf
	call WriteDec	; display decimal
	call Crlf
	call WriteHex	; display hexadecimal
	call Crlf
```

Sample output:

```output
0000 0000 0000 0000 0000 0000 0010 0011
35
23
```

### Example 4

* Input a string from the user. EDX points to the string and ECX specifies the maximum number of characters the user is permitted to enter.

```assembly
.data
fileName BYTE 80 DUP(0)

.code
	mov  edx,OFFSET fileName
	mov  ecx,SIZEOF fileName – 1
	call ReadString ; Reads string from stdin, terminated by [Enter]
```

> A null byte is automatically appended to the string.

### Example 5

* Generate and display ten pseudorandom signed integers in the range 0 – 99. Pass each integer to WriteInt in EAX and display it on a separate line.

```assembly
.code
	mov ecx,10			; loop counter

L1:	mov  eax,100		; ceiling value
	call RandomRange	; generate random int
	call WriteInt		; display signed int
	call Crlf			; goto next display line
	loop L1				; repeat loop
```

### Example 6

* Display a null-terminated string with yellow characters on a blue background. 				

```assembly
.data
str1 BYTE "Color output is easy!",0

.code
	mov  eax,yellow + (blue * 16)
	call SetTextColor
	mov  edx,OFFSET str1
	call WriteString
	call Crlf
```

> The background color is multiplied by 16 before being added to the foreground color.

## Program Design Using Procedures

* Top-Down Design (**functional decomposition**) involves the following:
  * **design** your program **before** starting to code
  * **break** large **tasks** into **smaller** ones
  * use a **hierarchical** structure based on **procedure** calls
  * test **individual** procedures **separately**

### Integer Summation Program

**Description**: Write a program that prompts the user for multiple 32-bit integers, stores them in an array, calculates the sum of the array, and displays the sum on the screen.

Main steps:

* **Prompt** user for **multiple** integers
* **Calculate** the **sum** of the **array**
* **Display** the sum

```assembly
Main
	Clrscr				; clear screen
	PromptForIntegers
		WriteString		; display string
		ReadInt 		; input integer
	ArraySum 			; sum the integers
	DisplaySum
		WriteString		; display string
		WriteInt		; display integer
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218100603177.png" alt="image-20220218100603177" style="zoom:67%;" />

(gray indicates library procedure)

### Random Integer: TestLib2.asm

* Random32
* RandomRange

### Performance Timing: TestLib3.asm

* Calculate the elapsed time of execution
* Design procedures 
* Use push and pop to access the loop counter
* Control the display position by calling Gotoxy

## 64-Bit Assembly Programming

* The Irvine64 Library
* Calling 64-Bit Subroutines
* The x64 Calling Convention

### The Irvine64 Library

* **Crlf**: Writes an end-of-line sequence to the console.
* **Random64**: Generates a 64-bit pseudorandom integer. 
* **Randomize**: Seeds the random number generator with a unique value.
* **ReadInt64**: Reads a 64-bit signed integer from the keyboard.
* **ReadString**: Reads a string from the keyboard. 
* **Str_compare**: Compares two strings in the same way as the CMP instruction.
* **Str_copy**: Copies a source string to a target location. 
* **Str_length**: Returns the length of a null-terminated string in RAX.
* **WriteInt64**: Displays the contents in the RAX register as a 64-bit signed decimal integer.
* **WriteHex64**: Displays the contents of the RAX register as a 64-bit hexadecimal integer.
* **WriteHexB**: Displays the contents of the RAX register as an 8-bit hexadecimal integer .
* **WriteString**: Displays a null-terminated ASCII string. 

### Calling 64-Bit Subroutines

* **Place** the first four **parameters** in **registers**

* Add **PROTO** directives at the top of your program

  * examples:

  ```assembly
  ExitProcess PROTO 	; located in the Windows API
  WriteHex64 PROTO 	; located in the Irvine64 library
  ```

### The x64 Calling Convention

* Must **use** this with the **64-bit** Windows **API**

* **CALl** instruction **subtracts** 8 from RSP

* First four parameters must be **placed** in **RCX, RDX, R8, and R9**

* **Caller** must **allocate** at least **32 bytes** of shadow space on the **stack**

* When calling a **subroutine**, the stack **pointer** must be **aligned** on a **16-byte** boundary.

  > See the CallProc_64.asm example program.

## Summary

* Procedure – **named block of executable code**
* Runtime stack – **LIFO** structure
  * **holds return** addresses, parameters, local variables
  * **PUSH** – add value to stack
  * **POP** – remove value from stack
* Use the **Irvine32** library for all **standard** I/O and data conversion

