## DNS Spoofer

A Python script that performs DNS spoofing, redirecting requests from specified domains to a different IP address.

### Features

- Intercepts DNS requests and responds with a specified IP address
- Allows redirection of target domains (e.g., www.bing.com) to a custom server

### Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Daniel-Ikenna/dns_spoof
   ```

2. **Configure Target Domain and IP**:
   Modify the script to replace `"www.bing.com"` and the IP address (`"192.168.*.*"`) with your desired domain and IP.

3. **Set Up iptables**:
   Before running the script, add an iptables rule to send packets to the netfilter queue:
   ```bash
   sudo iptables -I FORWARD -j NFQUEUE --queue-num 0
   ```

4. **Run the Script**:
   ```bash
   sudo python dns_spoofer.py
   ```

5. **Reset iptables**:
   After use, clear the iptables rule:
   ```bash
   sudo iptables --flush
   ```

### Requirements

- Python 3.x
- `scapy` and `netfilterqueue` libraries (install with `pip install scapy netfilterqueue`)
- Superuser privileges (use `sudo`)

### Important Note

This tool is strictly for educational purposes. Do not use on networks or domains without permission.

### Authors

- [Zaid Sabih](https://ie.linkedin.com/in/zaid-sabih-al-quraishi-5444a6127)
- [Uzoeshi Daniel](https://www.linkedin.com/in/daniel-ikenna-33b709235)
