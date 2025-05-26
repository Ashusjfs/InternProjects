# Task 1 - Local Network Port Scanning

## Objective
Perform a TCP SYN scan on the local network using Nmap and analyze the packets using Wireshark to understand network exposure and service visibility.

---

## Tools Used
- Nmap (v7.95)
- Wireshark
- Kali Linux

---

## Network Scan Details
- **My IP:** 192.168.164.128
- **Scanned Range:** 192.168.164.0/24
- **Scan Command: nmap -sS 192.168.164.0/24 -oN scan_result.txt

## Observation

### Live Hosts Detected:
- 192.168.164.0  
- 192.168.164.1  
- ...  
- 192.168.164.255

### Open Ports:
- All 1000 scanned ports were **filtered** (no response).
- Likely reasons: firewall protection, no active services, or stealth configurations.

---

## Wireshark Packet Capture

During the scan, Wireshark captured TCP SYN packets sent by Nmap to various hosts.

**Screenshot:**

![Wireshark TCP SYN](Screenshot 2025-05-26 114335.png)

### Filter Applied: tcp.flags.syn == 1 and tcp.flags.ack == 0

This filter shows only the SYN packets that are part of Nmap’s TCP SYN scan.

---

## Files Included

| File Name                          | Description                                  |
|-----------------------------------|----------------------------------------------|
| `scan_result.txt`                 | Raw Nmap scan result                         |
| `Screenshot 2025-05-26 114335.png`| Wireshark screenshot showing SYN packets     |
| `scan_capture.pcapng`             | Full Wireshark packet capture file (optional)|

---

## Conclusion

- Learned to scan a local network and detect hosts/services.
- Understood how firewalls affect visibility of services.
- Observed raw TCP SYN packets using Wireshark for deeper understanding.



