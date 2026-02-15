# Network Sniffer

A lightweight, terminal-based packet sniffer built with Python and Scapy. It features colored output, HTTP request parsing, raw payload previews, and a custom ASCII-art boot sequence.

Created by **The-R34per**.

---

## Overview

This tool captures live network traffic from a specified interface and displays:

- Source and destination IP addresses  
- Protocol numbers  
- HTTP request details (method, host, path)  
- Raw payload bytes (first 100 bytes)

It is designed for learning, debugging, and exploring network behavior in real time.

---

## Features

- Real-time packet capture  
- HTTP request detection  
- Raw payload extraction  
- Colored terminal output  
- Custom ASCII-art banner and loading sequence  
- Optional BPF filters (e.g., `tcp port 80`)  
- Command-line interface using `argparse`

---

## Requirements

You will need:

- Python 3.x  
- Scapy  
- Root or administrator privileges (required for packet sniffing)

Install Scapy:

```bash
pip install scapy
```

---

## Usage

Basic network sniffing:
```
sudo python3 NetworkSniffer.py -i <interface>
```

Example:
```
sudo python3 NetworkSniffer.py -i en0
```

With BPF Filter:
```
sudo python3 NetworkSniffer.py -i eth0 -f "tcp port 80"
```

---

## Common Filters

Only HTTP	=> "tcp port 80"
Only HTTPS =>	"tcp port 443"
Only DNS =>	"udp port 53"
Only TCP =>	"tcp"
Only UDP =>	"udp"

---

## How it Works

The script uses Scapy’s sniff() function with a callback (process_packet) to:
- Inspect IP layer fields
- Detect HTTP requests via HTTPRequest
- Extract raw payloads via Raw
- Print formatted output to the terminal
All packets are processed live and never stored.

---

## Disclaimer

This tool is for educational and authorized testing purposes only.
Do not sniff networks you do not own or have explicit permission to analyze.
The author of this tool is not responible for your actions.

---

## License

Python Network Sniffer  © 2026 by The-R34per is licensed under CC BY-SA 4.0. To view a copy of this license, visit https://creativecommons.org/licenses/by-sa/4.0/
