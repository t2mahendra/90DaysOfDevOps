****Day 04 – Linux Practice: Processes and Services**

**Task Done**

**-Check running processes
-Inspect one systemd service
-Capture a small troubleshooting flow**

root@Mahi-Server:~#
root@Mahi-Server:~# ps
    PID TTY          TIME CMD
   1584 pts/0    00:00:00 bash
   1601 pts/0    00:00:00 ps
root@Mahi-Server:~# top
top - 06:56:14 up 13 min,  2 users,  load average: 0.03, 0.03, 0.04
Tasks: 117 total,   1 running, 116 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  4.8 sy,  0.0 ni, 95.2 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3915.9 total,   3120.9 free,    497.8 used,    568.1 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3418.1 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0   22052  13096   9384 S   0.0   0.3   0:02.27 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueu+
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu+
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slu+
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-net+
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-+
     10 root      20   0       0      0      0 I   0.0   0.0   0:00.04 kworker/0:1-c+
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.26 kworker/u4:0-+
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_+
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kth+
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rud+
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_tra+
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.03 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:01.96 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.00 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
root@Mahi-Server:~# pgrep
pgrep: no matching criteria specified
Try `pgrep --help' for more information.
root@Mahi-Server:~# pgrep --help

Usage:
 pgrep [options] <pattern>

Options:
 -d, --delimiter <string>  specify output delimiter
 -l, --list-name           list PID and process name
 -a, --list-full           list PID and full command line
 -v, --inverse             negates the matching
 -w, --lightweight         list all TID
 -c, --count               count of matching processes
 -f, --full                use full process name to match
 -g, --pgroup <PGID,...>   match listed process group IDs
 -G, --group <GID,...>     match real group IDs
 -i, --ignore-case         match case insensitively
 -n, --newest              select most recently started
 -o, --oldest              select least recently started
 -O, --older <seconds>     select where older than seconds
 -P, --parent <PPID,...>   match only child processes of the given parent
 -s, --session <SID,...>   match session IDs
     --signal <sig>        signal to send (either number or name)
 -t, --terminal <tty,...>  match by controlling terminal
 -u, --euid <ID,...>       match by effective IDs
 -U, --uid <ID,...>        match by real IDs
 -x, --exact               match exactly with the command name
 -F, --pidfile <file>      read PIDs from file
 -L, --logpidfile          fail if PID file is not locked
 -r, --runstates <state>   match runstates [D,S,Z,...]
 -A, --ignore-ancestors    exclude our ancestors from results
 --cgroup <grp,...>        match by cgroup v2 names
 --ns <PID>                match the processes that belong to the same
                           namespace as <pid>
 --nslist <ns,...>         list which namespaces will be considered for
                           the --ns option.
                           Available namespaces: ipc, mnt, net, pid, user, uts

 -h, --help     display this help and exit
 -V, --version  output version information and exit

For more details see pgrep(1).
root@Mahi-Server:~# sysemctl status
Command 'sysemctl' not found, did you mean:
  command 'systemctl' from deb systemd (255.4-1ubuntu8.12)
  command 'systemctl' from deb systemctl (1.4.4181-1.1)
Try: apt install <deb name>
root@Mahi-Server:~# sysemctl status vasftp
Command 'sysemctl' not found, did you mean:
  command 'systemctl' from deb systemd (255.4-1ubuntu8.12)
  command 'systemctl' from deb systemctl (1.4.4181-1.1)
Try: apt install <deb name>
root@Mahi-Server:~# sysmctl status vsftpd
Command 'sysmctl' not found, did you mean:
  command 'sysctl' from deb procps (2:4.0.4-4ubuntu3.2)
Try: apt install <deb name>
root@Mahi-Server:~# sysmctl start vsftpd
Command 'sysmctl' not found, did you mean:
  command 'sysctl' from deb procps (2:4.0.4-4ubuntu3.2)
Try: apt install <deb name>
root@Mahi-Server:~# systemctl status vsftpd
● vsftpd.service - vsftpd FTP server
     Loaded: loaded (/usr/lib/systemd/system/vsftpd.service; enabled; preset: enabled)
     Active: active (running) since Wed 2026-02-04 06:42:52 UTC; 15min ago
    Process: 712 ExecStartPre=/bin/mkdir -p /var/run/vsftpd/empty (code=exited, statu>
   Main PID: 726 (vsftpd)
      Tasks: 1 (limit: 4653)
     Memory: 928.0K (peak: 1.5M)
        CPU: 14ms
     CGroup: /system.slice/vsftpd.service
             └─726 /usr/sbin/vsftpd /etc/vsftpd.conf

Feb 04 06:42:51 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Feb 04 06:42:52 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.

root@Mahi-Server:~# systemctl list-units
  UNIT                                                                               >
  proc-sys-fs-binfmt_misc.automount                                                  >
  sys-devices-pci0000:00-0000:00:03.0-virtio0-net-eth0.device                        >
  sys-devices-pci0000:00-0000:00:04.0-ata4-host3-target3:0:0-3:0:0:0-block-sr0.device>
  sys-devices-pci0000:00-0000:00:07.0-virtio2-block-vda-vda1.device                  >
  sys-devices-pci0000:00-0000:00:07.0-virtio2-block-vda-vda14.device                 >
  sys-devices-pci0000:00-0000:00:07.0-virtio2-block-vda-vda15.device                 >
  sys-devices-pci0000:00-0000:00:07.0-virtio2-block-vda-vda16.device                 >
  sys-devices-pci0000:00-0000:00:07.0-virtio2-block-vda.device                       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.1-tty-ttyS1.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.10-tty-ttyS10.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.11-tty-ttyS11.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.12-tty-ttyS12.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.13-tty-ttyS13.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.14-tty-ttyS14.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.15-tty-ttyS15.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.16-tty-ttyS16.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.17-tty-ttyS17.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.18-tty-ttyS18.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.19-tty-ttyS19.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.2-tty-ttyS2.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.20-tty-ttyS20.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.21-tty-ttyS21.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.22-tty-ttyS22.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.23-tty-ttyS23.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.24-tty-ttyS24.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.25-tty-ttyS25.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.26-tty-ttyS26.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.27-tty-ttyS27.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.28-tty-ttyS28.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.29-tty-ttyS29.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.3-tty-ttyS3.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.30-tty-ttyS30.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.31-tty-ttyS31.device     >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.4-tty-ttyS4.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.5-tty-ttyS5.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.6-tty-ttyS6.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.7-tty-ttyS7.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.8-tty-ttyS8.device       >
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.9-tty-ttyS9.device       >
  sys-devices-pnp0-00:00-00:00:0-00:00:0.0-tty-ttyS0.device                          >
  sys-devices-virtual-misc-rfkill.device                                             >
  sys-devices-virtual-tty-ttyprintk.device                                           >
  sys-module-configfs.device                                                         >
  sys-module-fuse.device                                                             >
  sys-subsystem-net-devices-eth0.device                                              >
  -.mount                                                                            >
  boot-efi.mount                                                                     >
  boot.mount                                                                         >
  dev-hugepages.mount                                                                >
  dev-mqueue.mount                                                                   >
  proc-sys-fs-binfmt_misc.mount                                                      >
  run-user-0.mount                                                                   >
  sys-fs-fuse-connections.mount                                                      >
  sys-kernel-config.mount                                                            >
  sys-kernel-debug.mount                                                             >
  sys-kernel-tracing.mount                                                           >
  systemd-ask-password-console.path                                                  >
  systemd-ask-password-wall.path                                                     >
  init.scope                                                                         >
  session-8.scope                                                                    >
  session-9.scope                                                                    >
  apparmor.service                                                                   >
  apport.service                                                                     >
  blk-availability.service                                                           >
  cloud-config.service                                                               >
  cloud-final.service                                                                >
  cloud-init-local.service                                                           >
  cloud-init.service                                                                 >
  console-setup.service                                                              >
  cron.service                                                                       >
  dbus.service                                                                       >
  finalrd.service                                                                    >
  getty@tty1.service                                                                 >
  jellyfin.service                                                                   >
  keyboard-setup.service                                                             >
  kmod-static-nodes.service                                                          >
  lvm2-monitor.service                                                               >
  ModemManager.service                                                               >
  multipathd.service                                                                 >
  plymouth-quit-wait.service                                                         >
  plymouth-quit.service                                                              >
  plymouth-read-write.service                                                        >
  polkit.service                                                                     >
  rsyslog.service                                                                    >
  serial-getty@ttyS0.service                                                         >
  setvtrgb.service                                                                   >
  snapd.apparmor.service                                                             >
  snapd.seeded.service                                                               >
  ssh.service                                                                        >
  sysstat.service                                                                    >
  systemd-binfmt.service                                                             >
  systemd-fsck@dev-disk-by\x2dlabel-BOOT.service                                     >
  systemd-fsck@dev-disk-by\x2dlabel-UEFI.service                                     >
  systemd-journal-flush.service                                                      >
  systemd-journald.service                                                           >
  systemd-logind.service                                                             >
  systemd-modules-load.service                                                       >
  systemd-networkd-wait-online.service                                               >
  systemd-networkd.service                                                           >
  systemd-random-seed.service                                                        >
  systemd-remount-fs.service                                                         >
  systemd-resolved.service                                                           >
  systemd-sysctl.service                                                             >
  systemd-timesyncd.service                                                          >
  systemd-tmpfiles-setup-dev-early.service                                           >
  systemd-tmpfiles-setup-dev.service                                                 >
  systemd-tmpfiles-setup.service                                                     >
  systemd-udev-trigger.service                                                       >
  systemd-udevd.service                                                              >
  systemd-update-utmp.service                                                        >
  systemd-user-sessions.service                                                      >
  udisks2.service                                                                    >
  ufw.service                                                                        >
  unattended-upgrades.service                                                        >
  user-runtime-dir@0.service                                                         >
  user@0.service                                                                     >
  vsftpd.service                                                                     >
  -.slice                                                                            >
  system-getty.slice                                                                 >
  system-modprobe.slice                                                              >
  system-serial\x2dgetty.slice                                                       >
  system-systemd\x2dfsck.slice                                                       >
  system.slice                                                                       >
  user-0.slice                                                                       >
  user.slice                                                                         >
  cloud-init-hotplugd.socket                                                         >
  dbus.socket                                                                        >
  dm-event.socket                                                                    >
  iscsid.socket                                                                      >
  lvm2-lvmpolld.socket                                                               >
  lxd-installer.socket                                                               >
  multipathd.socket                                                                  >
  snapd.socket                                                                       >
  ssh.socket                                                                         >
  syslog.socket                                                                      >
  systemd-fsckd.socket                                                               >
  systemd-initctl.socket                                                             >
  systemd-journald-dev-log.socket                                                    >
  systemd-journald.socket                                                            >
  systemd-networkd.socket                                                            >
  systemd-rfkill.socket                                                              >
  systemd-sysext.socket                                                              >
  systemd-udevd-control.socket                                                       >
  systemd-udevd-kernel.socket                                                        >
  uuidd.socket                                                                       >
  basic.target                                                                       >
  cloud-config.target                                                                >
  cloud-init.target                                                                  >
  cryptsetup.target                                                                  >
  getty-pre.target                                                                   >
  getty.target                                                                       >
  graphical.target                                                                   >
  integritysetup.target                                                              >
  local-fs-pre.target                                                                >
  local-fs.target                                                                    >
  multi-user.target                                                                  >
  network-online.target                                                              >
  network-pre.target                                                                 >
  network.target                                                                     >
  nss-lookup.target                                                                  >
  paths.target                                                                       >
  remote-fs-pre.target                                                               >
  remote-fs.target                                                                   >
  slices.target                                                                      >
  snapd.mounts-pre.target                                                            >
  snapd.mounts.target                                                                >
  sockets.target                                                                     >
  swap.target                                                                        >
  sysinit.target                                                                     >
  time-set.target                                                                    >
  timers.target                                                                      >
  veritysetup.target                                                                 >
  apt-daily-upgrade.timer                                                            >
  apt-daily.timer                                                                    >
  dpkg-db-backup.timer                                                               >
  e2scrub_all.timer                                                                  >
  fstrim.timer                                                                       >
  fwupd-refresh.timer                                                                >
  logrotate.timer                                                                    >
  man-db.timer                                                                       >
  motd-news.timer                                                                    >
  sysstat-collect.timer                                                              >
  sysstat-summary.timer                                                              >
  systemd-tmpfiles-clean.timer                                                       >
  update-notifier-download.timer                                                     >
  update-notifier-motd.timer                                                         >

Legend: LOAD   → Reflects whether the unit definition was properly loaded.
        ACTIVE → The high-level unit activation state, i.e. generalization of SUB.
        SUB    → The low-level unit activation state, values depend on unit type.

186 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.

root@Mahi-Server:~# journalctl -u vsftpd
Jan 26 05:08:24 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Jan 26 05:08:24 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.
Jan 26 05:08:43 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server...
Jan 26 05:08:43 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully.
Jan 26 05:08:43 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server.
Jan 26 05:08:43 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Jan 26 05:08:43 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.
Jan 26 05:10:13 Mahi-Server vsftpd[13729]: pam_unix(vsftpd:auth): check pass; user un>
Jan 26 05:10:13 Mahi-Server vsftpd[13729]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:33:38 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server...
Jan 26 05:33:38 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully.
Jan 26 05:33:38 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server.
Jan 26 05:33:38 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Jan 26 05:33:38 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.
Jan 26 05:33:46 Mahi-Server vsftpd[14068]: pam_unix(vsftpd:auth): check pass; user un>
Jan 26 05:33:46 Mahi-Server vsftpd[14068]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:33:48 Mahi-Server vsftpd[14070]: pam_unix(vsftpd:auth): check pass; user un>
Jan 26 05:33:48 Mahi-Server vsftpd[14070]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:34:11 Mahi-Server vsftpd[14078]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:35:51 Mahi-Server vsftpd[14124]: pam_unix(vsftpd:auth): check pass; user un>
Jan 26 05:35:51 Mahi-Server vsftpd[14124]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:39:18 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server...
Jan 26 05:39:18 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully.
Jan 26 05:39:18 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server.
Jan 26 05:39:18 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Jan 26 05:39:18 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.
Jan 26 05:39:33 Mahi-Server vsftpd[14400]: pam_unix(vsftpd:auth): check pass; user un>
Jan 26 05:39:33 Mahi-Server vsftpd[14400]: pam_unix(vsftpd:auth): authentication fail>
Jan 26 05:40:42 Mahi-Server systemd[1]: Stopping vsftpd.service - vsftpd FTP server...
Jan 26 05:40:42 Mahi-Server systemd[1]: vsftpd.service: Deactivated successfully.
Jan 26 05:40:42 Mahi-Server systemd[1]: Stopped vsftpd.service - vsftpd FTP server.
-- Boot 7d7c160f471c437887dbcc0d4c5a0d56 --
Jan 26 19:26:41 Mahi-Server systemd[1]: Starting vsftpd.service - vsftpd FTP server...
Jan 26 19:26:41 Mahi-Server systemd[1]: Started vsftpd.service - vsftpd FTP server.
Jan 26 14:01:11 Mahi-Server vsftpd[932]: pam_unix(vsftpd:auth): check pass; user unkn>
Jan 26 14:01:11 Mahi-Server vsftpd[932]: pam_unix(vsftpd:auth): authentication failur>
lines 10-36
^C
root@Mahi-Server:~# tail -n 50




^C
root@Mahi-Server:~# htop
root@Mahi-Server:~# df -h
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           392M 1004K  391M   1% /run
/dev/vda1        77G  3.2G   74G   5% /
tmpfs           2.0G     0  2.0G   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/vda16      881M  117M  703M  15% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
tmpfs           392M   12K  392M   1% /run/user/0
root@Mahi-Server:~# systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: enabled)
     Active: active (running) since Wed 2026-02-04 06:43:26 UTC; 19min ago
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 990 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 992 (sshd)
      Tasks: 1 (limit: 4653)
     Memory: 7.2M (peak: 25.4M)
        CPU: 742ms
     CGroup: /system.slice/ssh.service
             └─992 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

Feb 04 06:50:22 Mahi-Server sshd[1445]: Failed password for invalid user blank from 1>
Feb 04 06:50:23 Mahi-Server sshd[1445]: Connection closed by invalid user blank 120.1>
Feb 04 06:55:24 Mahi-Server sshd[1475]: Accepted password for root from 125.19.39.171>
Feb 04 06:55:24 Mahi-Server sshd[1475]: pam_unix(sshd:session): session opened for us>
Feb 04 06:55:25 Mahi-Server sshd[1494]: Accepted password for root from 125.19.39.171>
Feb 04 06:55:25 Mahi-Server sshd[1494]: pam_unix(sshd:session): session opened for us>
Feb 04 06:55:36 Mahi-Server sshd[1599]: Connection closed by 167.71.73.193 port 58800
Feb 04 06:56:19 Mahi-Server sshd[1603]: pam_unix(sshd:auth): authentication failure; >
Feb 04 06:56:22 Mahi-Server sshd[1603]: Failed password for root from 65.20.191.97 po>
Feb 04 06:56:22 Mahi-Server sshd[1603]: Connection closed by authenticating user root>
lines 1-24/24 (END)
root@Mahi-Server:~# systemctl status cron
● cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: active (running) since Wed 2026-02-04 06:42:51 UTC; 19min ago
       Docs: man:cron(8)
   Main PID: 679 (cron)
      Tasks: 1 (limit: 4653)
     Memory: 464.0K (peak: 1.8M)
        CPU: 29ms
     CGroup: /system.slice/cron.service
             └─679 /usr/sbin/cron -f -P

Feb 04 06:42:51 Mahi-Server systemd[1]: Started cron.service - Regular background pro>
Feb 04 06:42:51 Mahi-Server (cron)[679]: cron.service: Referenced but unset environme>
Feb 04 06:42:51 Mahi-Server cron[679]: (CRON) INFO (pidfile fd = 3)
Feb 04 06:42:51 Mahi-Server cron[679]: (CRON) INFO (Running @reboot jobs)
Feb 04 06:45:01 Mahi-Server CRON[1237]: pam_unix(cron:session): session opened for us>
Feb 04 06:45:01 Mahi-Server CRON[1238]: (root) CMD (command -v debian-sa1 > /dev/null>
Feb 04 06:45:01 Mahi-Server CRON[1237]: pam_unix(cron:session): session closed for us>
Feb 04 06:55:01 Mahi-Server CRON[1470]: pam_unix(cron:session): session opened for us>
Feb 04 06:55:01 Mahi-Server CRON[1471]: (root) CMD (command -v debian-sa1 > /dev/null>
Feb 04 06:55:01 Mahi-Server CRON[1470]: pam_unix(cron:session): session closed for us>

root@Mahi-Server:~# systemctl status docker
Unit docker.service could not be found.
root@Mahi-Server:~# sudo apt update
Hit:1 http://archive.ubuntu.com/ubuntu noble InRelease
Get:2 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Get:4 https://repo.jellyfin.org/ubuntu noble InRelease [10.6 kB]
Get:5 http://security.ubuntu.com/ubuntu noble-security/main amd64 Packages [1411 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [1723 kB]
Get:8 http://security.ubuntu.com/ubuntu noble-security/main Translation-en [230 kB]
Get:9 http://security.ubuntu.com/ubuntu noble-security/main amd64 Components [21.6 kB]
Get:10 http://security.ubuntu.com/ubuntu noble-security/main amd64 c-n-f Metadata [984                                           4 B]
Get:11 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Packages [929 k                                           B]
Get:12 http://security.ubuntu.com/ubuntu noble-security/universe Translation-en [212 k                                           B]
Get:13 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Components [74.                                           2 kB]
Get:14 http://security.ubuntu.com/ubuntu noble-security/universe amd64 c-n-f Metadata                                            [19.9 kB]
Get:15 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Packages [236                                           9 kB]
Get:16 http://archive.ubuntu.com/ubuntu noble-updates/main Translation-en [322 kB]
Get:17 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Components [175 kB]
Get:18 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 c-n-f Metadata [16.4                                            kB]
Get:19 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [1528 kB                                           ]
Get:20 http://security.ubuntu.com/ubuntu noble-security/restricted Translation-en [543                                            kB]
Get:21 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Components [2                                           12 B]
Get:22 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 c-n-f Metadat                                           a [536 B]
Get:23 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Packages [28.                                           8 kB]
Get:24 http://security.ubuntu.com/ubuntu noble-security/multiverse Translation-en [649                                           2 B]
Get:25 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Components [2                                           12 B]
Get:26 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 c-n-f Metadat                                           a [396 B]
Get:27 http://archive.ubuntu.com/ubuntu noble-updates/universe Translation-en [313 kB]
Get:28 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Components [387 k                                           B]
Get:29 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 c-n-f Metadata [3                                           1.9 kB]
Get:30 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Packages [2547                                            kB]
Get:31 http://archive.ubuntu.com/ubuntu noble-updates/restricted Translation-en [583 k                                           B]
Get:32 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Components [212                                            B]
Get:33 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 c-n-f Metadata                                            [556 B]
Get:34 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Packages [32.1                                            kB]
Get:35 http://archive.ubuntu.com/ubuntu noble-updates/multiverse Translation-en [6816                                            B]
Get:36 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Components [940                                            B]
Get:37 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 c-n-f Metadata                                            [496 B]
Get:38 http://archive.ubuntu.com/ubuntu noble-backports/main amd64 Components [7280 B]
Get:39 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Components [10.                                           5 kB]
Get:40 http://archive.ubuntu.com/ubuntu noble-backports/restricted amd64 Components [2                                           16 B]
Get:41 http://archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [2                                           12 B]
Fetched 13.9 MB in 5s (2861 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
30 packages can be upgraded. Run 'apt list --upgradable' to see them.
root@Mahi-Server:~# sudo apt install docker
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package docker is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  wmdocker

E: Package 'docker' has no installation candidate
root@Mahi-Server:~# sudo apt upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
Get more security updates through Ubuntu Pro with 'esm-apps' enabled:
  libzvbi-common libzvbi0t64
Learn more about Ubuntu Pro at https://ubuntu.com/pro
The following NEW packages will be installed:
  linux-headers-6.8.0-94 linux-headers-6.8.0-94-generic linux-image-6.8.0-94-generic
  linux-modules-6.8.0-94-generic linux-tools-6.8.0-94 linux-tools-6.8.0-94-generic
The following upgrades have been deferred due to phasing:
  libldap-common libldap2 python-apt-common python3-apt
The following packages will be upgraded:
  fwupd inetutils-telnet libc-bin libc-dev-bin libc-devtools libc6 libc6-dev
  libdrm-common libdrm2 libfwupd2 libnuma1 libpng16-16t64 libssl3t64
  linux-headers-generic linux-headers-virtual linux-image-virtual linux-libc-dev
  linux-tools-common linux-virtual locales numactl openssl python3-distupgrade
  screen telnet ubuntu-release-upgrader-core
26 upgraded, 6 newly installed, 0 to remove and 4 not upgraded.
12 standard LTS security updates
Need to get 99.8 MB of archives.
After this operation, 189 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libc-devtools amd64 2.                                           39-0ubuntu8.7 [29.3 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libc6-dev amd64 2.39-0                                           ubuntu8.7 [2124 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libc-dev-bin amd64 2.3                                           9-0ubuntu8.7 [20.4 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-libc-dev amd64 6                                           .8.0-94.96 [1932 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libc6 amd64 2.39-0ubun                                           tu8.7 [3263 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libc-bin amd64 2.39-0u                                           buntu8.7 [682 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libssl3t64 amd64 3.0.1                                           3-0ubuntu3.7 [1942 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 locales all 2.39-0ubun                                           tu8.7 [4225 kB]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 openssl amd64 3.0.13-0                                           ubuntu3.7 [1003 kB]
Get:10 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 inetutils-telnet amd6                                           4 2:2.5-3ubuntu4.1 [100.0 kB]
Get:11 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libdrm-common all 2.4                                           .125-1ubuntu0.1~24.04.1 [9174 B]
Get:12 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libdrm2 amd64 2.4.125                                           -1ubuntu0.1~24.04.1 [41.3 kB]
Get:13 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libnuma1 amd64 2.0.18                                           -1ubuntu0.24.04.1 [23.4 kB]
Get:14 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libpng16-16t64 amd64                                            1.6.43-5ubuntu0.4 [188 kB]
Get:15 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 numactl amd64 2.0.18-                                           1ubuntu0.24.04.1 [39.1 kB]
Get:16 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 ubuntu-release-upgrad                                           er-core all 1:24.04.28 [27.4 kB]
Get:17 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 python3-distupgrade a                                           ll 1:24.04.28 [125 kB]
Get:18 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 telnet all 0.17+2.5-3                                           ubuntu4.1 [3688 B]
Get:19 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libfwupd2 amd64 1.9.3                                           3-0ubuntu1~24.04.1ubuntu1 [137 kB]
Get:20 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 fwupd amd64 1.9.33-0u                                           buntu1~24.04.1ubuntu1 [4590 kB]
Get:21 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-headers-6.8.0-9                                           4 all 6.8.0-94.96 [14.0 MB]
Get:22 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-headers-6.8.0-9                                           4-generic amd64 6.8.0-94.96 [4163 kB]
Get:23 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-modules-6.8.0-9                                           4-generic amd64 6.8.0-94.96 [39.5 MB]
Get:24 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-image-6.8.0-94-                                           generic amd64 6.8.0-94.96 [14.8 MB]
Get:25 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-virtual amd64 6                                           .8.0-94.96 [1694 B]
Get:26 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-image-virtual a                                           md64 6.8.0-94.96 [11.0 kB]
Get:27 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-headers-virtual                                            amd64 6.8.0-94.96 [1646 B]
Get:28 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-headers-generic                                            amd64 6.8.0-94.96 [10.9 kB]
Get:29 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-tools-common al                                           l 6.8.0-94.96 [774 kB]
Get:30 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-tools-6.8.0-94                                            amd64 6.8.0-94.96 [5433 kB]
Get:31 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 linux-tools-6.8.0-94-                                           generic amd64 6.8.0-94.96 [1808 B]
Get:32 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 screen amd64 4.9.1-1u                                           buntu1 [654 kB]
Fetched 99.8 MB in 15s (6497 kB/s)
Extracting templates from packages: 100%
Preconfiguring packages ...
(Reading database ... 109655 files and directories currently installed.)
Preparing to unpack .../libc-devtools_2.39-0ubuntu8.7_amd64.deb ...
Unpacking libc-devtools (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Preparing to unpack .../libc6-dev_2.39-0ubuntu8.7_amd64.deb ...
Unpacking libc6-dev:amd64 (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Preparing to unpack .../libc-dev-bin_2.39-0ubuntu8.7_amd64.deb ...
Unpacking libc-dev-bin (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Preparing to unpack .../linux-libc-dev_6.8.0-94.96_amd64.deb ...
Unpacking linux-libc-dev:amd64 (6.8.0-94.96) over (6.8.0-90.91) ...
Preparing to unpack .../libc6_2.39-0ubuntu8.7_amd64.deb ...
Unpacking libc6:amd64 (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Setting up libc6:amd64 (2.39-0ubuntu8.7) ...
(Reading database ... 109655 files and directories currently installed.)
Preparing to unpack .../libc-bin_2.39-0ubuntu8.7_amd64.deb ...
Unpacking libc-bin (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Setting up libc-bin (2.39-0ubuntu8.7) ...
(Reading database ... 109655 files and directories currently installed.)
Preparing to unpack .../libssl3t64_3.0.13-0ubuntu3.7_amd64.deb ...
Unpacking libssl3t64:amd64 (3.0.13-0ubuntu3.7) over (3.0.13-0ubuntu3.6) ...
Setting up libssl3t64:amd64 (3.0.13-0ubuntu3.7) ...
(Reading database ... 109655 files and directories currently installed.)
Preparing to unpack .../00-locales_2.39-0ubuntu8.7_all.deb ...
Unpacking locales (2.39-0ubuntu8.7) over (2.39-0ubuntu8.6) ...
Preparing to unpack .../01-openssl_3.0.13-0ubuntu3.7_amd64.deb ...
Unpacking openssl (3.0.13-0ubuntu3.7) over (3.0.13-0ubuntu3.6) ...
Preparing to unpack .../02-inetutils-telnet_2%3a2.5-3ubuntu4.1_amd64.deb ...
Unpacking inetutils-telnet (2:2.5-3ubuntu4.1) over (2:2.5-3ubuntu4) ...
Preparing to unpack .../03-libdrm-common_2.4.125-1ubuntu0.1~24.04.1_all.deb ...
Unpacking libdrm-common (2.4.125-1ubuntu0.1~24.04.1) over (2.4.122-1~ubuntu0.24.04.2)                                            ...
Preparing to unpack .../04-libdrm2_2.4.125-1ubuntu0.1~24.04.1_amd64.deb ...
Unpacking libdrm2:amd64 (2.4.125-1ubuntu0.1~24.04.1) over (2.4.122-1~ubuntu0.24.04.2)                                            ...
Preparing to unpack .../05-libnuma1_2.0.18-1ubuntu0.24.04.1_amd64.deb ...
Unpacking libnuma1:amd64 (2.0.18-1ubuntu0.24.04.1) over (2.0.18-1build1) ...
Preparing to unpack .../06-libpng16-16t64_1.6.43-5ubuntu0.4_amd64.deb ...
Unpacking libpng16-16t64:amd64 (1.6.43-5ubuntu0.4) over (1.6.43-5ubuntu0.3) ...
Preparing to unpack .../07-numactl_2.0.18-1ubuntu0.24.04.1_amd64.deb ...
Unpacking numactl (2.0.18-1ubuntu0.24.04.1) over (2.0.18-1build1) ...
Preparing to unpack .../08-ubuntu-release-upgrader-core_1%3a24.04.28_all.deb ...
Unpacking ubuntu-release-upgrader-core (1:24.04.28) over (1:24.04.27) ...
Preparing to unpack .../09-python3-distupgrade_1%3a24.04.28_all.deb ...
Unpacking python3-distupgrade (1:24.04.28) over (1:24.04.27) ...
Preparing to unpack .../10-telnet_0.17+2.5-3ubuntu4.1_all.deb ...
Unpacking telnet (0.17+2.5-3ubuntu4.1) over (0.17+2.5-3ubuntu4) ...
Preparing to unpack .../11-libfwupd2_1.9.33-0ubuntu1~24.04.1ubuntu1_amd64.deb ...
Unpacking libfwupd2:amd64 (1.9.33-0ubuntu1~24.04.1ubuntu1) over (1.9.31-0ubuntu1~24.04                                           .1) ...
Preparing to unpack .../12-fwupd_1.9.33-0ubuntu1~24.04.1ubuntu1_amd64.deb ...
Unpacking fwupd (1.9.33-0ubuntu1~24.04.1ubuntu1) over (1.9.31-0ubuntu1~24.04.1) ...
Selecting previously unselected package linux-headers-6.8.0-94.
Preparing to unpack .../13-linux-headers-6.8.0-94_6.8.0-94.96_all.deb ...
Unpacking linux-headers-6.8.0-94 (6.8.0-94.96) ...
Selecting previously unselected package linux-headers-6.8.0-94-generic.
Preparing to unpack .../14-linux-headers-6.8.0-94-generic_6.8.0-94.96_amd64.deb ...
Unpacking linux-headers-6.8.0-94-generic (6.8.0-94.96) ...
Selecting previously unselected package linux-modules-6.8.0-94-generic.
Preparing to unpack .../15-linux-modules-6.8.0-94-generic_6.8.0-94.96_amd64.deb ...
Unpacking linux-modules-6.8.0-94-generic (6.8.0-94.96) ...
Selecting previously unselected package linux-image-6.8.0-94-generic.
Preparing to unpack .../16-linux-image-6.8.0-94-generic_6.8.0-94.96_amd64.deb ...
Unpacking linux-image-6.8.0-94-generic (6.8.0-94.96) ...
Preparing to unpack .../17-linux-virtual_6.8.0-94.96_amd64.deb ...
Unpacking linux-virtual (6.8.0-94.96) over (6.8.0-90.91) ...
Preparing to unpack .../18-linux-image-virtual_6.8.0-94.96_amd64.deb ...
Unpacking linux-image-virtual (6.8.0-94.96) over (6.8.0-90.91) ...
Preparing to unpack .../19-linux-headers-virtual_6.8.0-94.96_amd64.deb ...
Unpacking linux-headers-virtual (6.8.0-94.96) over (6.8.0-90.91) ...
Preparing to unpack .../20-linux-headers-generic_6.8.0-94.96_amd64.deb ...
Unpacking linux-headers-generic (6.8.0-94.96) over (6.8.0-90.91) ...
Preparing to unpack .../21-linux-tools-common_6.8.0-94.96_all.deb ...
Unpacking linux-tools-common (6.8.0-94.96) over (6.8.0-90.91) ...
Selecting previously unselected package linux-tools-6.8.0-94.
Preparing to unpack .../22-linux-tools-6.8.0-94_6.8.0-94.96_amd64.deb ...
Unpacking linux-tools-6.8.0-94 (6.8.0-94.96) ...
Selecting previously unselected package linux-tools-6.8.0-94-generic.
Preparing to unpack .../23-linux-tools-6.8.0-94-generic_6.8.0-94.96_amd64.deb ...
Unpacking linux-tools-6.8.0-94-generic (6.8.0-94.96) ...
Preparing to unpack .../24-screen_4.9.1-1ubuntu1_amd64.deb ...
Unpacking screen (4.9.1-1ubuntu1) over (4.9.1-1build1) ...
Setting up libfwupd2:amd64 (1.9.33-0ubuntu1~24.04.1ubuntu1) ...
Setting up inetutils-telnet (2:2.5-3ubuntu4.1) ...
Setting up linux-libc-dev:amd64 (6.8.0-94.96) ...
Setting up screen (4.9.1-1ubuntu1) ...
Setting up python3-distupgrade (1:24.04.28) ...
Setting up locales (2.39-0ubuntu8.7) ...
Generating locales (this might take a while)...
  en_US.UTF-8... done
Generation complete.
Setting up linux-headers-6.8.0-94 (6.8.0-94.96) ...
Setting up linux-headers-6.8.0-94-generic (6.8.0-94.96) ...
Setting up libpng16-16t64:amd64 (1.6.43-5ubuntu0.4) ...
Setting up ubuntu-release-upgrader-core (1:24.04.28) ...
Setting up libnuma1:amd64 (2.0.18-1ubuntu0.24.04.1) ...
Setting up libc-dev-bin (2.39-0ubuntu8.7) ...
Setting up openssl (3.0.13-0ubuntu3.7) ...
Setting up libdrm-common (2.4.125-1ubuntu0.1~24.04.1) ...
Setting up linux-tools-common (6.8.0-94.96) ...
Setting up fwupd (1.9.33-0ubuntu1~24.04.1ubuntu1) ...
fwupd-offline-update.service is a disabled or a static unit not running, not starting                                            it.
fwupd-refresh.service is a disabled or a static unit not running, not starting it.
fwupd.service is a disabled or a static unit not running, not starting it.
Setting up libc-devtools (2.39-0ubuntu8.7) ...
Setting up linux-modules-6.8.0-94-generic (6.8.0-94.96) ...
Setting up linux-image-6.8.0-94-generic (6.8.0-94.96) ...
I: /boot/vmlinuz.old is now a symlink to vmlinuz-6.8.0-90-generic
I: /boot/initrd.img.old is now a symlink to initrd.img-6.8.0-90-generic
I: /boot/vmlinuz is now a symlink to vmlinuz-6.8.0-94-generic
I: /boot/initrd.img is now a symlink to initrd.img-6.8.0-94-generic
Setting up telnet (0.17+2.5-3ubuntu4.1) ...
Setting up linux-tools-6.8.0-94 (6.8.0-94.96) ...
Setting up numactl (2.0.18-1ubuntu0.24.04.1) ...
Setting up linux-headers-generic (6.8.0-94.96) ...
Setting up linux-tools-6.8.0-94-generic (6.8.0-94.96) ...
Setting up libdrm2:amd64 (2.4.125-1ubuntu0.1~24.04.1) ...
Setting up libc6-dev:amd64 (2.39-0ubuntu8.7) ...
Setting up linux-image-virtual (6.8.0-94.96) ...
Setting up linux-headers-virtual (6.8.0-94.96) ...
Setting up linux-virtual (6.8.0-94.96) ...
Processing triggers for debianutils (5.17build1) ...
Processing triggers for install-info (7.1-3build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.7) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for dbus (1.14.10-4ubuntu4.1) ...
Processing triggers for linux-image-6.8.0-94-generic (6.8.0-94.96) ...
/etc/kernel/postinst.d/initramfs-tools:
update-initramfs: Generating /boot/initrd.img-6.8.0-94-generic
/etc/kernel/postinst.d/zz-update-grub:
Sourcing file `/etc/default/grub'
Sourcing file `/etc/default/grub.d/50-cloudimg-settings.cfg'
Generating grub configuration file ...
Found linux image: /boot/vmlinuz-6.8.0-94-generic
Found initrd image: /boot/initrd.img-6.8.0-94-generic
Found linux image: /boot/vmlinuz-6.8.0-90-generic
Found initrd image: /boot/initrd.img-6.8.0-90-generic
Found linux image: /boot/vmlinuz-6.8.0-87-generic
Found initrd image: /boot/initrd.img-6.8.0-87-generic
Warning: os-prober will not be executed to detect other bootable partitions.
Systems on them will not be added to the GRUB boot configuration.
Check GRUB_DISABLE_OS_PROBER documentation entry.
Adding boot menu entry for UEFI Firmware Settings ...
done
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
 /etc/needrestart/restart.d/systemd-manager
 systemctl restart apt-news.service cron.service jellyfin.service multipathd.service p                                           ackagekit.service polkit.service rsyslog.service ssh.service systemd-journald.service                                            systemd-networkd.service systemd-resolved.service systemd-timesyncd.service systemd-ud                                           evd.service udisks2.service vsftpd.service

Service restarts being deferred:
 systemctl restart ModemManager.service
 /etc/needrestart/restart.d/dbus.service
 systemctl restart getty@tty1.service
 systemctl restart serial-getty@ttyS0.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service

No containers need to be restarted.

User sessions running outdated binaries:
 root @ session #8: apt[2046], sshd[1475]
 root @ session #9: sshd[1494]
 root @ user manager service: systemd[998]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
root@Mahi-Server:~# sudo apt install docker
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package docker is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  wmdocker

E: Package 'docker' has no installation candidate
root@Mahi-Server:~# sudo apt install docker.io
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  linux-headers-6.8.0-87 linux-headers-6.8.0-87-generic linux-image-6.8.0-87-generic
  linux-modules-6.8.0-87-generic linux-tools-6.8.0-87 linux-tools-6.8.0-87-generic
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base pigz runc ubuntu-fan
Suggested packages:
  ifupdown aufs-tools cgroupfs-mount | cgroup-lite debootstrap docker-buildx
  docker-compose-v2 docker-doc rinse zfs-fuse | zfsutils
The following NEW packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base docker.io pigz runc ubuntu-fan
0 upgraded, 8 newly installed, 0 to remove and 4 not upgraded.
Need to get 76.1 MB of archives.
After this operation, 288 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu noble/universe amd64 pigz amd64 2.8-1 [65.6 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 bridge-utils amd64 1.7.1-1ubun                                           tu2 [33.9 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 runc amd64 1.3.3-0ubun                                           tu1~24.04.3 [8815 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 containerd amd64 1.7.2                                           8-0ubuntu1~24.04.2 [38.4 MB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 dns-root-data all 2024                                           071801~ubuntu0.24.04.1 [5918 B]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 dnsmasq-base amd64 2.9                                           0-2ubuntu0.1 [376 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 docker.io amd64 28                                           .2.2-0ubuntu1~24.04.1 [28.3 MB]
Get:8 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 ubuntu-fan all 0.1                                           2.16+24.04.1 [34.2 kB]
Fetched 76.1 MB in 5s (16.8 MB/s)
Preconfiguring packages ...
Selecting previously unselected package pigz.
(Reading database ... 141251 files and directories currently installed.)
Preparing to unpack .../0-pigz_2.8-1_amd64.deb ...
Unpacking pigz (2.8-1) ...
Selecting previously unselected package bridge-utils.
Preparing to unpack .../1-bridge-utils_1.7.1-1ubuntu2_amd64.deb ...
Unpacking bridge-utils (1.7.1-1ubuntu2) ...
Selecting previously unselected package runc.
Preparing to unpack .../2-runc_1.3.3-0ubuntu1~24.04.3_amd64.deb ...
Unpacking runc (1.3.3-0ubuntu1~24.04.3) ...
Selecting previously unselected package containerd.
Preparing to unpack .../3-containerd_1.7.28-0ubuntu1~24.04.2_amd64.deb ...
Unpacking containerd (1.7.28-0ubuntu1~24.04.2) ...
Selecting previously unselected package dns-root-data.
Preparing to unpack .../4-dns-root-data_2024071801~ubuntu0.24.04.1_all.deb ...
Unpacking dns-root-data (2024071801~ubuntu0.24.04.1) ...
Selecting previously unselected package dnsmasq-base.
Preparing to unpack .../5-dnsmasq-base_2.90-2ubuntu0.1_amd64.deb ...
Unpacking dnsmasq-base (2.90-2ubuntu0.1) ...
Selecting previously unselected package docker.io.
Preparing to unpack .../6-docker.io_28.2.2-0ubuntu1~24.04.1_amd64.deb ...
Unpacking docker.io (28.2.2-0ubuntu1~24.04.1) ...
Selecting previously unselected package ubuntu-fan.
Preparing to unpack .../7-ubuntu-fan_0.12.16+24.04.1_all.deb ...
Unpacking ubuntu-fan (0.12.16+24.04.1) ...
Setting up dnsmasq-base (2.90-2ubuntu0.1) ...
Setting up runc (1.3.3-0ubuntu1~24.04.3) ...
Setting up dns-root-data (2024071801~ubuntu0.24.04.1) ...
Setting up bridge-utils (1.7.1-1ubuntu2) ...
Setting up pigz (2.8-1) ...
Setting up containerd (1.7.28-0ubuntu1~24.04.2) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /usr/                                           lib/systemd/system/containerd.service.
Setting up ubuntu-fan (0.12.16+24.04.1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ubuntu-fan.service → /usr/                                           lib/systemd/system/ubuntu-fan.service.
Setting up docker.io (28.2.2-0ubuntu1~24.04.1) ...
info: Selecting GID from range 100 to 999 ...
info: Adding group `docker' (GID 115) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/                                           systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /usr/lib/syst                                           emd/system/docker.socket.
Processing triggers for dbus (1.14.10-4ubuntu4.1) ...
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
 root @ session #8: sshd[1475]
 root @ session #9: sshd[1494]
 root @ user manager service: systemd[998]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
root@Mahi-Server:~# systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; preset: enabled)
     Active: active (running) since Wed 2026-02-04 07:05:27 UTC; 27s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 8438 (dockerd)
      Tasks: 9
     Memory: 21.2M (peak: 21.5M)
        CPU: 390ms
     CGroup: /system.slice/docker.service
             └─8438 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd>

Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.513668642Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.853701639Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.871676845Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.871783776Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.875137845Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.875156410Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.903497613Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.911197812Z" leve>
Feb 04 07:05:27 Mahi-Server dockerd[8438]: time="2026-02-04T07:05:27.911248497Z" leve>
Feb 04 07:05:27 Mahi-Server systemd[1]: Started docker.service - Docker Application C>

root@Mahi-Server:~# man
What manual page do you want?
For example, try 'man man'.
root@Mahi-Server:~# sudo man
What manual page do you want?
For example, try 'man man'.
root@Mahi-Server:~#
