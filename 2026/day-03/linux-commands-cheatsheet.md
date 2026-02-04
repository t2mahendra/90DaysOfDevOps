**Day 03 – Linux Commands Practice**

**Task Done**

You will create a cheat sheet of commands focused on:

**-Process management
-File system
-Networking troubleshooting**

**root@Mahi-Server:~# htop**
 0[|                              0.7%] Tasks: 28, 42 thr, 101 kthr; 1 running
    1[|                              1.3%] Load average: 0.24 0.27 0.11
  Mem[||||||||||               289M/3.82G] Uptime: 00:02:15
  Swp[                              0K/0K]

  [Main] [I/O]
    PID USER       IO    DISK R/W?  DISK READ  DISK WRITE SWPD%  IOD% Command
      1 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/init
    323 root       B3    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    370 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    387 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    388 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    389 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    390 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    391 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    392 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    393 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /sbin/multipathd
    512 systemd-re B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    519 systemd-ti B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    565 systemd-ti B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    632 systemd-ne B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
    679 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/sbin/cron -
    680 messagebus B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 @dbus-daemon --s
    685 jellyfin   B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/bin/jellyfi
    689 polkitd    B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/polkit-
    698 root       B4    0.00 B/s    0.00 B/s    0.00 B/s   0.0   0.0 /usr/lib/systemd
F1Help  F2Setup F3SearchF4FilterF5Tree  F6SortByF7Nice -F8Nice +F9Kill  F10Quit

**root@Mahi-Server:/home# ll**
total 20
drwxr-xr-x  5 root   root   4096 Jan 26 14:32 ./
drwxr-xr-x 22 root   root   4096 Feb  4 06:42 ../
drwxr-xr-x  2 root   root   4096 Jan 26 14:35 Data/
drwxr-x---  3 mahi   mahi   4096 Jan 26 05:40 mahi/
drwxr-x---  3 ubuntu ubuntu 4096 Jan 25 19:41 ubuntu/
root@Mahi-Server:/home#

**root@Mahi-Server:~# ip a**
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:16:3e:b3:b6:7f brd ff:ff:ff:ff:ff:ff
    altname enp0s3
    inet 150.241.245.184/24 brd 150.241.245.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::216:3eff:feb3:b67f/64 scope link
       valid_lft forever preferred_lft forever
root@Mahi-Server:~#
root@Mahi-Server:~# ping 8.8.88
PING 8.8.88 (8.8.0.88) 56(84) bytes of data.
^C
--- 8.8.88 ping statistics ---
3 packets transmitted, 0 received, 100% packet loss, time 2033ms

root@Mahi-Server:~# ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=116 time=37.6 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=116 time=32.6 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=116 time=36.9 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=116 time=29.9 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=116 time=37.9 ms
64 bytes from 8.8.8.8: icmp_seq=6 ttl=116 time=39.4 ms
^C
--- 8.8.8.8 ping statistics ---
6 packets transmitted, 6 received, 0% packet loss, time 5008ms
rtt min/avg/max/mdev = 29.870/35.700/39.397/3.347 ms
root@Mahi-Server:~# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen                                            1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default ql                                           en 1000
    link/ether 00:16:3e:b3:b6:7f brd ff:ff:ff:ff:ff:ff
    altname enp0s3
    inet 150.241.245.184/24 brd 150.241.245.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::216:3eff:feb3:b67f/64 scope link
       valid_lft forever preferred_lft forever
root@Mahi-Server:~# dig

; <<>> DiG 9.18.39-0ubuntu0.24.04.2-Ubuntu <<>>
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 29810
;; flags: qr rd ra; QUERY: 1, ANSWER: 13, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;.                              IN      NS

;; ANSWER SECTION:
.                       7142    IN      NS      e.root-servers.net.
.                       7142    IN      NS      h.root-servers.net.
.                       7142    IN      NS      i.root-servers.net.
.                       7142    IN      NS      g.root-servers.net.
.                       7142    IN      NS      k.root-servers.net.
.                       7142    IN      NS      m.root-servers.net.
.                       7142    IN      NS      f.root-servers.net.
.                       7142    IN      NS      j.root-servers.net.
.                       7142    IN      NS      l.root-servers.net.
.                       7142    IN      NS      d.root-servers.net.
.                       7142    IN      NS      a.root-servers.net.
.                       7142    IN      NS      b.root-servers.net.
.                       7142    IN      NS      c.root-servers.net.

;; Query time: 1 msec
;; SERVER: 127.0.0.53#53(127.0.0.53) (UDP)
;; WHEN: Wed Feb 04 06:50:12 UTC 2026
;; MSG SIZE  rcvd: 239

root@Mahi-Server:~# pwd
/root
root@Mahi-Server:~# curl
curl: try 'curl --help' or 'curl --manual' for more information
root@Mahi-Server:~# cd /home/
root@Mahi-Server:/home#
root@Mahi-Server:/home#
root@Mahi-Server:/home#
root@Mahi-Server:/home#
root@Mahi-Server:/home#
root@Mahi-Server:/home#
root@Mahi-Server:/home# cd
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~#
root@Mahi-Server:~# top
top - 06:51:04 up 8 min,  2 users,  load average: 0.00, 0.07, 0.06
Tasks: 121 total,   1 running, 120 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3915.9 total,   3122.3 free,    496.6 used,    567.8 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3419.3 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0   22052  13096   9384 S   0.0   0.3   0:02.25 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueu+
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slu+
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-net+
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-+
     10 root      20   0       0      0      0 I   0.0   0.0   0:00.04 kworker/0:1-e+
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.24 kworker/u4:0-+
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_+
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kth+
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rud+
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_tra+
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.02 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:01.22 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.00 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
root@Mahi-Server:~#

Happy Learning
Mahendra





