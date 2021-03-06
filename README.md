# BIOS-PC
 BIOS PC XT


You may be interested in a history of where this BIOS came from, and
how it arrived in its present form.  A heavily patched,
partially-functionally BIOS (with no copyright statement, or other
visible indication of origin) was supplied with my IBM-PC/xt
compatible 10 mHz motherboard.  In order to get my motherboard to
function correctly, in other words, to work with the parity interrupt
enabled and to operate with the NEC "V20", it was necessary to
disassemble and thoroughly go thru this "anonymous" bios, which was
hinted as supplied by Taiwan, while limping along on a name brand
bios, as supplied on my previous motherboard by a different vendor.
In the course of this disassembly, aided by comparison with the
published IBM-PC/xt listings, it became apparent that the
synchronization on horizontal retrace in the video INT 10h service was
the root cause of the failure to operate with the NEC "V20", and that
correcting it to correspond with logic (as in IBM's bios) caused the
glitch to disappear.  I am unable to account as to why several name
brand BIOS brands (excluding IBM's) had similar glitches - maybe they
they were produced from similar source code, although this seems
unlikely.  In any case, as evidenced by DEBUG, some of these
name-brand BIOS were full of machine-level patches - did the vendor
ever bother to reassemble and optimize the source code.  The code that
I examined was full of recursive INT(errupt) instructions, which did
not to contribute to screaming fast BIOS.  Therefore, the assembly
code was rearranged so as to eliminate some of the unnecessary CALL,
JMP, and especially INT instructions, as the optimization proceeded
with the later releases.  The bios is (c)Anonymous, because there was
no indication of the original authors...

ps: While playing around with my 10 mHz motherboard, I encountered an
    unusual program called HELPME.COM, which ran at a higher pitch
    than normal.  Since this program behaved normally on other (8 mHz)
    turbo motherboards, my curiousity was aroused.  This eventually
    led me to discover that the 10 mHz motherboard was refreshed in
    hardware by channel 1 of the 8253 timer ic, and that this channel
    appeared to be counting down from an unusually fast oscillator.
    Maybe this could cause problems with other programs...
