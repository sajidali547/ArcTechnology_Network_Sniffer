# 🔍 Network Traffic Sniffer & Packet Analysis
### Arc Technology Internship — Task 1

## Overview
This project implements a Python-based packet sniffer using **Scapy** and validates the captured network traffic using **Wireshark**. 

The lab demonstrates packet capture and analysis across **ICMP, TCP, HTTP, and DNS** traffic in a controlled environment. This simulates how a SOC Analyst monitors network traffic for anomalies.

## Lab Architecture
- **Capture Host:** Ubuntu Linux (Interface: ens34)
- **Test Endpoint:** Windows VM
- **Tools:** Python, Scapy, Wireshark

## Features
- Real-time packet capture via Scapy.
- Protocol identification (TCP, UDP, ICMP).
- Extracts Source/Destination IPs, Ports, and Payload.
- CSV logging for offline analysis (`captured_packets.csv`).
- Validates findings using Wireshark protocol filters.

## SOC Analyst Findings
- **ICMP:** TTL 128 observed, identifying a Windows OS fingerprint.
- **HTTP:** User-Agent `curl/8.0.1` detected, indicating a scripted client rather than a browser. Server banner also exposed Python version (info-disclosure).
- **DNS:** Windows appended `.localdomain` to queries, a common DNS suffix misconfiguration.

## Screenshots
- `01-sniffer-running.png`: Python script capturing live traffic.
- `02-wireshark-capture.png`: Wireshark validating the HTTP/ICMP packets.

## How to Run
```bash
sudo python3 sniffer.py