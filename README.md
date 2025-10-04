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

## File Structure

- [`firewall.py`](firewall.py): Main simulation script.

## Customization

You can modify the `firewall_rules` dictionary in [`firewall.py`](firewall.py) to change which IPs are blocked or allowed.

---

Feel free to use and modify this project for educational purposes!