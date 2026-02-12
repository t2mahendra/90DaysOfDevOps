# Breather & Revision (Days 01–11)

## What to Review (pick at least one per section)
- **Mindset & plan:** revisit your Day 01 learning plan—are your goals still right? any tweaks?
- Revisit your Day 01 learning plan from the #90DaysOfDevOps challenge by confirming if its foundational focus—what is DevOps, basic principles, and resources like mind maps—still aligns with your current expertise in broadcast engineering, i am practice on Linux/Ubuntu.
- **Processes & services:** rerun 2 commands from Day 04/05 (e.g., `ps`, `systemctl status`, `journalctl -u <service>`); jot what you observed today.
- root@Mahi-Server:~# sysmctl status vsftpd

Command 'sysmctl' not found, did you mean: command 'sysctl' from deb procps (2:4.0.4-4ubuntu3.2) Try: apt install root@Mahi-Server:# sysmctl start vsftpd Command 'sysmctl' not found, did you mean: command 'sysctl' from deb procps (2:4.0.4-4ubuntu3.2) Try: apt install root@Mahi-Server:# systemctl status vsftpd

● vsftpd.service - vsftpd FTP server Loaded: loaded (/usr/lib/systemd/system/vsftpd.service; enabled; preset: enabled) Active: active (running) since Wed 2026-02-04 06:42:52 UTC; 15min ago Process: 712 ExecStartPre=/bin/mkdir -p /var/run/vsftpd/empty (code=exited, statu> Main PID: 726 (vsftpd) Tasks: 1 (limit: 4653) Memory: 928.0K (peak: 1.5M) CPU: 14ms CGroup: /system.slice/vsftpd.service └─726 /usr/sbin/vsftpd /etc/vsftpd.conf

Feb 04 06:42:51 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Feb 04 06:42:52 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.

root@Mahi-Server:~# journalctl -u vsftpd

Jan 26 05:08:24 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Jan 26 05:08:24 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server. Jan 26 05:08:43 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server... Jan 26 05:08:43 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully. Jan 26 05:08:43 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server. Jan 26 05:08:43 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Jan 26 05:08:43 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server. Jan 26 05:10:13 Mahi-Server vsftpd[13729]: pam_unix(vsftpd:auth): check pass; user un> Jan 26 05:10:13 Mahi-Server vsftpd[13729]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:33:38 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server... Jan 26 05:33:38 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully. Jan 26 05:33:38 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server. Jan 26 05:33:38 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Jan 26 05:33:38 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server. Jan 26 05:33:46 Mahi-Server vsftpd[14068]: pam_unix(vsftpd:auth): check pass; user un> Jan 26 05:33:46 Mahi-Server vsftpd[14068]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:33:48 Mahi-Server vsftpd[14070]: pam_unix(vsftpd:auth): check pass; user un> Jan 26 05:33:48 Mahi-Server vsftpd[14070]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:34:11 Mahi-Server vsftpd[14078]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:35:51 Mahi-Server vsftpd[14124]: pam_unix(vsftpd:auth): check pass; user un> Jan 26 05:35:51 Mahi-Server vsftpd[14124]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:39:18 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server... Jan 26 05:39:18 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully. Jan 26 05:39:18 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server. Jan 26 05:39:18 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Jan 26 05:39:18 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server. Jan 26 05:39:33 Mahi-Server vsftpd[14400]: pam_unix(vsftpd:auth): check pass; user un> Jan 26 05:39:33 Mahi-Server vsftpd[14400]: pam_unix(vsftpd:auth): authentication fail> Jan 26 05:40:42 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server... Jan 26 05:40:42 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully. Jan 26 05:40:42 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server. -- Boot 7d7c160f471c437887dbcc0d4c5a0d56 -- Jan 26 19:26:41 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server... Jan 26 19:26:41 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server. Jan 26 14:01:11 Mahi-Server vsftpd[932]: pam_unix(vsftpd:auth): check pass; user unkn> Jan 26 14:01:11 Mahi-Server vsftpd[932]: pam_unix(vsftpd:auth): authentication failur> lines 10-36 ^C root@Mahi-Server:~# tail -n 50


- **File skills:** practice 3 quick ops from Days 06–11 (e.g., `echo >>`, `chmod`, `chown`, `ls -l`, `cp`, `mkdir`).

- mahi@Mahi-Server:~$ echo notes.txt

notes.txt mahi@Mahi-Server:~$ cat notes.txt

mahi@Mahi-Server:~$ head -n 2 notes.txt

mahi@Mahi-Server:$ mahi@Mahi-Server:$ tail -n 2 notes.txt

mahi@Mahi-Server:~$ echo "Line 3" | tee -a notes.txt

root@Mahi-Server:# root@Mahi-Server:# root@Mahi-Server:# touch my file root@Mahi-Server:# cat my file root@Mahi-Server:~# head my file ==> my <==

<img width="468" height="78" alt="image" src="https://github.com/user-attachments/assets/ce7c9212-b3f0-4e99-9254-5cc3a2792c05" />

- **Cheat sheet refresh:** skim your Day 03 commands—highlight 5 you’d reach for first in an incident.
- root@Mahi-Server:~# htop
- root@Mahi-Server:/home# ll
- root@Mahi-Server:~# ip a
- root@Mahi-Server:# ping 8.8.8.8
- root@Mahi-Server:~# dig
- 
- **User/group sanity:** recreate one small scenario from Day 09 or Day 11 (create a user or change ownership) and verify with `id`/`ls -l`.
- Create three users with home directories and passwords:

tokyo berlin professor Verify: Check /etc/passwd and /home/ directory

root@Mahi-Server:~# adduser tokyo

root@Mahi-Server:~# adduser berlin

root@Mahi-Server:~# adduser professor

root@Mahi-Server:~# cat /etc/passwd

Run ls -l in your home directory

change ownership

Run ls -l in your home directory

<img width="507" height="155" alt="image" src="https://github.com/user-attachments/assets/50f8b992-d45a-43f7-8d5d-390c084b3950" />

Identify the owner and group columns
Check who owns your files
Format: -rw-r--r-- 1 owner group size date filename

Basic chown Operations 
Create file devops-file.txt
Check current owner: ls -l devops-file.txt
Change owner to tokyo (create user if needed)
Change owner to berlin
Verify the changes

<img width="445" height="160" alt="image" src="https://github.com/user-attachments/assets/4ef20f51-5cf5-4ff3-8ec7-eb964e8dc7dc" />

Basic chgrp Operations 
Create file team-notes.txt
Check current group: ls -l team-notes.txt
Create group: sudo groupadd heist-team
Change file group to heist-team
Verify the change

<img width="441" height="150" alt="image" src="https://github.com/user-attachments/assets/73e9e7ab-4230-4623-b9b0-49441400a7c6" />

Combined Owner & Group Change 
Using chown you can change both owner and group together:

Create file project-config.yaml
Change owner to professor AND group to heist-team (one command)
Create directory app-logs/
Change its owner to berlin and group to heist-team

<img width="578" height="427" alt="image" src="https://github.com/user-attachments/assets/638a57c3-a63e-44af-841b-9874f60efdad" />

Recursive Ownership 
Create directory structure:

mkdir -p heist-project/vault
mkdir -p heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf
Create group planners: sudo groupadd planners

Change ownership of entire heist-project/ directory:

Owner: professor
Group: planners
Use recursive flag (-R)
Verify all files and subdirectories changed: ls -lR heist-project/

<img width="553" height="336" alt="image" src="https://github.com/user-attachments/assets/fb86d7d5-676f-4c58-b7ed-415eb1a00d85" />


Happy Learning  
**Mahendra Singh**

