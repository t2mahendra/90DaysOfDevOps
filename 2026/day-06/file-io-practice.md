**Day 06 – Linux Fundamentals: Read and Write Text Files**

**Task Done**


Creating a file
root@Mahi-Server:~#touch mahi

Writing text to a file
root@Mahi-Server:~#vim Mahi

Appending new lines
my name is mahendra.
all good

Create a file named notes.txt

Write 3 lines into the file using redirection (> and >>)
Use cat to read the full file
Use head and tail to read parts of the file
Use tee once to write and display at the same time
Keep it short (8–12 lines total in the file)

mahi@Mahi-Server:~$

mahi@Mahi-Server:~$ touch notes.txt

mahi@Mahi-Server:~$ echi "line 1" > notes.txt
Command 'echi' not found, did you mean:
  command 'echo' from deb coreutils (9.4-3ubuntu6.1)
Try: apt install <deb name>
mahi@Mahi-Server:~$ echo notes.txt
notes.txt
mahi@Mahi-Server:~$ cat notes.txt

mahi@Mahi-Server:~$ head -n 2 notes.txt

mahi@Mahi-Server:~$
mahi@Mahi-Server:~$ tail -n 2 notes.txt
mahi@Mahi-Server:~$ echo "Line 3" | tee -a notes.txt


root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# touch my file
root@Mahi-Server:~# cat my file
root@Mahi-Server:~# head my file
==> my <==

==> file <==


Happy Learning

Mahendra





