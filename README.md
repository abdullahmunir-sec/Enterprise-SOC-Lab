# Enterprise SOC Lab – Security Monitoring & Network Detection

This project documents the design and deployment of a virtualized enterprise-style Security Operations Center (SOC) lab.

The lab simulates a segmented corporate network and demonstrates how security teams monitor, detect, and investigate threats using host-based and network-based telemetry.

## Objectives

- Design a segmented network architecture
- Deploy Security Onion for network intrusion detection
- Mirror traffic using SPAN for passive monitoring
- Correlate logs across multiple sources for threat analysis

## Network Architecture

The lab environment consists of multiple isolated networks:

- **Internal LAN** hosting domain controller and user workstation
- **Attacker network** used to simulate malicious activity
- **SIEM network** hosting Splunk for centralized logging
- **Management network** used to administer security tools
- **Security Onion sensor** monitoring mirrored traffic

![Enterprise SOC Architecture](architecture/enterprise-soc-network-v1.png)

## Deployment Progress

The following infrastructure components have been deployed:

- Multi-interface pfSense firewall enforcing network segmentation
- Windows 11 enterprise endpoint
- Kali Linux attacker workstation
- Metasploitable 2 vulnerable server
- Ubuntu Server prepared for Splunk SIEM deployment
- Windows Server 2022 Domain Controller with Active Directory (test.local)

## Monitoring Platform

Security Onion has been deployed to provide network intrusion detection and security event monitoring across the lab environment. The platform collects mirrored traffic and generates alerts based on detected threats and anomalies.
