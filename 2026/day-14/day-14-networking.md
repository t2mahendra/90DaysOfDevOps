# Networking Fundamentals & Hands-on Checks

## Task Done
Get comfortable with core networking concepts and the commands you’ll actually run during troubleshooting.

You will:
- Map the **OSI vs TCP/IP models** in your own words
  ![Screenshot 2026-02-19 211732](https://github.com/user-attachments/assets/e396b847-9b53-40d0-9165-343c74789222)

- Run essential connectivity commands
  ping
  ipconfig
  ifconfig
  ip a
  
- Capture a mini network check for a target host/service
<img width="471" height="212" alt="image" src="https://github.com/user-attachments/assets/559662fe-6d51-4938-984e-15b7179e4bf8" />


## Quick Concepts (write 1–2 bullets each)

- OSI layers (L1–L7) vs TCP/IP stack (Link, Internet, Transport, Application)
- OSI Layer 7-5 (Application, Presentation, Session) 
 TCP/IP Application Layer: Handles user interfaces, data formatting, encryption, and session management.
OSI Layer 4 (Transport) 
 TCP/IP Transport Layer: Manages end-to-end communication, flow control, and error correction (TCP/UDP).
OSI Layer 3 (Network) 
 TCP/IP Internet Layer: Handles logical addressing (IP addresses) and routing of packets across networks.
OSI Layer 2-1 (Data Link, Physical) 
 TCP/IP Link Layer: Manages physical transmission, MAC addressing, and hardware interfacing.

- Where **IP**, **TCP/UDP**, **HTTP/HTTPS**, **DNS** sit in the stack

HTTP/HTTPS -	Application	Defines web browser communication (data transfer)
DNS	- Application	Translates domain names to IP addresses
TCP/UDP -	Transport	Manages data flow and connections
IP - Internet	Routes packets to the correct destination
  
- One real example: “`curl https://example.com` = App layer over TCP over IP”
  <img width="1007" height="409" alt="image" src="https://github.com/user-attachments/assets/83283bbc-0fe8-4aff-ab9d-fc6009520589" />

## Hands-on Checklist (run these; add 1–2 line observations)
- **Identity:** `hostname -I` (or `ip addr show`) — note your IP.
  <img width="884" height="333" alt="image" src="https://github.com/user-attachments/assets/4596daa7-ba2c-4301-98e0-c43486de15a2" />

- **Reachability:** `ping <target>` — mention latency and packet loss.
<img width="808" height="250" alt="image" src="https://github.com/user-attachments/assets/2a6190ce-cb47-40fe-8c82-bb1ae025664c" />

- **Path:** `traceroute <target>` (or `tracepath`) — note any long hops/timeouts.
<img width="628" height="172" alt="image" src="https://github.com/user-attachments/assets/de8aea51-825e-4523-9a58-c56cf5173d88" />
 
- **Ports:** `ss -tulpn` (or `netstat -tulpn`) — list one listening service and its port.
<img width="997" height="369" alt="image" src="https://github.com/user-attachments/assets/1c1287c2-1e57-4e9c-ab3a-afabc5fbd837" />
 
- **Name resolution:** `dig <domain>` or `nslookup <domain>` — record the resolved IP.
  <img width="562" height="331" alt="image" src="https://github.com/user-attachments/assets/e781719d-9529-4091-af47-1912f5cd82c0" />

- **HTTP check:** `curl -I <http/https-url>` — note the HTTP status code.
<img width="1014" height="260" alt="image" src="https://github.com/user-attachments/assets/18e8d2e9-c4f9-4b25-9ba3-4925a6a2084f" />

- **Connections snapshot:** `netstat -an | head` — count ESTABLISHED vs LISTEN (rough).
  <img width="681" height="437" alt="image" src="https://github.com/user-attachments/assets/e384388a-b44c-414a-aa55-e30c21af8844" />

Pick one target service/host (e.g., `google.com`, your lab server, or a local service) and stick to it for ping/traceroute/curl where possible.

---

## Mini Task: Port Probe & Interpret
1) Identify one listening port from `ss -tulpn` (e.g., SSH on 22 or a local web app).
   <img width="993" height="358" alt="image" src="https://github.com/user-attachments/assets/f409fe1d-be28-4340-9484-dfee23acc0f8" />

3) From the same machine, test it: `nc -zv localhost <port>` (or `curl -I http://localhost:<port>`).
<img width="628" height="139" alt="image" src="https://github.com/user-attachments/assets/2bba28bf-630a-4b02-8987-4885453827e0" />

5) Write one line: is it reachable? If not, what’s the next check? (e.g., service status, firewall).
<img width="756" height="186" alt="image" src="https://github.com/user-attachments/assets/b75f3e76-8ca9-4fca-b76f-521fd294a43f" />


---

## Reflection (add to your markdown)
- Which command gives you the fastest signal when something is broken?
- What layer (OSI/TCP-IP) would you inspect next if DNS fails? If HTTP 500 shows up?
- Two follow-up checks you’d run in a real incident.

---

## Submission
1. Add `day-14-networking.md` to `2026/day-14/`
2. Commit and push to your fork

---

## Learn in Public
Post 2–3 lines on the commands you practiced and one interesting traceroute/curl finding.

Use hashtags:  
#90DaysOfDevOps  
#DevOpsKaJosh  
#TrainWithShubham

Happy Learning  
**TrainWithShubham**
