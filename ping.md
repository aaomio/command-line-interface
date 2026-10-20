## Ping Command Comparison

| Function | Linux (`iputils`) | Windows CMD | Cisco IOS |
|---|---|---|---|
| **Request count** | `-c <count>` | `-n <count>` | Extended ping: `Repeat count` |
| **Packet size** | `-s <bytes>` | `-l <bytes>` | Extended ping: `Datagram size` |
| **TTL** | `-t <TTL>` | `-i <TTL>` | Extended ping: `TTL` (where supported) |
| **Disable reverse DNS lookup** | `-n` | No direct equivalent in standard `ping` | Depends on IOS configuration and output |
| **Flood / continuous ping** | `-f` (requires root privileges) | `-t` (continuous ping until interrupted) | No direct equivalent to Linux flood mode |

### Notes

- Linux `-c` and Windows `-n` specify the number of echo requests.
- Linux `-s` and Windows `-l` specify the data payload size in bytes.
- Linux `-t` specifies the TTL, whereas Windows `-t` sends continuous echo requests until interrupted with `Ctrl+C`.
- Linux `-n` disables hostname resolution; Windows `-n` specifies the request count.
- Cisco IOS extended ping provides interactive options such as repeat count, datagram size and TTL, depending on platform support.
- **Continuous ping is not the same as flood mode:** Windows `-t` continuously sends requests, while Linux `-f` sends them as rapidly as possible.
