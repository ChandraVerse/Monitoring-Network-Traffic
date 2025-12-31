# Monitoring-Network-Traffic

 🔍 Monitoring Network Traffic with Wireshark – SOC Lab

This lab demonstrates how to monitor and analyze network traffic using Wireshark, focusing on TCP, UDP, ports, HTTP, DNS, and IP addresses from a Security Operations Center (SOC) perspective.📡

 🎯 Objectives

- Capture live network traffic on a Linux VM using Wireshark.
- Analyze TCP and UDP flows, including the TCP three-way handshake.
- Inspect HTTP requests/responses and DNS queries/responses.
- Understand IP addresses, ports, and the concept of open vs closed ports.
- Document observations like a SOC analyst.🛡️

 🧪 Lab Environment

- OS: Linux VM (e.g., Kali/Ubuntu) running in Oracle VirtualBox.
- Tool: Wireshark (GUI) for packet capture and analysis.[page:1][web:20]
- Interface: `eth0` selected as capture interface.
- Typical client IP: `10.0.2.15` (VM).
- Example servers:
  - DNS server: `10.0.2.3`
  - Web server: `34.107.221.82` (Firefox connectivity check).[page:1]

 🧵 High‑Level Workflow

1. Start Wireshark and select `eth0`.
2. Begin capture and apply display filters:
   - DNS: `dns` or `udp.port == 53`
   - HTTP: `http`
   - Web TCP: `tcp.port == 80`
3. In the browser, visit a test site like `http://detectportal.firefox.com/success.txt` to generate traffic.
4. Observe:
   - DNS queries and responses between `10.0.2.15` and `10.0.2.3`.
   - TCP three‑way handshake and data flow between `10.0.2.15` and `34.107.221.82`.
   - HTTP GET and HTTP 200 OK messages.
5. Stop capture and save the `.pcapng` file.

 🧠 Key Concepts (Quick Glossary)

- **Wireshark** – Open‑source network protocol analyzer used to capture and inspect packets for troubleshooting and security monitoring.
- **TCP** – Reliable, connection‑oriented transport protocol that guarantees ordered delivery using sequence numbers and acknowledgments.
- **UDP** – Connectionless, best‑effort transport protocol used where speed matters more than reliability (e.g., DNS).
- **TCP Three‑Way Handshake** – SYN → SYN‑ACK → ACK sequence used to establish a reliable TCP connection.
- **Port** – Logical endpoint that identifies an application on a host; well‑known ports 0–1023 include HTTP 80, HTTPS 443, DNS 53.
- **Open Port** – A port with a listening service that responds normally (e.g., TCP SYN‑ACK).  
- **Closed Port** – No listening service; host typically replies with TCP RST or no response.
- **HTTP** – Application‑layer protocol for web communication over TCP, using methods like GET and POST.
- **DNS** – Domain Name System that translates domain names (e.g., `example.com`) to IP addresses.
- **IP Address** – Numerical address (IPv4/IPv6) used by routers to deliver packets between source and destination.

 📂 Repo Structure

- README.md – This file.
- report.md – Detailed analysis and explanations.
- screenshots – Wireshark screenshots for DNS, HTTP, and TCP sessions.

 ✅ Learning Outcomes

After completing this lab you should be able to:

- Use Wireshark filters to isolate specific protocols.
- Visually trace DNS, TCP, and HTTP flows.
- Explain open vs closed ports using TCP flags.
- Write a basic SOC‑style network traffic report.💼
