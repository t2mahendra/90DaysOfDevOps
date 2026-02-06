**Day 07 – Linux File System Hierarchy & Scenario-Based Practice**

**Task Done**

Core Directories (Must Know):

/ (root) - The starting point of everything
/home - User home directories
/root - Root user's home directory
/etc - Configuration files
/var/log - Log files (very important for DevOps!)
/tmp - Temporary files

root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# ll
total 112
drwx------  6 root root  4096 Feb  5 03:48 ./
drwxr-xr-x 22 root root  4096 Feb  5 03:21 ../
-rw-------  1 root root   180 Feb  5 03:48 .Xauthority
-rw-------  1 root root  3343 Feb  5 03:33 .bash_history
-rw-r--r--  1 root root  3106 Apr 22  2024 .bashrc
drwx------  2 root root  4096 Jan 25 14:15 .cache/
drwx------  4 root root  4096 Feb  4 06:51 .config/
-rw-------  1 root root    20 Feb  4 14:35 .lesshst
drwxr-xr-x  3 root root  4096 Jan 26 05:30 .local/
-rw-r--r--  1 root root   161 Apr 22  2024 .profile
drwx------  2 root root  4096 Jan 25 19:41 .ssh/
-rw-------  1 root root  1468 Feb  5 03:31 .viminfo
-rw-r--r--  1 root root    39 Feb  5 03:23 Mahi
-rw-r--r--  1 root root    51 Jan 25 14:14 init.log
-rw-r--r--  1 root root 12926 Jan 26 14:09 install-debuntu.sh
-rwxr-xr-x  1 root root  9455 Jan 28 15:24 install_pnetlab_v6.sh*
-rw-r--r--  1 root root  9455 Jan 28 16:15 install_pnetlab_v6.sh.1
-rw-r--r--  1 root root  9455 Feb  4 15:04 install_pnetlab_v6.sh.2
-rw-r--r--  1 root root     7 Jan 25 14:14 utho.txt
root@Mahi-Server:~# /home/
-bash: /home/: Is a directory
root@Mahi-Server:~# cd /home/
root@Mahi-Server:/home# /root/
-bash: /root/: Is a directory
root@Mahi-Server:/home# /etc/
-bash: /etc/: Is a directory
root@Mahi-Server:/home# cd /etc/
root@Mahi-Server:/etc#
root@Mahi-Server:/etc#
root@Mahi-Server:/etc#
root@Mahi-Server:/etc# cd /var/log/
root@Mahi-Server:/var/log# ll
total 7136
drwxrwxr-x  10 root      syslog             4096 Feb  5 03:21 ./
drwxr-xr-x  13 root      root               4096 Jan 25 19:41 ../
lrwxrwxrwx   1 root      root                 39 Oct 31 12:53 README -> ../../us                                                    r/share/doc/systemd/README.logs
-rw-r--r--   1 root      root                296 Feb  4 07:04 alternatives.log
-rw-r--r--   1 root      root                618 Jan 26 04:50 alternatives.log.1
-rw-r-----   1 root      adm                   0 Jan 25 19:41 apport.log
drwxr-xr-x   2 root      root               4096 Feb  4 07:28 apt/
-rw-r-----   1 syslog    adm             1086780 Feb  5 03:49 auth.log
-rw-r-----   1 syslog    adm              154350 Jan 28 16:21 auth.log.1
-rw-rw----   1 root      utmp            1213056 Feb  5 03:43 btmp
-rw-rw----   1 root      utmp             122112 Jan 26 15:29 btmp.1
-rw-r-----   1 root      adm               50891 Feb  5 03:21 cloud-init-output.                                                    log
-rw-r-----   1 syslog    adm              950090 Feb  5 03:21 cloud-init.log
drwxr-xr-x   2 root      root               4096 Jul 25  2025 dist-upgrade/
-rw-r-----   1 root      adm               50251 Feb  5 03:21 dmesg
-rw-r-----   1 root      adm               50681 Feb  4 14:34 dmesg.0
-rw-r-----   1 root      adm               15361 Feb  4 13:11 dmesg.1.gz
-rw-r-----   1 root      adm               15408 Feb  4 08:09 dmesg.2.gz
-rw-r-----   1 root      adm               15164 Feb  4 06:42 dmesg.3.gz
-rw-r-----   1 root      adm               15726 Jan 28 20:45 dmesg.4.gz
-rw-r--r--   1 root      root              29750 Feb  4 15:04 dpkg.log
-rw-r--r--   1 root      root              94074 Jan 28 16:16 dpkg.log.1
drwxr-x---   2 jellyfin  adm                4096 Feb  5 03:21 jellyfin/
drwxr-sr-x+  3 root      systemd-journal    4096 Jan 25 19:41 journal/
-rw-r-----   1 syslog    adm              307537 Feb  5 03:21 kern.log
-rw-r-----   1 syslog    adm              608748 Jan 28 20:45 kern.log.1
drwxr-xr-x   2 landscape landscape          4096 Jan 25 14:15 landscape/
-rw-rw-r--   1 root      utmp             292584 Feb  5 03:48 lastlog
drwx------   2 root      root               4096 Jan 25 19:41 private/
-rw-r-----   1 syslog    adm              897898 Feb  5 03:50 syslog
-rw-r-----   1 syslog    adm             1445636 Jan 28 16:21 syslog.1
drwxr-xr-x   2 root      root               4096 Feb  5 03:21 sysstat/
-rw-r--r--   1 root      root                  0 Jan 26 04:50 ubuntu-advantage-a                                                    pt-hook.log
drwxr-x---   2 root      adm                4096 Feb  4 06:42 unattended-upgrade                                                    s/
-rw-r-----   1 root      adm                 389 Feb  5 03:47 vsftpd.log
-rw-------   1 root      root               3859 Jan 26 14:01 vsftpd.log.1
-rw-rw-r--   1 root      utmp              48384 Feb  5 03:48 wtmp
root@Mahi-Server:/var/log# cd /tmp/
root@Mahi-Server:/tmp#

