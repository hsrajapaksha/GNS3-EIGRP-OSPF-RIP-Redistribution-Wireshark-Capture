## GNS3 Project – EIGRP, OSPF, and RIP with Wireshark

### Project Overview

This project shows how to configure and connect **EIGRP**, **OSPF**, and **RIP** routing protocols in a mixed network using **GNS3**.
Router **R4** works as the redistribution point between all three routing domains.
**Wireshark** is used to capture and analyze **EIGRP Hello**, **OSPF Hello**, and **ICMP** (ping) packets.

---

### Network Topology

<img width="1584" height="618" alt="Screenshot 2025-10-27 112512" src="https://github.com/user-attachments/assets/01af06c7-df17-445a-96d0-d97a13a68405" />

---

### IP Address Plan

| Router | Interface | IP Address    |
| ------ | --------- | ------------- |
| R1     | G1/0      | 10.10.10.1    |
| R1     | G0/0      | 172.16.10.1   |
| R2     | G0/0      | 10.10.10.2    |
| R2     | G1/0      | 10.10.11.1    |
| R2     | G3/0      | 10.10.12.2    |
| R3     | G1/0      | 10.10.11.2    |
| R3     | G0/0      | 192.168.10.1  |
| R4     | G0/0      | 10.10.12.1    |
| R4     | G1/0      | 10.10.13.1    |
| R4     | G2/0      | 10.10.14.1    |
| R5     | G0/0      | 10.10.13.2    |
| R5     | G1/0      | 192.168.100.1 |
| R6     | G0/0      | 10.10.14.2    |
| R6     | G1/0      | 192.168.200.1 |

---

### Routing Setup

* **R1, R2, R3** → EIGRP (AS 100)
* **R4** → OSPF Area 0 (with redistribution)
* **R5, R6** → RIP v2
* **R4** redistributes routes between **EIGRP**, **OSPF**, and **RIP**

---

### Wireshark Verification

Captured packets:

* **EIGRP Hello** → between R1 and R2
* **OSPF Hello** → between R2 and R4
* **ICMP (ping)** → between R1 and R6

Wireshark filters:

```
eigrp
ospf
icmp
```

---

### Results

✅ All routers successfully exchanged routes
✅ Full connectivity verified using ping
✅ EIGRP, OSPF, and ICMP packets captured in Wireshark

---

### Project Files

All project files (GNS3 topology, configurations, captures, and screenshots) are available here:
👉 [Google Drive Project Folder](https://drive.google.com/file/d/13C6pZQNUdYY7fITZym1SoSOXNR-wsnlF/view?usp=sharing)

---

### Author

**H.Rajapaksha**
GNS3 Network Simulation Project – EIGRP, OSPF, RIP with Wireshark Analysis


