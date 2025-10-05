# Firewall-Simulator

# Firewall-Simulator

A simple Python-based firewall simulator that demonstrates basic IP filtering logic.

## Features

- Simulates random IP address generation within a local network range.
- Applies firewall rules to block or allow specific IP addresses.
- Displays the action taken for each IP (block/allow) along with a random identifier.

## How It Works

The simulator generates random IP addresses in the range `192.168.1.0` to `192.168.1.5`. It checks each IP against a set of firewall rules defined in the code. If the IP matches a rule, the specified action (e.g., "block") is applied; otherwise, the IP is allowed.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/Firewall-Simulator.git
    cd Firewall-Simulator
    ```

2. Run the simulator:
    ```bash
    python firewall.py
    ```

## Example Output

```
IP: 192.168.1.2, Action: block, Random: 1234
IP: 192.168.1.5, Action: allow, Random: 5678
...
Blocking IP: 192.168.1.100, packet_rate: 45.0
```

## File Structure

- [`firewall.py`](firewall.py): Main simulation script.

## Customization

You can modify the `firewall_rules` dictionary in [`firewall.py`](firewall.py) to change which IPs are blocked or allowed.

---

Feel free to use and modify this project for educational purposes!


# DoS Blocker

This script is a simple Denial-of-Service (DoS) attack detection and prevention tool written in Python. It uses the Scapy library to monitor network traffic and automatically blocks IP addresses that exceed a specified packet rate threshold.

## Features

- Monitors incoming network packets in real time.
- Tracks the number of packets received from each IP address.
- Calculates the packet rate for each IP over one-second intervals.
- Automatically blocks IPs that exceed the defined packet rate threshold using `iptables`.
- Prints alerts when an IP is blocked.

## How It Works

1. The script listens for IP packets on the network interface.
2. For each packet, it increments a counter for the source IP.
3. Every second, it calculates the packet rate for each IP.
4. If an IP's packet rate exceeds the threshold (default: 40 packets/second), the script blocks that IP using the system firewall (`iptables`).
5. Blocked IPs are tracked to avoid repeated blocking.

## Usage

> **Note:** This script requires root privileges and is intended for Linux systems with `iptables` installed.

1. Install dependencies:
    ```bash
    pip install scapy
    ```

2. Run the script with root privileges:
    ```bash
    sudo python dos-blocker.py
    ```

3. The script will print the threshold and begin monitoring:
    ```
    THRESHOLD: 40
    monitoring network traffic...
    Blocking IP: 192.168.1.100, packet_rate: 45.0
    ```

## Customization

- Change the `THRESHOLD` variable at the top of the script to adjust sensitivity.
- Modify the packet filter in the `sniff()` function if you want to monitor other protocols.

## Disclaimer

This script is for educational and demonstration purposes only. Use responsibly and ensure you have permission to monitor and block traffic on your network.

---
```# DoS Blocker

This script is a simple Denial-of-Service (DoS) attack detection and prevention tool written in Python. It uses the Scapy library to monitor network traffic and automatically blocks IP addresses that exceed a specified packet rate threshold.

## Features

- Monitors incoming network packets in real time.
- Tracks the number of packets received from each IP address.
- Calculates the packet rate for each IP over one-second intervals.
- Automatically blocks IPs that exceed the defined packet rate threshold using `iptables`.
- Prints alerts when an IP is blocked.

## How It Works

1. The script listens for IP packets on the network interface.
2. For each packet, it increments a counter for the source IP.
3. Every second, it calculates the packet rate for each IP.
4. If an IP's packet rate exceeds the threshold (default: 40 packets/second), the script blocks that IP using the system firewall (`iptables`).
5. Blocked IPs are tracked to avoid repeated blocking.

## Usage

> **Note:** This script requires root privileges and is intended for Linux systems with `iptables` installed.

1. Install dependencies:
    ```bash
    pip install scapy
    ```

2. Run the script with root privileges:
    ```bash
    sudo python dos-blocker.py
    ```

3. The script will print the threshold and begin monitoring:
    ```
    THRESHOLD: 40
    monitoring network traffic...
    Blocking IP: 192.168.1.100, packet_rate: 45.0
    ```

## Customization

- Change the `THRESHOLD` variable at the top of the script to adjust sensitivity.
- Modify the packet filter in the `sniff()` function if you want to monitor other protocols.

## Disclaimer

This script is for educational and demonstration purposes only. Use responsibly and ensure you have permission to monitor and block traffic on your network.

---

# Packet Flooding Script

This script demonstrates how to send a burst of TCP packets to a target IP address using the Scapy library. It can be used for testing network resilience, firewall rules, or DoS protection mechanisms.

## Features

- Sends a specified number of TCP packets to a target IP address.
- Allows you to set the target IP, network interface, number of packets, and duration.
- Uses Scapy for packet crafting and sending.

## How It Works

The script creates a TCP packet and sends it repeatedly to the target IP address over the specified network interface. The sending continues until either the desired number of packets is sent or the duration (in seconds) has elapsed.

## Usage

> **Note:** This script requires root privileges and is intended for educational/testing purposes only.

1. Install Scapy:
    ```bash
    pip install scapy
    ```

2. Edit the script:
    - Replace `TARGET_IP` with the IP address you want to target.
    - Replace `INTERFACE` with your network interface name (e.g., `eth0`, `wlan0`).

3. Run the script with Python 3 and root privileges:
    ```bash
    sudo python packet-flooding.py
    ```

## Parameters

- `TARGET_IP`: The destination IP address for the packets.
- `INTERFACE`: The network interface to use for sending packets.
- `NUM_PACKETS`: Maximum number of packets to send.
- `DURATION`: Maximum duration (in seconds) to send packets.

## Example

```
Sending up to 100 TCP packets to 192.168.1.10 over eth0 for 5 seconds.
```

## Disclaimer

This script is for educational and testing purposes only. Do not use it to attack or disrupt networks without explicit permission.

---
```# Packet Flooding Script

This script demonstrates how to send a burst of TCP packets to a target IP address using the Scapy library. It can be used for testing network resilience, firewall rules, or DoS protection mechanisms.

## Features

- Sends a specified number of TCP packets to a target IP address.
- Allows you to set the target IP, network interface, number of packets, and duration.
- Uses Scapy for packet crafting and sending.

## How It Works

The script creates a TCP packet and sends it repeatedly to the target IP address over the specified network interface. The sending continues until either the desired number of packets is sent or the duration (in seconds) has elapsed.

## Usage

> **Note:** This script requires root privileges and is intended for educational/testing purposes only.

1. Install Scapy:
    ```bash
    pip install scapy
    ```

2. Edit the script:
    - Replace `TARGET_IP` with the IP address you want to target.
    - Replace `INTERFACE` with your network interface name (e.g., `eth0`, `wlan0`).

3. Run the script with Python 3 and root privileges:
    ```bash
    sudo python packet-flooding.py
    ```

## Parameters

- `TARGET_IP`: The destination IP address for the packets.
- `INTERFACE`: The network interface to use for sending packets.
- `NUM_PACKETS`: Maximum number of packets to send.
- `DURATION`: Maximum duration (in seconds) to send packets.

## Example

```
Sending up to 100 TCP packets to 192.168.1.10 over eth0 for 5 seconds.
```

## Disclaimer

This script is for educational and testing purposes only. Do not use it to attack or disrupt networks without explicit permission.

---