# Project:    kino


# Toolflags:
CC           = cc
CCflags      = -Otime -c -depend !Depend -throwback -IC: -APCS 3/32bit/fpe3
Linkflags    = -o $@ 

Files        = o.mpeg2dec
Libs         = C:o.Stubs @.^.libmpeg2.o.libmpeg2 @.^.libvo.o.libvo @.^.libaudio.o.libaudio OSLib:o.OSLib32

# Final targets:
kino:    $(Files) $(Libs)
         link $(Linkflags) $(Files) $(Libs)

#Rule patterns:
VPATH        = @ @.^
.SUFFIXES:    .o .c
.c.o:;        $(CC) $(CCFlags) -o $@ $<

# Dynamic dependencies:
o.mpeg2dec: c.mpeg2dec h.config OSLib:h.os OSLib:h.types h.inttypes h.video_out h.mpeg2 h.mm_accel h.mpglib h.soundcode h.timer1
