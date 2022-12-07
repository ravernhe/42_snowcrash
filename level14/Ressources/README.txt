# We have nothing...

# First idea, time to break getflag ? Lol
# So we tried other thing first but ended up with nothing...(Not cool m8)

# We strings /bin/getflag and find something weird
libc.so.6 # Prog in C
getuid # ?

# This look like our 14 flag ? Or something else like hash or whatever ?
Check flag.Here is your token :
You are root are you that dumb ?
I`fA>_88eEd:=`85h0D8HE>,D
7`4Ci4=^d=J,?>i;6,7d416,7
<>B16\AD<C6,G_<1>^7ci>l4B
B8b:6,3fj7:,;bh>D@>8i:6@D
?4d@:,C>8C60G>8:h:Gb4?l,A
G8H.6,=4k5J0<cd/D@>>B:>:4
H8B8h_20B4J43><8>\ED<;j@3
78H:J4<4<9i_I4k0J^5>B1j`9
bci`mC{)jxkn<"uD~6%g7FK`7
Dc6m~;}f8Cj#xFkel;#&ycfbK
74H9D^3ed7k05445J0E4e;Da4
70hCi,E44Df[A4B/J@3f<=:`D
8_Dw"4#?+3i]q&;p6 gtw88EC
boe]!ai0FB@.:|L6l@A?>qJ}I
g <t61:|4_|!@IF.-62FH&G~DCK/Ekrvvdwz?v|
Nope there is no token here for you sorry. Try again :)

# We take the last one "boe]!ai0FB@.:|L6l@A?>qJ}I" and try to search where it's stored during the execution

> gdb getflag
> b main
> info proc map # See Mapped address spaces

	Start Addr   End Addr       Size     Offset objfile
	 0x8048000  0x804a000     0x2000        0x0 /bin/getflag
	 0x804a000  0x804b000     0x1000     0x1000 /bin/getflag
	 0x804b000  0x804c000     0x1000     0x2000 /bin/getflag
	0xb7e2b000 0xb7e2c000     0x1000        0x0
	0xb7e2c000 0xb7fcf000   0x1a3000        0x0 /lib/i386-linux-gnu/libc-2.15.so
	0xb7fcf000 0xb7fd1000     0x2000   0x1a3000 /lib/i386-linux-gnu/libc-2.15.so
	0xb7fd1000 0xb7fd2000     0x1000   0x1a5000 /lib/i386-linux-gnu/libc-2.15.so
	0xb7fd2000 0xb7fd5000     0x3000        0x0
	0xb7fdb000 0xb7fdd000     0x2000        0x0
	0xb7fdd000 0xb7fde000     0x1000        0x0 [vdso]
	0xb7fde000 0xb7ffe000    0x20000        0x0 /lib/i386-linux-gnu/ld-2.15.so
	0xb7ffe000 0xb7fff000     0x1000    0x1f000 /lib/i386-linux-gnu/ld-2.15.so
	0xb7fff000 0xb8000000     0x1000    0x20000 /lib/i386-linux-gnu/ld-2.15.so
	0xbffdf000 0xc0000000    0x21000        0x0 [stack]
  
 > find 0x8048000,0x804a000,"boe]!ai0FB@.:|L6l@A?>qJ}I" # We try to find our string in memory allocated
 0x8049204
1 pattern found. 🧐

> x /s 0x8049204 # check the content of the memory adress
0x8049204:	 "boe]!ai0FB@.:|L6l@A?>qJ}I"

# NOW we search when it's called during getflag execution
# Exit gdb and magic trick to grep
gdb getflag 2>&1 | tee /tmp/main_disas; grep -A 10 -B 10 0x8049204 /tmp/main_disas
disas main
quit
   0x08048da3 <+1117>:	mov    0x804b060,%eax        # We have a Pattern
   0x08048da8 <+1122>:	mov    %eax,%ebx
   0x08048daa <+1124>:	movl   $0x80491ea,(%esp)
   0x08048db1 <+1131>:	call   0x8048604 <ft_des>
   0x08048db6 <+1136>:	mov    %ebx,0x4(%esp)
   0x08048dba <+1140>:	mov    %eax,(%esp)
   0x08048dbd <+1143>:	call   0x8048530 <fputs@plt>
   0x08048dc2 <+1148>:	jmp    0x8048e2f <main+1257>
   0x08048dc4 <+1150>:	mov    0x804b060,%eax        # We have a Pattern
   0x08048dc9 <+1155>:	mov    %eax,%ebx
   0x08048dcb <+1157>:	movl   $0x8049204,(%esp)
   0x08048dd2 <+1164>:	call   0x8048604 <ft_des>
   0x08048dd7 <+1169>:	mov    %ebx,0x4(%esp)
   0x08048ddb <+1173>:	mov    %eax,(%esp)
   0x08048dde <+1176>:	call   0x8048530 <fputs@plt>
   0x08048de3 <+1181>:	jmp    0x8048e2f <main+1257>
   0x08048de5 <+1183>:	mov    0x804b060,%eax        # We have a Pattern (We double check)
   0x08048dea <+1188>:	mov    %eax,%ebx
   0x08048dec <+1190>:	movl   $0x8049220,(%esp)
   0x08048df3 <+1197>:	call   0x8048604 <ft_des>
   0x08048df8 <+1202>:	mov    %ebx,0x4(%esp)
   
# We test all line in the pattern
# test test test
ju *0x08048de5 # OMG A FLAG
> Continuing at 0x8048de5.
> 7QiHafiNa3HVozsaXkawuYrTstxbpABHD8CPnHJ

# We check previous same pattern above
ju *0x08048dc4
> Continuing at 0x8048dc4.
> 2A31L79asukciNyi8uppkEuSx # THE PREVIOUS FLAG

# SUUUUUUU TIME, working GG




