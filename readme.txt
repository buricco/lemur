I'm trying to write a stripped-down Apple ][+ emulator in 8086 ASM.

I uploaded it to GitHub because it's very broken and I need help.  I think
most of the current problem has to do with the ADC opcode but I've made about
a dozen attempts at it and none of them work quite right.  It's not even
BCD-related since I'm pretty sure Microsoft Basic doesn't even use BCD.

You need a 12K system ROM; the FPBASIC file from earlier versions of the DOS
3.3 System Master will do perfectly (I do most of my testing with it).

HGR is not supported.

Page 2 is not supported.

Sound is not supported.

The CPU is not throttled.

There is no external hardware implemented.

It'll run on an 8086 with MS-DOS 2 and 256K, but why?
