#  Wireshark Packet Analysis Report

##  Objective
The objective was to capture network packets, apply protocol-specific filters, and analyze the communication flow and key packet details.

---

##  Protocols and Observations

###  DNS
- **Purpose:** Domain Name System resolves human-readable names to IP addresses.
- **Example Packet:**
  - **Source IP:** 192.168.31.114
  - **Destination IP:** 192.168.31.1
  - **Query:** `amazon.com`
  - **Response:** A record → 52.94.236.248, 54.239.28.85
- **Notes:** Multiple queries to domains such as `mozilla.com` and `amazon.com` were observed.

---

###  HTTP
- **Purpose:** HyperText Transfer Protocol used for web page data transfer.
- **Example Packet:**
  - **Source IP:** 192.168.31.114
  - **Destination IP:** 34.107.221.82
  - **Request:** `GET /success.txt?ipv4 HTTP/1.1`
  - **Response:** HTTP/1.1 200 OK (text/plain)
- **Notes:** Traffic was unencrypted and readable in Wireshark.

---

###  TCP
- **Purpose:** Transmission Control Protocol provides reliable, ordered delivery of packets.
- **Example Packet:**
  - **Source IP:** 192.168.31.114
  - **Destination IP:** 34.107.243.93
  - **Flags:** SYN → initiating handshake on port 443
- **Notes:** TCP was used for both HTTP and HTTPS sessions, with visible handshake sequences.

---

##  Summary
- DNS queries were used to resolve target websites before HTTP/TCP communication.
- HTTP traffic was captured and showed unencrypted requests/responses.
- TCP flows included both control (handshake) and application data.

---

##  Recommendations
- Use HTTPS instead of HTTP to prevent unencrypted data transfer.
- Monitor DNS queries for suspicious domains.
- Capture TCP/UDP metadata for threat hunting.

---

## 📸 Screenshots
- `dns-filter.png`
- `http-filter.png`
- `tcp-filter.png`
