# Networking Concepts: DNS, IP, Subnets & Ports

## Task Done
Build on Day 14 by understanding the building blocks of networking every DevOps engineer must know.

You will:
- Understand how **DNS** resolves names to IPs
  <img width="570" height="338" alt="image" src="https://github.com/user-attachments/assets/22788d1e-9937-49f6-9a7e-1b13293ea0f3" />

- Learn **IP addressing** (IPv4, public vs private)
A public IPv4 address is a globally unique, internet-routable address assigned by ISPs to routers, enabling direct communication over the internet.

Reserved Private IPv4 Address Ranges (RFC 1918)
These ranges are not routable on the public internet: 
Class A: 10.0.0.0 - 10.255.255.255
Class B: 172.16.0.0 - 172.31.255.255
Class C: 192.168.0.0 - 192.168.255.255
  
- Break down **CIDR notation** and **subnetting** basics

CIDR (Classless Inter-Domain Routing) is a compact method for representing IP addresses and their network masks using a slash followed by the number of network bits (e.g., /24) instead of traditional subnet masks (e.g., 255.255.255.0)

Subnet Mask: A 32-bit number (e.g., 255.255.255.0 or /24) that identifies which part of an IP address represents the network and which part represents the host.
  
- Know common **ports** and why they matter

20/21 - FTP (File Transfer Protocol): Used to transfer files between a client and a server.
22 - SSH (Secure Shell): Used for secure remote logins and file transfers.
23 - Telnet: Used for unencrypted remote login (legacy protocol, generally insecure).
25 - SMTP (Simple Mail Transfer Protocol): Used for sending email between servers.
53 - DNS (Domain Name System): Resolves human-readable domain names to IP addresses.
80 - HTTP (Hypertext Transfer Protocol): The foundation of unencrypted web traffic.
110 - POP3 (Post Office Protocol): Used to download emails from a server to a client.
123 - NTP (Network Time Protocol): Used for synchronizing system clocks.
143 - IMAP (Internet Message Access Protocol): Used to manage and retrieve emails from a server.
443 - HTTPS (HTTP Secure): The encrypted version of HTTP, used for secure web traffic.
445 - SMB (Server Message Block): Used for file sharing in Windows networks.
3306 - MySQL: Used for database communication.
3389 - RDP (Remote Desktop Protocol): Allows remote access to a Windows computer.

---

## Challenge Tasks

### Task 1: DNS – How Names Become IPs
1. Explain in 3–4 lines: what happens when you type `google.com` in a browser?

Type google.com and press enter, the browser first uses DNS (Domain Name System) to translate the URL into an IP address to locate Google's server. A secure connection (HTTPS/SSL) is then established, and the browser sends a request to the server, which is handled by a load balancer that distributes traffic to available servers.
   
3. What are these record types? Write one line each:
   - `A`, `AAAA`, `CNAME`, `MX`, `NS`

     definitions for the requested DNS record types:
A (Address): Maps a domain name (or subdomain) directly to an IPv4 address.
AAAA (Quad-A): Maps a domain name directly to an IPv6 address.
CNAME (Canonical Name): Creates an alias that points one domain name to another domain name instead of an IP address.
MX (Mail Exchanger): Directs email to the appropriate mail server for a domain.
NS (Name Server): Defines which authoritative DNS servers are responsible for a domain.

4. Run: `dig google.com` — identify the A record and TTL from the output

   <img width="580" height="355" alt="image" src="https://github.com/user-attachments/assets/9f05f3d3-7d53-47e5-994f-d90b20975081" />


---

### Task 2: IP Addressing
1. What is an IPv4 address? How is it structured? (e.g., `192.168.1.10`)

IPv4 (Internet Protocol version 4) address is a unique, numerical label assigned to each device (computer, printer, smartphone) connected to a computer network that uses the Internet Protocol for communication. It functions as a digital identifier and location address for transmitting data packets.
   
3. Difference between **public** and **private** IPs — give one example of each
4. What are the private IP ranges?
   - `10.x.x.x`, `172.16.x.x – 172.31.x.x`, `192.168.x.x`
5. Run: `ip addr show` — identify which of your IPs are private

---

### Task 3: CIDR & Subnetting
1. What does `/24` mean in `192.168.1.0/24`?
2. How many usable hosts in a `/24`? A `/16`? A `/28`?
3. Explain in your own words: why do we subnet?
4. Quick exercise — fill in:

| CIDR | Subnet Mask | Total IPs | Usable Hosts |
|------|-------------|-----------|--------------|
| /24  | ?           | ?         | ?            |
| /16  | ?           | ?         | ?            |
| /28  | ?           | ?         | ?            |

---

### Task 4: Ports – The Doors to Services
1. What is a port? Why do we need them?
2. Document these common ports:

| Port | Service |
|------|---------|
| 22   | ?       |
| 80   | ?       |
| 443  | ?       |
| 53   | ?       |
| 3306 | ?       |
| 6379 | ?       |
| 27017| ?       |

3. Run `ss -tulpn` — match at least 2 listening ports to their services

---

### Task 5: Putting It Together
Answer in 2–3 lines each:
- You run `curl http://myapp.com:8080` — what networking concepts from today are involved?
- Your app can't reach a database at `10.0.1.50:3306` — what would you check first?

---

## Documentation

Create `day-15-networking-concepts.md` with:
- Your answers to each task
- Command outputs from `dig` and `ss`
- The filled CIDR table
- What you learned (3 key points)

---

## Submission
1. Add `day-15-networking-concepts.md` to `2026/day-15/`
2. Commit and push to your fork

---

## Learn in Public

Share what you learned about DNS, subnets, or ports on LinkedIn.

```
#90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham
```

Happy Learning!
**TrainWithShubham**

