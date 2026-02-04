**Day 05 – Linux Troubleshooting Drill: CPU, Memory, and Logs**

**Task Done**

-Capture a quick health snapshot (CPU, memory, disk, network)
-Trace logs for that service
-Write a mini runbook describing what you did and what you’d do next if things were worse

root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# top -bn1 | head -n 20
top - 07:15:52 up 33 min,  2 users,  load average: 0.00, 0.02, 0.03
Tasks: 122 total,   1 running, 121 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  4.5 sy,  0.0 ni, 95.5 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3915.9 total,   2065.0 free,    587.7 used,   1584.3 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3328.2 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
   8984 root      20   0   12360   5376   3328 R   9.1   0.1   0:00.02 top
      1 root      20   0   22564  13696   9600 S   0.0   0.3   0:05.18 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_wo+
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
     10 root      20   0       0      0      0 I   0.0   0.0   0:00.04 kworker+
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.58 kworker+
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tas+
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# df -h
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           392M  1.1M  391M   1% /run
/dev/vda1        77G  3.7G   73G   5% /
tmpfs           2.0G     0  2.0G   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  170M  650M  21% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
tmpfs           392M   12K  392M   1% /run/user/0
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# free -h
               total        used        free      shared  buff/cache   available
Mem:           3.8Gi       585Mi       2.0Gi        51Mi       1.5Gi       3.3Gi
Swap:             0B          0B          0B
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# sysemctl --failed
Command 'sysemctl' not found, did you mean:
  command 'systemctl' from deb systemd (255.4-1ubuntu8.12)
  command 'systemctl' from deb systemctl (1.4.4181-1.1)
Try: apt install <deb name>
root@Mahi-Server:~# systemctl --failed
  UNIT LOAD ACTIVE SUB DESCRIPTION

0 loaded units listed.
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# journalctl -p 3 -xb | tail -n 20
-- No entries --
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# ss -tulpn
Netid   State    Recv-Q    Send-Q       Local Address:Port        Peer Address:Port                                              Process
udp     UNCONN   0         0                  0.0.0.0:7359             0.0.0.0:*                                                  users:(("jellyfin",pid=7837,fd=455))
udp     UNCONN   0         0               127.0.0.54:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=16))
udp     UNCONN   0         0            127.0.0.53%lo:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=14))
tcp     LISTEN   0         128              127.0.0.1:6010             0.0.0.0:*                                                  users:(("sshd",pid=8822,fd=7))
tcp     LISTEN   0         512                0.0.0.0:8096             0.0.0.0:*                                                  users:(("jellyfin",pid=7837,fd=480))
tcp     LISTEN   0         4096         127.0.0.53%lo:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=15))
tcp     LISTEN   0         4096            127.0.0.54:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=17))
tcp     LISTEN   0         4096             127.0.0.1:40001            0.0.0.0:*                                                  users:(("containerd",pid=8218,fd=9))
tcp     LISTEN   0         4096               0.0.0.0:22               0.0.0.0:*                                                  users:(("sshd",pid=7825,fd=3),("systemd",pid=1,fd=93))
tcp     LISTEN   0         4096                  [::]:22                  [::]:*                                                  users:(("sshd",pid=7825,fd=4),("systemd",pid=1,fd=94))
tcp     LISTEN   0         32                       *:21                     *:*                                                  users:(("vsftpd",pid=7824,fd=3))
tcp     LISTEN   0         128                  [::1]:6010                [::]:*                                                  users:(("sshd",pid=8822,fd=5))
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# sudo apt install lm-sensors
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  linux-headers-6.8.0-87 linux-headers-6.8.0-87-generic linux-image-6.8.0-87-generic
  linux-modules-6.8.0-87-generic linux-tools-6.8.0-87 linux-tools-6.8.0-87-generic
Use 'sudo apt autoremove' to remove them.
Suggested packages:
  fancontrol read-edid i2c-tools
The following NEW packages will be installed:
  lm-sensors
