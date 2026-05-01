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

## Infrastructure Configuration

Additional configurations have been completed to support a functional and realistic SOC environment:

- Configured Active Directory with domain users and security groups
- Implemented group-based access control for simulation
- Enabled DNS reverse lookup zone for internal host resolution
- Joined Windows 11 endpoint to Active Directory domain (test.local)
- Installed Splunk SIEM on Ubuntu Server
- Assigned static IP to Splunk server for consistent communication
- Introduced intentional Active Directory misconfigurations for security testing
- Configured Splunk to ingest logs from Windows Server (Domain Controller)
- Enabled centralized collection of Windows Event Logs

These configurations enable realistic enterprise scenarios involving authentication, logging, and attack simulation.

## Attack Simulation & Detection

Initial attack simulations have been performed to validate monitoring and detection capabilities:

- Conducted network scanning using Kali Linux against Metasploitable
- Generated ICMP traffic to simulate basic communication
- Monitored and analyzed activity using Security Onion
- Verified detection of scanning behavior and network traffic visibility
- Performed Kerberos-based brute force attack against AD user `hr1`
- Observed multiple pre-authentication failures (Event ID 4771) followed by a successful TGT request (Event ID 4768)
- Investigated authentication patterns in Splunk SIEM
- Identified behavior consistent with credential brute force attack

This marks the transition from lab setup to active SOC monitoring and detection.