Hands-on task:

# Find the largest log file in /var/log
du -sh /var/log/* 2>/dev/null | sort -h | tail -5

root@Mahi-Server:/tmp# du -sh /var/log/* 2>/dev/null | sort -h | tail -5
932K    /var/log/cloud-init.log
1.1M    /var/log/auth.log
1.2M    /var/log/btmp
1.4M    /var/log/syslog.1
93M     /var/log/journal
root@Mahi-Server:/tmp#

# Look at a config file in /etc
cat /etc/hostname
Mahi-Server

# Check your home directory
ls -la ~

root@Mahi-Server:/tmp# ls -la ~
total 112
drwx------  6 root root  4096 Feb  5 03:48 .
drwxr-xr-x 22 root root  4096 Feb  5 03:53 ..
-rw-------  1 root root   180 Feb  5 03:48 .Xauthority
-rw-------  1 root root  3343 Feb  5 03:33 .bash_history
-rw-r--r--  1 root root  3106 Apr 22  2024 .bashrc
drwx------  2 root root  4096 Jan 25 14:15 .cache
drwx------  4 root root  4096 Feb  4 06:51 .config
-rw-------  1 root root    20 Feb  4 14:35 .lesshst
drwxr-xr-x  3 root root  4096 Jan 26 05:30 .local
-rw-r--r--  1 root root   161 Apr 22  2024 .profile
drwx------  2 root root  4096 Jan 25 19:41 .ssh
-rw-------  1 root root  1468 Feb  5 03:31 .viminfo
-rw-r--r--  1 root root    39 Feb  5 03:23 Mahi
-rw-r--r--  1 root root    51 Jan 25 14:14 init.log
-rw-r--r--  1 root root 12926 Jan 26 14:09 install-debuntu.sh
-rwxr-xr-x  1 root root  9455 Jan 28 15:24 install_pnetlab_v6.sh
-rw-r--r--  1 root root  9455 Jan 28 16:15 install_pnetlab_v6.sh.1
-rw-r--r--  1 root root  9455 Feb  4 15:04 install_pnetlab_v6.sh.2
-rw-r--r--  1 root root     7 Jan 25 14:14 utho.txt
root@Mahi-Server:/tmp# \

Part 2: Scenario-Based Practice

Question: How do you check if the 'nginx' service is running?
root@Mahi-Server:~# systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; preset: en>
     Active: active (**running**) since Thu 2026-02-05 03:59:08 UTC; 7s ago
       Docs: man:nginx(8)
    Process: 3426 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_proce>
    Process: 3428 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (c>
   Main PID: 3457 (nginx)
      Tasks: 3 (limit: 4653)
     Memory: 2.4M (peak: 5.3M)
        CPU: 27ms
     CGroup: /system.slice/nginx.service
             ├─3457 "nginx: master process /usr/sbin/nginx -g daemon on; master>
             ├─3460 "nginx: worker process"
             └─3461 "nginx: worker process"

Feb 05 03:59:08 Mahi-Server systemd[1]: Starting nginx.service - A high perform>
Feb 05 03:59:08 Mahi-Server systemd[1]: Started nginx.se


Step 2: If service is not found, list all services

systemctl list-units --type=service
root@Mahi-Server:~# systemctl list-units --type=service
  UNIT                                           LOAD   ACTIVE SUB     DESCRIPT>
  apparmor.service                               loaded active exited  Load App>
  apport.service                                 loaded active exited  automati>
  blk-availability.service                       loaded active exited  Availabi>
  cloud-config.service                           loaded active exited  Cloud-in>
  cloud-final.service                            loaded active exited  Cloud-in>
  cloud-init-local.service                       loaded active exited  Cloud-in>
  cloud-init.service                             loaded active exited  Cloud-in>
  console-setup.service                          loaded active exited  Set cons>
  containerd.service                             loaded active running containe>
  cron.service                                   loaded active running Regular >
  dbus.service                                   loaded active running D-Bus Sy>
  docker.service                                 loaded active running Docker A>
  finalrd.service                                loaded active exited  Create f>
  getty@tty1.service                             loaded active running Getty on>
  jellyfin.service                               loaded active running Jellyfin>
  keyboard-setup.service                         loaded active exited  Set the >
  kmod-static-nodes.service                      loaded active exited  Create L>
  lm-sensors.service                             loaded active exited  Initiali>
  lvm2-monitor.service                           loaded active exited  Monitori>
  ModemManager.service                           loaded active running Modem Ma>
  multipathd.service                             loaded active running Device-M>
  nginx.service                                  loaded active running A high p>
  plymouth-quit-wait.service                     loaded 

Step 3: Check if service is enabled on boot

systemctl is-enabled nginx
root@Mahi-Server:~# systemctl is-enabled nginx
enabled


Scenario 1: Service Not Starting

A web application service called 'myapp' failed to start after a server reboot.
What commands would you run to diagnose the issue?
Write at least 4 commands in order.
Hint:

First check: Is the service running or failed?
Then check: What do the logs say?
Finally check: Is it enabled to start on boot?
Commands to explore: systemctl status myapp, systemctl is-enabled myapp, journalctl -u myapp -n 50

Resource: Review Day 04 (Process and Services practice)

Template for your answer:

Step 1: [command]
Why:  systemctl start vsftpd

Step 2: [command]
Why: systemctl restart vsftpd

...
Scenario 2: High CPU Usage

Your manager reports that the application server is slow.
You SSH into the server. What commands would you run to identify
which process is using high CPU?
Hint:

root@Mahi-Server:~# htop
root@Mahi-Server:~# kill 782
root@Mahi-Server:~#

Scenario 3: Finding Service Logs

A developer asks: "Where are the logs for the 'docker' service?"
The service is managed by systemd.
What commands would you use?

root@Mahi-Server:~# journalctl -u docker
Feb 04 12:35:27 Mahi-Server systemd[1]: Starting docker.service - Docker Applic>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.298742497Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.299383409Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.299633077Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.342660710Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.513668642Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.853701639Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.871676845Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.871783776Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.875137845Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.875156410Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.903497613Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.911197812Z>
Feb 04 12:35:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.911248497Z>
Feb 04 12:35:27 Mahi-Server systemd[1]: Started docker.service - Docker Applica>
Feb 04 13:38:58 Mahi-Server systemd[1]: Stopping docker.service - Docker Applic>
Feb 04 13:38:58 Mahi-Server dockerd[8438]: time="2026-02-04T08:08:58.317857100Z>
Feb 04 13:38:58 Mahi-Server dockerd[8438]: time="2026-02-04T08:08:58.387635974Z>
Feb 04 13:38:58 Mahi-Server systemd[1]: docker.service: Deactivated successfull>
Feb 04 13:38:58 Mahi-Server systemd[1]: Stopped docker.service - Docker Applica>
Feb 04 13:38:58 Mahi-Server systemd[1]: docker.service: Consumed 1.076s CPU tim>
-- Boot 4f0dbd2d587747809a5f460a9a3c017d --
Feb 04 13:39:15 Mahi-Server systemd[1]: Starting docker.service - Docker Applic>
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.130000424Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.138493089Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.142859937Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.255494602Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.290385457Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.292547651Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.747547927Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.826128546Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.847818377Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.848153977Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.851332036Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.851353737Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.882410081Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.887701173Z">
Feb 04 13:39:16 Mahi-Server dockerd[933]: time="2026-02-04T08:09:16.887764632Z">
Feb 04 13:39:16 Mahi-Server systemd[1]: Started docker.service - Docker Applica>
Feb 04 14:52:18 Mahi-Server systemd[1]: Stopping docker.service - Docker Applic>
Feb 04 14:52:18 Mahi-Server dockerd[933]: time="2026-02-04T09:22:18.742864218Z">
Feb 04 14:52:18 Mahi-Server dockerd[933]: time="2026-02-04T09:22:18.752300953Z">
Feb 04 14:52:18 Mahi-Server dockerd[933]: time="2026-02-04T09:22:18.757444047Z">
Feb 04 14:52:18 Mahi-Server dockerd[933]: time="2026-02-04T09:22:18.759153032Z">
Feb 04 14:52:18 Mahi-Server systemd[1]: docker.service: Deactivated successfull>
Feb 04 14:52:18 Mahi-Server systemd[1]: Stopped docker.service - Docker Applica>
Feb 04 14:52:18 Mahi-Server systemd[1]: docker.service: Consumed 1.156s CPU tim>
-- Boot 41e8dc40aee34170b0bcbddca700be1c --
Feb 04 18:41:56 Mahi-Server systemd[1]: Starting docke

root@Mahi-Server:~#
root@Mahi-Server:~# systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: ena>
     Active: active (running) since Fri 2026-02-06 11:54:12 IST; 14min ago
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 1373 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 1374 (sshd)
      Tasks: 1 (limit: 4653)
     Memory: 7.2M (peak: 25.7M)
        CPU: 496ms
     CGroup: /system.slice/ssh.service
             └─1374 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

Feb 06 12:00:52 Mahi-Server sshd[1666]: pam_unix(sshd:auth): check pass; user u>
Feb 06 12:00:52 Mahi-Server sshd[1666]: pam_unix(sshd:auth): authentication fai>
Feb 06 12:00:55 Mahi-Server sshd[1666]: Failed password for invalid user admin >
Feb 06 12:00:56 Mahi-Server sshd[1666]: Connection closed by invalid user admin>
Feb 06 12:04:07 Mahi-Server sshd[1692]: pam_unix(sshd:auth): authentication fai>
Feb 06 12:04:10 Mahi-Server sshd[1692]: Failed password for root from 65.20.202>
Feb 06 12:04:11 Mahi-Server sshd[1692]: Connection closed by authenticating use>
Feb 06 12:04:17 Mahi-Server sshd[1694]: pam_unix(sshd:auth): authentication fai>
Feb 06 12:04:19 Mahi-Server sshd[1694]: Failed password for root from 62.201.22>

root@Mahi-Server:~# journalctl -u ssh -n 50
Feb 05 12:00:07 Mahi-Server sshd[7590]: pam_unix(sshd:auth): authentication fai>
Feb 05 12:00:08 Mahi-Server sshd[7591]: Connection closed by invalid user admin>
Feb 05 12:00:09 Mahi-Server sshd[7590]: Failed password for ubuntu from 167.172>
Feb 05 12:00:10 Mahi-Server sshd[7590]: Connection closed by authenticating use>
Feb 05 12:00:24 Mahi-Server sshd[7598]: Invalid user postgres from 152.42.130.2>
Feb 05 12:00:25 Mahi-Server sshd[7598]: pam_unix(sshd:auth): check pass; user u>
Feb 05 12:00:25 Mahi-Server sshd[7598]: pam_unix(sshd:auth): authentication fai>
Feb 05 12:00:27 Mahi-Server sshd[7598]: Failed password for invalid user postgr>
Feb 05 12:00:29 Mahi-Server sshd[7600]: Invalid user admin from 134.209.84.60 p>
Feb 05 12:00:29 Mahi-Server sshd[7600]: pam_unix(sshd:auth): check pass; user u>
Feb 05 12:00:29 Mahi-Server sshd[7600]: pam_unix(sshd:auth): authentication fai>
Feb 05 12:00:29 Mahi-Server sshd[7598]: Connection closed by invalid user postg>
Feb 05 12:00:31 Mahi-Server sshd[7600]: Failed password for invalid user admin >
Feb 05 12:00:33 Mahi-Server sshd[7600]: Connection closed by invalid user admin>
Feb 05 12:00:54 Mahi-Server sshd[7605]: Invalid user admin from 134.209.84.60 p>
Feb 05 12:00:55 Mahi-Server sshd[7605]: pam_unix(sshd:auth): check pass; user u>
Feb 05 12:00:55 Mahi-Server sshd[7605]: pam_unix(sshd:auth): authentication fai>
Feb 05 12:00:56 Mahi-Server sshd[7605]: Failed password for invalid user admin >
Feb 05 12:00:57 Mahi-Server sshd[7605]: Connection closed by invalid user admin>
Feb 05 12:01:02 Mahi-Server systemd[1]: Stopping ssh.service - OpenBSD Secure S>
Feb 05 12:01:02 Mahi-Server sshd[1359]: Received signal 15; terminating.


root@Mahi-Server:~# journalctl -u ssh -f
Feb 06 12:00:52 Mahi-Server sshd[1666]: pam_unix(sshd:auth): check pass; user unknown
Feb 06 12:00:52 Mahi-Server sshd[1666]: pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=203.198.129.123
Feb 06 12:00:55 Mahi-Server sshd[1666]: Failed password for invalid user admin from 203.198.129.123 port 59075 ssh2
Feb 06 12:00:56 Mahi-Server sshd[1666]: Connection closed by invalid user admin 203.198.129.123 port 59075 [preauth]
Feb 06 12:04:07 Mahi-Server sshd[1692]: pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=65.20.202.4  user=root
Feb 06 12:04:10 Mahi-Server sshd[1692]: Failed password for root from 65.20.202.4 port 54089 ssh2
Feb 06 12:04:11 Mahi-Server sshd[1692]: Connection closed by authenticating user root 65.20.202.4 port 54089 [preauth]



Scenario 4: File Permissions Issue

A script at /home/user/backup.sh is not executing.
When you run it: ./backup.sh
You get: "Permission denied"

What commands would you use to fix this?

root@Mahi-Server:~# ls -l /home/mahi/backup.sh
-rw-r--r-- 1 root root 0 Feb  6 12:12 /home/mahi/backup.sh

root@Mahi-Server:~# chmod +x /home/mahi/backup.sh
root@Mahi-Server:~# ls -l /home/mahi/backup.sh
-rwxr-xr-x 1 root root 0 Feb  6 12:12 /home/mahi/backup.sh

Knowing where to find logs, configs, and binaries
Troubleshooting deployment issues
Writing automation scripts that work across systems
Scenario-based practice prepares you for:

Real production incidents
DevOps interviews
On-call troubleshooting under pressure

Happy Learning 

Mahendra Singh







