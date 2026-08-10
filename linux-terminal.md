# Linux Command Reference

A structured reference of common Linux commands with sudo equivalents.

## Network Configuration

```bash
sudo hostname                                      # Show hostname
sudo ifconfig                                      # Show all network interfaces
sudo ifconfig enp0s8                               # Show enp0s8 configuration
sudo ifconfig enp0s8 192.168.1.1 netmask 255.255.255.0 broadcast 192.168.1.255
                                                     # Assign IP, subnet mask and broadcast address
sudo ifconfig enp0s8 up                            # Enable interface
```

### Default Route

```bash
sudo route add default gw <GATEWAY>                # Add default gateway
```

Example:

```bash
sudo route add default gw 192.168.1.254
```

> `enp0s8` is the interface name. Check the exact name with `ifconfig` or `ip addr`.

---

# Snort

## Installation

```bash
sudo apt update && sudo apt upgrade -y             # Update package lists and upgrade packages
sudo apt install snort -y                          # Install Snort
```

## Verify Snort

```bash
snort -V                                           # Show Snort version
```

## Packet Capture

```bash
sudo snort -i enp0s8 -v                            # Capture packets verbosely on interface enp0s8
```

## Local Rules

Edit the local rule file:

```bash
sudo nano /etc/snort/rules/local.rules
```

Example TCP rule:

```text
alert tcp any any -> 192.168.1.0/24 any (msg:"TCP Packet Detected"; sid:1000001; rev:1;)
```

```text
alert             # Generate an alert
tcp               # Match TCP traffic
any any           # Any source IP and source port
->                # Traffic direction
192.168.1.0/24    # Destination network
any               # Any destination port
msg               # Alert message
sid               # Snort rule ID
rev               # Rule revision
```

## Run Snort with Configuration

```bash
sudo snort -A console -i enp0s8 -c /etc/snort/snort.conf
                                                     # Run Snort and display alerts in console
```

Test the configuration before running:

```bash
sudo snort -T -c /etc/snort/snort.conf             # Test Snort configuration and rules
```

---

# hping3

## Installation

```bash
sudo apt install hping3 -y                         # Install hping3
```

## Create Payload

```bash
echo -e "\r\n" > payload1                          # Create a file containing CR/LF
```

> `echo -e` interprets escape sequences. `\r` = carriage return and `\n` = line feed.

## Example hping3

```bash
sudo hping3 -a <SOURCE-IP> -p <DEST-PORT> -s <SOURCE-PORT> \
-d <DATA-SIZE> -c 1 -E payload1 <DESTINATION-IP>
```

Example:

```bash
sudo hping3 -a 192.168.1.65 -p 80 -s 12345 \
-d 2 -c 1 -E payload1 192.168.1.1
```

```text
-a              # Spoof source IP
-p              # Destination port
-s              # Source port
-d              # Data size
-c 1            # Send one packet
-E payload1     # Read packet data from payload1
```

---

# UFW

## Status

```bash
sudo ufw status                                   # Show UFW status
sudo ufw status verbose                           # Show detailed status
sudo ufw status numbered                          # Show numbered rules
```

## Disable / Enable

```bash
sudo ufw disable                                  # Disable firewall
sudo ufw enable                                   # Enable firewall
```

## Allow SSH from a Network

```bash
sudo ufw allow from 192.168.1.0/24 to any port 22 proto tcp
                                                     # Allow SSH from network
```

## Block Telnet

```bash
sudo ufw deny from any to any port 23 proto tcp   # Block TCP Telnet
```

## Block TCP Port from a Subnet

```bash
sudo ufw deny from 192.168.1.64/26 to any port 80 proto tcp
                                                     # Block TCP port 80 from subnet
```

## Monitor UFW Logs

```bash
sudo tail -f /var/log/ufw.log                     # Follow UFW log in real time
```

