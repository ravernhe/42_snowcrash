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

scp -P 4242 level14@192.168.56.101:/bin/getflag .
# Get rdy to die
./ghidraRun

# we slect the main

                  else if (_Var6 < 0xbb9) {
                    if (_Var6 == 0) {
                      fwrite("You are root are you that dumb ?\n",1,0x21,stdout);
                    }
                    else {
LAB_08048e06:
                      fwrite("\nNope there is no token here for you sorry. Try again :)",1,0x38,
                             stdout);
                    }
                  }
                  else {
                    pcVar4 = (char *)ft_des("7`4Ci4=^d=J,?>i;6,7d416,7");
                    fputs(pcVar4,__stream);
                  }
                }
                else if (_Var6 == 0xbbc) {
                  pcVar4 = (char *)ft_des("?4d@:,C>8C60G>8:h:Gb4?l,A");
                  fputs(pcVar4,__stream);
                }
                else if (_Var6 < 0xbbd) {
                  pcVar4 = (char *)ft_des("B8b:6,3fj7:,;bh>D@>8i:6@D");
                  fputs(pcVar4,__stream);
                }
                else {
                  pcVar4 = (char *)ft_des("G8H.6,=4k5J0<cd/D@>>B:>:4");
                  fputs(pcVar4,__stream);
                }
              }
              else if (_Var6 == 0xbc2) {
                pcVar4 = (char *)ft_des("74H9D^3ed7k05445J0E4e;Da4");
                fputs(pcVar4,__stream);
              }
              else if (_Var6 < 0xbc3) {
                if (_Var6 == 0xbc0) {
                  pcVar4 = (char *)ft_des("bci`mC{)jxkn<\"uD~6%g7FK`7");
                  fputs(pcVar4,__stream);
                }
                else if (_Var6 < 0xbc1) {
                  pcVar4 = (char *)ft_des("78H:J4<4<9i_I4k0J^5>B1j`9");
                  fputs(pcVar4,__stream);
                }
                else {
                  pcVar4 = (char *)ft_des("Dc6m~;}f8Cj#xFkel;#&ycfbK");
                  fputs(pcVar4,__stream);
                }
              }
              else if (_Var6 == 0xbc4) {
                pcVar4 = (char *)ft_des("8_Dw\"4#?+3i]q&;p6 gtw88EC");
                fputs(pcVar4,__stream);
              }
              else if (_Var6 < 0xbc4) {
                pcVar4 = (char *)ft_des("70hCi,E44Df[A4B/J@3f<=:`D");
                fputs(pcVar4,__stream);
              }
              else if (_Var6 == 0xbc5) {
                pcVar4 = (char *)ft_des("boe]!ai0FB@.:|L6l@A?>qJ}I");
                fputs(pcVar4,__stream);
              }
              else {
                if (_Var6 != 0xbc6) goto LAB_08048e06;
                pcVar4 = (char *)ft_des("g <t61:|4_|!@IF.-62FH&G~DCK/Ekrvvdwz?v|");
                fputs(pcVar4,__stream);
              }

# We can see a if forest using uid, they decypher the encrypted flag then puts them
# So we skip everything and jump to the last if (or the one before a flag) so it decypher the flag and print it without checking id

                             LAB_08048de5                                    XREF[1]:     08048bbb(j)  
        08048de5 a1 60 b0        MOV        EAX,[stdout]
                 04 08
        08048dea 89 c3           MOV        EBX,EAX
        08048dec c7 04 24        MOV        dword ptr [ESP]=>local_130,s_g_<t61:|4_|!@IF.-   = "g <t61:|4_|!@IF.-62FH&G~DCK/E
                 20 92 04 08
        08048df3 e8 0c f8        CALL       ft_des                                           undefined ft_des(undefined4 para
                 ff ff
        08048df8 89 5c 24 04     MOV        dword ptr [ESP + local_12c],EBX
        08048dfc 89 04 24        MOV        dword ptr [ESP]=>local_130,EAX
        08048dff e8 2c f7        CALL       <EXTERNAL>::fputs                                int fputs(char * __s, FILE * __s
                 ff ff

ju *0x08048de5
> Continuing at 0x8048de5.
> 7QiHafiNa3HVozsaXkawuYrTstxbpABHD8CPnHJ

# Dada
# SUUUUUUU TIME, working GG




