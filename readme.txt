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

The stock VGA font looks ugly in 40x25 text mode, so in that situation I load
in a replacement.  (To save space this is only half a font.  And I could
probably save even more by making the program double it at runtime.)  It is
not the actual Apple font - doesn't look anything like it - but still fits
better.  I load it in the upper half of font memory; the lower half is left
untouched.  (This allows for a bit of an "impossible" illusion, where the top
24 lines are in the custom font and the status bar is not!)  A modified
version of MouseText is included in the font, which will allow me to implement
that feature in the future along with //e emulation.  (The change, replacing
inverse checkmark with the glyph used to draw the GR screen, is made possible
by the fact that the VGA can invert a glyph in hardware; the Apple hardware
needs to fudge it.)