0 upgraded, 1 newly installed, 0 to remove and 4 not upgraded.
Need to get 90.1 kB of archives.
After this operation, 387 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble/universe amd64 lm-sensors amd64 1:3.6.0-9                                           build1 [90.1 kB]
Fetched 90.1 kB in 1s (94.4 kB/s)
Selecting previously unselected package lm-sensors.
(Reading database ... 141619 files and directories currently installed.)
Preparing to unpack .../lm-sensors_1%3a3.6.0-9build1_amd64.deb ...
Unpacking lm-sensors (1:3.6.0-9build1) ...
Setting up lm-sensors (1:3.6.0-9build1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/lm-sensors.service → /usr/                                           lib/systemd/system/lm-sensors.service.
Processing triggers for man-db (2.12.0-4build2) ...
Scanning processes...
Scanning candidates...
Scanning linux images...

Pending kernel upgrade!
Running kernel version:
  6.8.0-90-generic
Diagnostics:
  The currently running kernel version is not the expected kernel version
6.8.0-94-generic.

Restarting the system to load the new kernel will not be handled automatically, so
you should consider rebooting.

Restarting services...

Service restarts being deferred:
 /etc/needrestart/restart.d/dbus.service
 systemctl restart getty@tty1.service
 systemctl restart serial-getty@ttyS0.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service

No containers need to be restarted.

User sessions running outdated binaries:
 root @ user manager service: systemd[998]



Run and record output for at least 8 commands (save snippets in your runbook)
Environment basics (2): uname -a, lsb_release -a (or cat /etc/os-release)
Filesystem sanity (2): create a throwaway folder and file, e.g., mkdir /tmp/runbook-demo, cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo
CPU / Memory (2): top/htop/ps -o pid,pcpu,pmem,comm -p <pid>, free -h, vm_stat (mac)
Disk / IO (2): df -h, du -sh /var/log, iostat/vmstat/dstat
Network (2): ss -tulpn/netstat -tulpn, curl -I <service-endpoint>/ping
Logs (2): journalctl -u <service> -n 50, tail -n 50 /var/log/<file>.log
Choose one target service/process (e.g., ssh, cron, docker, your web app) and stick to it for the drill.
For each command, add a 1–2 line note on what you observed (e.g., “CPU spikes to 80% when restarting”, No recent errors in last 50 lines”).

root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# uname -a
Linux Mahi-Server 6.8.0-90-generic #91-Ubuntu SMP PREEMPT_DYNAMIC Tue Nov 18 14:14:30                                            UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.3 LTS
Release:        24.04
Codename:       noble
root@Mahi-Server:~# cat /etc/os-release
PRETTY_NAME="Ubuntu 24.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.3 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
root@Mahi-Server:~# makdir /tmp/runbook-demo
Command 'makdir' not found, did you mean:
  command 'mkdir' from deb coreutils (9.4-3ubuntu6.1)
  command 'mmkdir' from deb mblaze (1.1-1)
Try: apt install <deb name>
root@Mahi-Server:~# makdir /tmp/runbook-demo.txt
Command 'makdir' not found, did you mean:
  command 'mmkdir' from deb mblaze (1.1-1)
  command 'mkdir' from deb coreutils (9.4-3ubuntu6.1)
Try: apt install <deb name>
root@Mahi-Server:~# makdir /tmp/runbook-demo
Command 'makdir' not found, did you mean:
  command 'mmkdir' from deb mblaze (1.1-1)
  command 'mkdir' from deb coreutils (9.4-3ubuntu6.1)
Try: apt install <deb name>
root@Mahi-Server:~# sudo mkdir /tmp/runbook-demo
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-d                                           emo
total 4
-rw-r--r-- 1 root root 221 Feb  4 07:25 hosts-copy
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# top
top - 07:25:55 up 43 min,  2 users,  load average: 0.00, 0.02, 0.00
Tasks: 119 total,   1 running, 118 sleeping,   0 stopped,   0 zombie
%Cpu(s):  4.5 us,  4.5 sy,  0.0 ni, 90.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3915.9 total,   2075.1 free,    571.9 used,   1589.8 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3344.0 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0   22564  13696   9600 S   0.0   0.3   0:05.53 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueu+
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slu+
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-net+
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-+
     10 root      20   0       0      0      0 I   0.0   0.0   0:00.04 kworker/0:1-c+
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.67 kworker/u4:0-+
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_+
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kth+
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rud+
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_tra+
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.10 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:03.47 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.02 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
root@Mahi-Server:~# htop
root@Mahi-Server:~# ps -o pid
    PID
   9374
   9461
root@Mahi-Server:~# pcpu
Command 'pcpu' not found, did you mean:
  command 'pcp' from deb pcp (6.1.1-1)
  command 'cpu' from deb cpu (1.4.3-13build2)
  command 'pcpp' from deb pcc (1.2.0~DEVEL+20220331-1)
Try: apt install <deb name>
root@Mahi-Server:~# df -h
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           392M  1.1M  391M   1% /run
/dev/vda1        77G  3.7G   73G   5% /
tmpfs           2.0G     0  2.0G   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  170M  650M  21% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
tmpfs           392M   12K  392M   1% /run/user/0
root@Mahi-Server:~# du -sh
104K    .
root@Mahi-Server:~# du -sh /var/log
66M     /var/log
root@Mahi-Server:~# ss -tulpn
Netid   State    Recv-Q    Send-Q       Local Address:Port        Peer Address:Port                                              Process
udp     UNCONN   0         0                  0.0.0.0:7359             0.0.0.0:*                                                  users:(("jellyfin",pid=7837,fd=455))
udp     UNCONN   0         0               127.0.0.54:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=16))
udp     UNCONN   0         0            127.0.0.53%lo:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=14))
tcp     LISTEN   0         128              127.0.0.1:6010             0.0.0.0:*                                                  users:(("sshd",pid=9269,fd=7))
tcp     LISTEN   0         512                0.0.0.0:8096             0.0.0.0:*                                                  users:(("jellyfin",pid=7837,fd=480))
tcp     LISTEN   0         4096         127.0.0.53%lo:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=15))
tcp     LISTEN   0         4096            127.0.0.54:53               0.0.0.0:*                                                  users:(("systemd-resolve",pid=7803,fd=17))
tcp     LISTEN   0         4096             127.0.0.1:40001            0.0.0.0:*                                                  users:(("containerd",pid=8218,fd=9))
tcp     LISTEN   0         4096               0.0.0.0:22               0.0.0.0:*                                                  users:(("sshd",pid=7825,fd=3),("systemd",pid=1,fd=135))
tcp     LISTEN   0         4096                  [::]:22                  [::]:*                                                  users:(("sshd",pid=7825,fd=4),("systemd",pid=1,fd=137))
tcp     LISTEN   0         32                       *:21                     *:*                                                  users:(("vsftpd",pid=7824,fd=3))
tcp     LISTEN   0         128                  [::1]:6010                [::]:*                                                  users:(("sshd",pid=9269,fd=5))
root@Mahi-Server:~# netstat -tulpn
Command 'netstat' not found, but can be installed with:
apt install net-tools
root@Mahi-Server:~# apt install net-tools
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  linux-headers-6.8.0-87 linux-headers-6.8.0-87-generic linux-image-6.8.0-87-generic
  linux-modules-6.8.0-87-generic linux-tools-6.8.0-87 linux-tools-6.8.0-87-generic
