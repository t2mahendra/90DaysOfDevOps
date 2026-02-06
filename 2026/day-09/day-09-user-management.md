
**Day 09 – Linux User & Group Management Challenge**

**Task Done**

Today's goal is to practice user and group management by completing hands-on challenges.

Figure out how to:

Create users and set passwords
Create groups and assign users
Set up shared directories with group permissions

Challenge Tasks
Task 1: Create Users (20 minutes)
Create three users with home directories and passwords:

tokyo
berlin
professor
Verify: Check /etc/passwd and /home/ directory

root@Mahi-Server:~# adduser tokyo

info: Adding user `tokyo' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `tokyo' (1002) ...
info: Adding new user `tokyo' (1002) with group `tokyo (1002)' ...
info: Creating home directory `/home/tokyo' ...
info: Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for tokyo
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n]
info: Adding new user `tokyo' to supplemental / extra groups `users' ...
info: Adding user `tokyo' to group `users' ...
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# adduser berlin
info: Adding user `berlin' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `berlin' (1003) ...
info: Adding new user `berlin' (1003) with group `berlin (1003)' ...
info: Creating home directory `/home/berlin' ...
info: Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for berlin
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n]
info: Adding new user `berlin' to supplemental / extra groups `users' ...
info: Adding user `berlin' to group `users' ...
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# adduser professor
info: Adding user `professor' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Adding new group `professor' (1004) ...
info: Adding new user `professor' (1004) with group `professor (1004)' ...
info: Creating home directory `/home/professor' ...
info: Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for professor
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n]
info: Adding new user `professor' to supplemental / extra groups `users' ...
info: Adding user `professor' to group `users' ...
root@Mahi-Server:~#
root@Mahi-Server:~#

root@Mahi-Server:~# cat /etc/passwd

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:998:998:systemd Network Management:/:/usr/sbin/nologin
systemd-timesync:x:996:996:systemd Time Synchronization:/:/usr/sbin/nologin
dhcpcd:x:100:65534:DHCP Client Daemon,,,:/usr/lib/dhcpcd:/bin/false
messagebus:x:101:101::/nonexistent:/usr/sbin/nologin
syslog:x:102:102::/nonexistent:/usr/sbin/nologin
systemd-resolve:x:991:991:systemd Resolver:/:/usr/sbin/nologin
uuidd:x:103:103::/run/uuidd:/usr/sbin/nologin
tss:x:104:104:TPM software stack,,,:/var/lib/tpm:/bin/false
sshd:x:105:65534::/run/sshd:/usr/sbin/nologin
pollinate:x:106:1::/var/cache/pollinate:/bin/false
tcpdump:x:107:108::/nonexistent:/usr/sbin/nologin
landscape:x:108:109::/var/lib/landscape:/usr/sbin/nologin
fwupd-refresh:x:990:990:Firmware update daemon:/var/lib/fwupd:/usr/sbin/nologin
polkitd:x:989:989:User for polkitd:/:/usr/sbin/nologin
ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash
mahi:x:1001:1001:,,,:/home/mahi:/bin/bash
ftp:x:109:113:ftp daemon,,,:/srv/ftp:/usr/sbin/nologin
jellyfin:x:110:114:Jellyfin default user,,,:/var/lib/jellyfin:/bin/false
dnsmasq:x:999:65534:dnsmasq:/var/lib/misc:/usr/sbin/nologin
tokyo:x:1002:1002:,,,:/home/tokyo:/bin/bash
berlin:x:1003:1003:,,,:/home/berlin:/bin/bash
professor:x:1004:1004:,,,:/home/professor:/bin/bash
root@Mahi-Server:~#

root@Mahi-Server:~# cd /home/
root@Mahi-Server:/home# ll
total 32
drwxr-xr-x  8 root      root      4096 Feb  6 12:56 ./
drwxr-xr-x 22 root      root      4096 Feb  6 11:53 ../
drwxr-xr-x  2 root      root      4096 Jan 26 20:05 Data/
drwxr-x---  2 berlin    berlin    4096 Feb  6 12:56 berlin/
drwxr-x---  4 mahi      mahi      4096 Feb  6 12:12 mahi/
drwxr-x---  2 professor professor 4096 Feb  6 12:56 professor/
drwxr-x---  2 tokyo     tokyo     4096 Feb  6 12:55 tokyo/
drwxr-x---  3 ubuntu    ubuntu    4096 Jan 26 01:11 ubuntu/
root@Mahi-Server:/home#

Task 2: Create Groups (10 minutes)
Create two groups:

developers
admins
Verify: Check /etc/group

root@Mahi-Server:~# sudo addgroup developers
info: Selecting GID from range 1000 to 59999 ...
info: Adding group `developers' (GID 1005) ...
root@Mahi-Server:~# sudo addgroup admins
info: Selecting GID from range 1000 to 59999 ...
info: Adding group `admins' (GID 1006) ...
root@Mahi-Server:~# cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,ubuntu
tty:x:5:
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:ubuntu
floppy:x:25:
tape:x:26:
sudo:x:27:ubuntu
audio:x:29:
dip:x:30:ubuntu
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
shadow:x:42:
utmp:x:43:
video:x:44:jellyfin
sasl:x:45:
plugdev:x:46:
staff:x:50:
games:x:60:
users:x:100:mahi,tokyo,berlin,professor
nogroup:x:65534:
systemd-journal:x:999:
systemd-network:x:998:
crontab:x:997:
systemd-timesync:x:996:
input:x:995:
sgx:x:994:
kvm:x:993:
render:x:992:jellyfin
messagebus:x:101:
syslog:x:102:
systemd-resolve:x:991:
uuidd:x:103:
tss:x:104:
lxd:x:105:ubuntu
_ssh:x:106:
rdma:x:107:
tcpdump:x:108:
landscape:x:109:
fwupd-refresh:x:990:
polkitd:x:989:
admin:x:110:
netdev:x:111:
ubuntu:x:1000:
mahi:x:1001:
ssl-cert:x:112:
ftp:x:113:
jellyfin:x:114:
docker:x:115:
tokyo:x:1002:
berlin:x:1003:
professor:x:1004:
developers:x:1005:
admins:x:1006:
root@Mahi-Server:~#

