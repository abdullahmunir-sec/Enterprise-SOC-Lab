# pfSense Firewall Deployment

A pfSense firewall was deployed to control routing between segmented networks and simulate an enterprise perimeter firewall.

## Network Interfaces

- WAN – Connected to external / simulated internet network
- LAN – Internal network (192.168.1.0/24)
- OPT1 – Attacker network (192.168.3.0/24)
- OPT2 – SIEM network (192.168.5.0/24)
- OPT3 – Management network (192.168.114.0/24)

## Role in the SOC Architecture

The firewall is responsible for:
- Routing traffic between network segments
- Enforcing network isolation
- Providing a point for traffic mirroring toward Security Onion