Use 'apt autoremove' to remove them.
The following NEW packages will be installed:
  net-tools
0 upgraded, 1 newly installed, 0 to remove and 4 not upgraded.
Need to get 204 kB of archives.
After this operation, 811 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 net-tools amd64 2.10-0                                           .1ubuntu4.4 [204 kB]
Fetched 204 kB in 2s (135 kB/s)
Selecting previously unselected package net-tools.
(Reading database ... 141654 files and directories currently installed.)
Preparing to unpack .../net-tools_2.10-0.1ubuntu4.4_amd64.deb ...
Unpacking net-tools (2.10-0.1ubuntu4.4) ...
Setting up net-tools (2.10-0.1ubuntu4.4) ...
Processing triggers for man-db (2.12.0-4build2) ...
Scanning processes...
Scanning candidates...
Scanning linux images...

Pending kernel upgrade!
Running kernel version:
  6.8.0-90-generic
Diagnostics:
  The currently running kernel version is not the expected kernel version
6.8.0-94-generic.

Restarting the system to load the new kernel will not be handled automatically, so
you should consider rebooting.

Restarting services...

Service restarts being deferred:
 /etc/needrestart/restart.d/dbus.service
 systemctl restart getty@tty1.service
 systemctl restart serial-getty@ttyS0.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service

No containers need to be restarted.

User sessions running outdated binaries:
 root @ user manager service: systemd[998]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
root@Mahi-Server:~# netstat -tulpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Pr                                           ogram name
tcp        0      0 127.0.0.1:6010          0.0.0.0:*               LISTEN      9269/s                                           shd: root@pts
tcp        0      0 0.0.0.0:8096            0.0.0.0:*               LISTEN      7837/j                                           ellyfin
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      7803/s                                           ystemd-resolv
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      7803/s                                           ystemd-resolv
tcp        0      0 127.0.0.1:40001         0.0.0.0:*               LISTEN      8218/c                                           ontainerd
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      1/syst                                           emd
tcp6       0      0 :::22                   :::*                    LISTEN      1/syst                                           emd
tcp6       0      0 :::21                   :::*                    LISTEN      7824/v                                           sftpd
tcp6       0      0 ::1:6010                :::*                    LISTEN      9269/s                                           shd: root@pts
udp        0      0 0.0.0.0:7359            0.0.0.0:*                           7837/j                                           ellyfin
udp        0      0 127.0.0.54:53           0.0.0.0:*                           7803/s                                           ystemd-resolv
udp        0      0 127.0.0.53:53           0.0.0.0:*                           7803/s                                           ystemd-resolv
root@Mahi-Server:~# tail -n 50 /var/log/<file>.log
-bash: file: No such file or directory
root@Mahi-Server:~# tail -n 50 /var/log/file.log
tail: cannot open '/var/log/file.log' for reading: No such file or directory
root@Mahi-Server:~# ssh
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface] [-b bind_address]
           [-c cipher_spec] [-D [bind_address:]port] [-E log_file]
           [-e escape_char] [-F configfile] [-I pkcs11] [-i identity_file]
           [-J destination] [-L address] [-l login_name] [-m mac_spec]
           [-O ctl_cmd] [-o option] [-P tag] [-p port] [-R address]
           [-S ctl_path] [-W host:port] [-w local_tun[:remote_tun]]
           destination [command [argument ...]]
       ssh [-Q query_option]
root@Mahi-Server:~# ^C
root@Mahi-Server:~#

