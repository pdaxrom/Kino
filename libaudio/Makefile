# Project:    o.libaudio

# Toolflags:
CC           = cc
CCflags      = -DLAYER2 -DLAYER3 -c -Otime -depend !Depend -throwback -IC: -APCS 3/32bit/fpe3
Linkflags    = -o libaudio

Files        =	o.common o.dct64 o.dct64_2 o.dct64_4 \
		o.decode o.decode_2to1 o.decode_4to1 \
		o.layer1 o.layer2 o.layer3 o.tabinit o.interface \
		o.soundcode
Libs         = C:o.Stubs OSLib:o.OSLib32

# Final targets:
o.libaudio:      $(Files) $(Libs)
              libfile -c o.libaudio $(Files)
#              link $(Linkflags) $(Files) $(Libs)

#Rule patterns:
VPATH        = @ @.^
.SUFFIXES:    .o .c
.c.o:;        $(CC) $(CCFlags) -o $@ $<

# Dynamic dependencies:
o.main: c.main h.mpg123 h.mpglib C:h.kernel h.soundcode OSLib:h.os OSLib:h.types OSLib:h.wimp OSLib:h.osspriteop OSLib:h.font
o.common: c.common h.mpg123
o.dct64: c.dct64 h.mpg123
o.dct64_2: c.dct64_2 h.mpg123
o.dct64_4: c.dct64_4 h.mpg123
o.decode: c.decode h.mpg123
o.decode_2to1: c.decode_2to1 h.mpg123
o.decode_4to1: c.decode_4to1 h.mpg123
o.layer1: c.layer1 h.mpg123
o.layer2: c.layer2 h.mpg123 h.l2tables
o.layer3: c.layer3 h.mpg123 h.mpglib h.huffman
o.tabinit: c.tabinit h.mpg123
o.interface: c.interface h.mpg123 h.mpglib
o.soundcode: c.soundcode OSLib:h.os OSLib:h.types OSLib:h.osmodule OSLib:h.sound h.soundcode
