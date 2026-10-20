## Traceroute Command Comparison

| Function | Linux (`traceroute`) | Windows CMD (`tracert`) | Cisco IOS |
|---|---|---|---|
| **Disable reverse DNS lookup** | `-n` | `-d` | `numeric` |
| **Probe count per hop** | `-q <count>` |  | `Probe count` |
| **Use IPv4** | `-4` | `-4` |  |
| **Use IPv6** | `-6` | `-6` | `traceroute ipv6` |