Task 3: Assign to Groups (15 minutes)
Assign users:

tokyo → developers
berlin → developers + admins (both groups)
professor → admins
Verify: Use appropriate command to check group membership

root@Mahi-Server:~# sudo usermod -aG developers tokyo
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# sudo usermod -aG developers berlin
root@Mahi-Server:~# sudo usermod -aG admin berlin
admin   admins

root@Mahi-Server:~# sudo usermod -aG admins berlin
root@Mahi-Server:~# cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,ubuntu
tty:x:5:
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:ubuntu
floppy:x:25:
tape:x:26:
sudo:x:27:ubuntu
audio:x:29:
dip:x:30:ubuntu
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
shadow:x:42:
utmp:x:43:
video:x:44:jellyfin
sasl:x:45:
plugdev:x:46:
staff:x:50:
games:x:60:
users:x:100:mahi,tokyo,berlin,professor
nogroup:x:65534:
systemd-journal:x:999:
systemd-network:x:998:
crontab:x:997:
systemd-timesync:x:996:
input:x:995:
sgx:x:994:
kvm:x:993:
render:x:992:jellyfin
messagebus:x:101:
syslog:x:102:
systemd-resolve:x:991:
uuidd:x:103:
tss:x:104:
lxd:x:105:ubuntu
_ssh:x:106:
rdma:x:107:
tcpdump:x:108:
landscape:x:109:
fwupd-refresh:x:990:
polkitd:x:989:
admin:x:110:
netdev:x:111:
ubuntu:x:1000:
mahi:x:1001:
ssl-cert:x:112:
ftp:x:113:
jellyfin:x:114:
docker:x:115:
tokyo:x:1002:
berlin:x:1003:
professor:x:1004:
developers:x:1005:tokyo,berlin
admins:x:1006:berlin
root@Mahi-Server:~#

Task 4: Shared Directory (20 minutes)
Create directory: /opt/dev-project
Set group owner to developers
Set permissions to 775 (rwxrwxr-x)
Test by creating files as tokyo and berlin
Verify: Check permissions and test file creation

root@Mahi-Server:~# touch /opt/dev-project
root@Mahi-Server:~# cd /opt/
root@Mahi-Server:/opt# ll
total 12
drwxr-xr-x  3 root root 4096 Feb  6 13:30 ./
drwxr-xr-x 22 root root 4096 Feb  6 11:53 ../
drwx--x--x  4 root root 4096 Feb  4 12:35 containerd/
-rw-r--r--  1 root root    0 Feb  6 13:30 dev-project
root@Mahi-Server:/opt#

root@Mahi-Server:~# touch /opt/dev-project
root@Mahi-Server:~# cd /opt/
root@Mahi-Server:/opt# ll
total 12
drwxr-xr-x  3 root root 4096 Feb  6 13:30 ./
drwxr-xr-x 22 root root 4096 Feb  6 11:53 ../
drwx--x--x  4 root root 4096 Feb  4 12:35 containerd/
-rw-r--r--  1 root root    0 Feb  6 13:30 dev-project
root@Mahi-Server:/opt# ^C
root@Mahi-Server:/opt#
root@Mahi-Server:/opt#
root@Mahi-Server:/opt#
root@Mahi-Server:/opt#
root@Mahi-Server:/opt# sudo chown :developers /opt/dev-project
root@Mahi-Server:/opt# sudo chmod 775 /opt/dev-project
root@Mahi-Server:/opt# ll
total 12
drwxr-xr-x  3 root root       4096 Feb  6 13:30 ./
drwxr-xr-x 22 root root       4096 Feb  6 11:53 ../
drwx--x--x  4 root root       4096 Feb  4 12:35 containerd/
-rwxrwxr-x  1 root developers    0 Feb  6 13:30 dev-project*
root@Mahi-Server:/opt# # Test as user tokyo

Task 5: Team Workspace (20 minutes)
Create user nairobi with home directory
Create group project-team
Add nairobi and tokyo to project-team
Create /opt/team-workspace directory
Set group to project-team, permissions to 775
Test by creating file as nairobi

root@Mahi-Server:~#
root@Mahi-Server:~# sudo useradd -m nairobi
root@Mahi-Server:~# sudo groupadd project-team
root@Mahi-Server:~# sudo usermod -aG project-team nairobi
root@Mahi-Server:~# sudo usermod -aG project-team tokyo
root@Mahi-Server:~# sudo mkdir /opt/team-workspace
root@Mahi-Server:~# sudo chown :project-team /opt/team-workspace
root@Mahi-Server:~# sudo chmod 775 /opt/team-workspace
root@Mahi-Server:~# sudo -u nairobi touch /opt/team-workspace/nairobi-test.txt
ls -l /opt/team-workspace/nairobi-test.txt
-rw-rw-r-- 1 nairobi nairobi 0 Feb  6 14:14 /opt/team-workspace/nairobi-test.txt
root@Mahi-Server:~#

Happy Learning 

Mahendra



