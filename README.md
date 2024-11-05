# IP Sweep Script

This is a simple Bash script that performs a ping sweep across a specified IP range. It checks which hosts are active in a given subnet by sending one ping request to each address in the range and displaying the IPs that respond.

## Usage

### Syntax

```bash
./ipsweep.sh <IP prefix>

\```
### Example

To scan the `192.168.4.x` subnet:

\```bash
./ipsweep.sh 192.168.4
\```

This command will ping each IP from `192.168.4.1` to `192.168.4.254` and list the active IPs in that range.

### Output

The script will print the IP addresses that responded to the ping.

### Requirements

- **Bash**: The script is written in Bash and should run on any Unix-based system with Bash support.
- **ping**: The `ping` utility is required to check the availability of each IP address.

### How It Works

1. The script accepts the first three octets of an IP address as an argument.
2. If no IP prefix is provided, the script displays usage instructions.
3. For each IP address in the specified range (from `.1` to `.254`):
   - It sends one ping request (`ping -c 1`).
   - Filters the response to show only the IPs that replied.
4. The script runs the pings in parallel for faster results using `&` at the end of each command.

### Notes

- Make sure the script has execute permissions:
  \```bash
  chmod +x ipsweep.sh
  \```
- Only IPs that respond will be displayed in the output.

### Disclaimer

This script is for educational and network troubleshooting purposes. Ensure you have permission to scan any network before using this tool.
\```
