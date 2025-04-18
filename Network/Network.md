# 🌐 Internet Networks

## 📖 Table of Contents

1. What is the internet?
2. TCP/IP 4-Layer Model
3. Common Communication Protocols（HTTP、HTTPS、FTP…）
4. Basic Network Security Concepts
5. Tools & Practical Recommendations

---

## 1️⃣ What is the Internet?

The internet is a global network made up of billions of interconnected devices. Its main purposes are data transmission and resource sharing.

- Based on a set of shared **communication protocols**
- Data is transmitted in **packets**
- Essentially, it's a **network of networks**

---

## 2️⃣ TCP/IP Model (4-Layer Architecture)

| Layer                   | Function                                   | Examples              |
|-------------------------|--------------------------------------------|-----------------------|
| Application Layer       | Provides network services to applications        | HTTP, FTP, DNS  |
| Transport Layer         | Ensures reliable data transmission               | TCP, UDP        |
| Internet Layer          | Handles routing and addressing of data           | IP              |
| Network Interface Layer | Deals with physical transmission, NICs, drivers  | Ethernet, Wi-Fi |

---

## 3️⃣ Common Communication Protocols

| Protocol | Function                            | Notes                             |
|----------|-------------------------------------|-----------------------------------|
| HTTP     | Web page transfer protocol          | Not encrypted                     |
| HTTPS    | Secure version of HTTP              | Uses SSL/TLS encryption           |
| FTP      | File Transfer Protocol              | Common for server file access     |
| DNS      | Domain name resolution protocol     |                                   |
| TCP      | Ensures reliable, ordered delivery  |                                   |
| UDP      | Fast transmission, no guarantee     | Ideal for real-time communication |

---

## 4️⃣ Basic Network Security Concepts

- **Firewall**：Filters packets, blocks malicious connections
- **Encryption（SSL/TLS）**：Protects data from interception
- **VPN（Virtual Private Network）**：Creates encrypted tunnels for privacy
- **DDoS Attack**：Overwhelms servers with massive traffic

---

## 5️⃣ Tools & Practical Recommendations

| Tool         | Function                                   |
|--------------|--------------------------------------------|
| `ping`       | Checks if a host is reachable              |
| `tracert` / `traceroute` | Displays the path data travels |
| `nslookup`   | Queries DNS records                        |
| Wireshark    | Packet capturing and analysis tool         |
| Packet Tracer| Network device and topology simulator      |

---

> 📌 Lecture notes by Tony Kang. Feel free to share or reference — please credit or link back to the Github 🙌
