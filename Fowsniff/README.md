nmap:
22 ssh
80 http
110 pop3
143 imap

found twitter: https://twitter.com/fowsniffcorp
found employees cred: check credential.txt

use metasploit to bruteforce pop3: make 2 dir:	user.txt+pass.txt

found seina:scoobydoo2

checking emails got ssh cred: bakteen:S1ck3nBluff+secureshell

bakteen belongs to group <users> 
	/opt/cube/cube.sh can be edited -> add rev shell 

checking /etc/update-motd.d: 00-header run cube.sh as shell
-> exit ssh -> log-in again -> get shell as root
