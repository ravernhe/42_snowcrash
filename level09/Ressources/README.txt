# Again level09 and token, ls -l, both in group level09

# Let's try to run level09
./level09
> You need to provied only one arg.

# Let's test
./level09 test
> tfuw

# USE BRAIN POWER, T + 0 = T, E + 1 = F, etc
# We code a reverse level09
```
import sys

str = [chr(ord(x)-i) for i, x in enumerate(sys.argv[1])]
print(''.join(str))
```

# We use it on the content of token
python /tmp/reverse_level09.py `cat token`
> f3iji1ju5yuevaus41q1afiuq

# WE SUUUUUUUU flag09
getflag
> Check flag.Here is your token : s5cAJpM8ev6XHw998pRWG728z
