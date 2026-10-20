## Traceroute Command Comparison

| Function | Linux (`traceroute`) | Windows CMD (`tracert`) | Cisco IOS |
|---|---|---|---|
| **Disable reverse DNS lookup** | `-n` | `-d` | `traceroute` options: `numeric` |
| **Maximum hop count** | `-m <hops>` | `-h <hops>` | `traceroute` options: `Numeric display` / `Maximum TTL` |
| **Probe count per hop** | `-q <count>` | No direct equivalent | `Probe count` (where supported) |
| **Use IPv4** | `-4` | `-4` | Depends on IOS command and platform |
| **Use IPv6** | `-6` | `-6` | `traceroute ipv6` (where supported) |
