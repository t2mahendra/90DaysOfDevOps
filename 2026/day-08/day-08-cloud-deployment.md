
**Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment**

**Task Done**

Launch a cloud instance (AWS EC2 or Utho)
Connect via SSH
Install Nginx
Configure security groups for web access (port 80 by default for nginx)
Extract and save logs to a file
Verify your webpage is accessible from the internet

Expected Output
By the end of today, you should have:

A markdown file named: day-08-cloud-deployment.md
Screenshots showing:
SSH connection to your server
Nginx welcome page accessible from browser
Log file contents
The log file: nginx-logs.txt

SSH connection

<img width="333" height="292" alt="image" src="https://github.com/user-attachments/assets/ad7f69aa-f71a-4254-9a6f-da94b216716c" />

Nginx welcome page accessible from browser

<img width="508" height="318" alt="image" src="https://github.com/user-attachments/assets/e61f5cc3-6c48-4b78-896a-96cf4c9ca4b5" />

root@Mahi-Server:/var/log# ll
total 8304
drwxrwxr-x  11 root      syslog             4096 Feb  6 11:53 ./
drwxr-xr-x  14 root      root               4096 Feb  5 09:29 ../
lrwxrwxrwx   1 root      root                 39 Oct 31 18:23 README -> ../../usr/share/doc/systemd/README.logs
drwxr-xr-x   2 root      adm                4096 Feb  5 09:29 nginx/
root@Mahi-Server:/var/log# cd nginx/
root@Mahi-Server:/var/log/nginx# ll
total 16
drwxr-xr-x  2 root     adm    4096 Feb  5 09:29 ./
drwxrwxr-x 11 root     syslog 4096 Feb  6 11:53 ../
-rw-r-----  1 www-data adm    2502 Feb  6 12:24 access.log
-rw-r-----  1 www-data adm      76 Feb  5 09:29 error.log
root@Mahi-Server:/var/log/nginx#

Part 1: Launch Cloud Instance & SSH Access (15 minutes)

Step 1: Create a Cloud Instance

Ubuntu serber has been created on utho cloud.

Step 2: Connect via SSH

SSH has been connected with putty.


Part 2: Install Docker & Nginx (20 minutes)
Step 1: Update System
Step 3: Install Nginx

Installed 

http://150.241.245.184/

Part 4: Extract Nginx Logs (15 minutes)
Step 1: View Nginx Logs

Step 2: Save Logs to File

Step 3: Download Log File to Your Local Machine

root@Mahi-Server:/var/log/nginx# scp root@150.241.245.184:~/nginx-logs.txt
usage: scp [-346ABCOpqRrsTv] [-c cipher] [-D sftp_server_path] [-F ssh_config]
           [-i identity_file] [-J destination] [-l limit] [-o ssh_option]
           [-P port] [-S program] [-X sftp_option] source ... target
root@Mahi-Server:/var/log/nginx#
root@Mahi-Server:/var/log/nginx#

Happy Learning 

Mahendra





