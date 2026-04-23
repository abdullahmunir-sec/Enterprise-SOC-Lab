# Windows Log Forwarding to Splunk

## Overview

This document outlines the configuration of log forwarding from the Windows Server (Domain Controller) to the Splunk SIEM using the Splunk Universal Forwarder.

A custom input configuration was created to collect and forward Windows Event Logs for centralized monitoring and analysis.

---

## Splunk Add-on Installation

The Splunk Add-on for Windows was installed on the forwarder to enable proper parsing and ingestion of Windows Event Logs.

### Steps Performed

* Downloaded Splunk Add-on for Windows
* Extracted contents to:

  * `$SPLUNK_HOME/etc/apps/Splunk_TA_windows`

---

## Input Configuration

A custom configuration file was created to define which logs should be collected and forwarded.

### File Location

```
$SPLUNK_HOME/etc/apps/Splunk_TA_windows/local/inputs.conf
```

### Configuration

```
[WinEventLog://Security]
disabled = 0
index = winsrvlogs
sourcetype = WinEventLog:Security
renderXml = false

[WinEventLog://System]
disabled = 0
index = winsrvlogs
sourcetype = WinEventLog:System
renderXml = false

[WinEventLog://Application]
disabled = 0
index = winsrvlogs
sourcetype = WinEventLog:Application
renderXml = false

[WinEventLog://ForwardedEvents]
disabled = 0
index = winsrvlogs
sourcetype = WinEventLog:ForwardedEvents
renderXml = false

[WinEventLog://Setup]
disabled = 0
index = winsrvlogs
sourcetype = WinEventLog:Setup
renderXml = false
```

---

## Configuration Details

* **Index:** `winsrvlogs`

  * Dedicated index for Windows Server logs

* **Sourcetypes:**

  * `WinEventLog:Security`
  * `WinEventLog:System`
  * `WinEventLog:Application`
  * `WinEventLog:ForwardedEvents`
  * `WinEventLog:Setup`

* **renderXml = false**

  * Improves readability and simplifies analysis in Splunk

---

## Validation

* Restarted Splunk Universal Forwarder service
* Verified connection to Splunk indexer
* Confirmed logs are visible in Splunk Web

### Test Queries

```
index=winsrvlogs
```

```
index=winsrvlogs sourcetype=WinEventLog:Security
```

---

## Purpose

This configuration enables:

* Centralized collection of Windows Event Logs
* Visibility into authentication and system activity
* Detection of suspicious behavior (e.g., failed logins, privilege escalation)

This is a critical component of the SOC lab, enabling realistic monitoring and detection workflows.
