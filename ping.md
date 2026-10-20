## Ping Command Comparison

| Function | Linux (`iputils`) | Windows CMD | Cisco IOS |
|---|---|---|---|
| **Request count** | `-c <count>` | `-n <count>` | `repeat <count>` |
| **Packet size** | `-s <bytes>` | `-l <bytes>` | `size <bytes>` |
| **TTL** | `-t <TTL>` | `-i <TTL>` | `hops <TTL>`|
| **Resolve address to hostname** |  | `-a` |  |
| **Flood / continuous ping** | `-f` | `-t` |  |

