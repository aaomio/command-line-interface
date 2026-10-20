## Ping Command Comparison

| Function | Linux (`iputils`) | Windows CMD | Cisco IOS |
|---|---|---|---|
| **Request count** | `-c <count>` | `-n <count>` | Extended ping: `Repeat count` |
| **Packet size** | `-s <bytes>` | `-l <bytes>` | Extended ping: `Datagram size` |
| **TTL** | `-t <TTL>` | `-i <TTL>` | Extended ping: `TTL` (where supported) |
| **Disable reverse DNS lookup** | `-n` | No direct equivalent in standard `ping` | Depends on IOS configuration and output |
| **Flood / continuous ping** | `-f` (requires root privileges) | `-t` (continuous ping until interrupted) | No direct equivalent to Linux flood mode |

