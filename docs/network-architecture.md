## Enterprise SOC Network Design

The network is segmented into separate zones to simulate a real enterprise environment:

- Internal LAN (192.168.1.0/24)
- Attacker Network (192.168.3.0/24)
- SIEM Network (192.168.5.0/24)
- Management Network (192.168.114.0/24)

Traffic from the internal LAN is mirrored via SPAN to a Security Onion sensor, enabling passive network intrusion detection without impacting live traffic.
