# Active Directory Setup – Windows Server 2022

## Overview

This document outlines the deployment and configuration of Active Directory Domain Services (AD DS) in the Enterprise SOC Lab using Windows Server 2022.

The goal is to simulate a real-world enterprise environment where centralized identity management and authentication are enforced.

---

## Environment Details

* Server OS: Windows Server 2022 Evaluation
* Role Installed: Active Directory Domain Services (AD DS)
* Domain Name: test.local
* Server Role: Domain Controller (DC)

---

## Installation Steps

### 1. Install AD DS Role

* Open **Server Manager**
* Navigate to **Add Roles and Features**
* Select:

  * Active Directory Domain Services
* Complete installation and restart if required

---

### 2. Promote Server to Domain Controller

* Click **Promote this server to a domain controller**

* Select:

  * Add a new forest

* Root domain name:

  * `test.local`

* Set:

  * Directory Services Restore Mode (DSRM) password

* Complete configuration and allow automatic reboot

---

### 3. Post-Installation Configuration

* Verified domain controller functionality
* Checked DNS configuration
* Confirmed domain availability:

  * `test.local`

---

## Validation

* Logged into domain as Administrator
* Opened:

  * Active Directory Users and Computers (ADUC)
* Verified domain structure is accessible

---

## Security Relevance

Active Directory is a primary target in enterprise environments. This setup enables simulation of:

* Credential-based attacks (e.g., brute force, Kerberos abuse)
* Lateral movement
* Privilege escalation
* Account enumeration
