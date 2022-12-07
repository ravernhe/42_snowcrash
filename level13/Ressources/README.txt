# We have an executable ./level13

./level13
> UID 2013 started us but we we expect 4242

# So we need to find a way to have the good UID

# strings level13
libc.so.6           # Mean we have a code in C
_IO_stdin_used
exit
strdup
printf
getuid              # Get the UID
__libc_start_main
GLIBC_2.0
PTRh`
UWVS
[^_]
0123456
UID %d started us but we we expect %d # The UID getted is in a var
boe]!ai0FB@.:|L6l@A?>qJ}I
your token is %s

# NGL i was advised to use GDB SO WE LEARN TO USE GDB
# AND GOD THIS THING MAKE ME HORNY

# So we put a breakpoint at getuid and when the function return a value we put it manually

gdb
> b getuid
> r
> return (int) 4242
> c
Continuing.
your token is 2A31L79asukciNyi8uppkEuSx
[Inferior 1 (process 2135) exited with code 050]
