
# Show routing based on DNS name
```
ip route get $(dig +short a google.com|tail -n1)
```

ip tcp_metrics

# If you need `json` output

```bash
ip --json --brief address show lo
```
```
[{"ifname": "lo", "operstate": "UNKNOWN", "addr_info": [{"local": "127.0.0.1", "prefixlen": 8},{"local": "::1", "prefixlen": 128}]}, {}, {}]
```

# Show only static or dynamic IPv6 addresses
Show only statically configured addresses:
```bash
ip address show [dev ${interface}] permanent
```
Show only addresses learnt via autoconfiguration:
```bash
ip address show [dev ${interface}] dynamic
```

# `iproute2` replace old net-tools

| old command      | iproute2 replacement |
| --------------- |:-------------:| -----------:|
| `ifconfig` (interface list) | `ip link` |
| `ifconfig` (ip configuration) | `ip addr` |
| `ifconfig` (interface stats) | `ip -s link` |
| `route` | `ip route` |
| `arp` | `ip neigh` |
| `netstat` | `ss` |
| `netstat -g` | `ip maddr` |
| `netstat -i` | `ip -s link` |
| `netstat -r` | `ip route` |
