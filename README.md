# Wireshark-packet-analysis

##  Overview
This repository contains a Wireshark packet capture and analysis performed and the goal was to capture live network traffic, filter it by different protocols, and analyze key packet details.

---

## 🛠 Tools Used
- **Wireshark** (latest version)
- OS: Linux (Kali)
- Network Interface: wlan0

---

## 📋 Steps Performed
1. Installed Wireshark on the system.
2. Selected the active network interface (**eth0**).
3. Started a live capture.
4. Generated traffic by:
   - Visiting websites (amazon.com)
   - Using curl and ping commands
5. Applied protocol filters:
   - `dns`
   - `http`
   - `tcp`
6. Stopped the capture after ~1 minute.
7. Saved the capture file as `network_capture.pcap`.
8. Took screenshots of each filter view.

---

## 🔍 Protocols Identified
| Protocol | Purpose | Example |
|----------|---------|---------|
| DNS      | Resolves domain names to IP addresses | Query for `amazon.com` |
| HTTP     | Transfers unencrypted web data | GET request to `success.txt` |
| TCP      | Reliable transport protocol for data | Connection setup (SYN, ACK) to port 443 |

---

## 📸 Screenshots
- `dns-filter.png` – DNS queries and responses
- `http-filter.png` – HTTP requests and responses
- `tcp-filter.png` – TCP handshake and data transfer

---

##  Learning Outcomes
- Learned how to capture and filter packets in Wireshark.
- Understood the difference between DNS, HTTP, and TCP layers.
- Observed packet details such as source/destination IPs and ports.
- Saw how DNS queries precede HTTP/TCP communication.
