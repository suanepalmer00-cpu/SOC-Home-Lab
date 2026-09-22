# SOC Home Lab

## Overview

This project documents the development of a Security Operations Center (SOC) home lab designed to practice security monitoring, log analysis, threat detection, and incident response.

## Objectives

- Build a virtualized security lab
- Collect and analyze security logs
- Practice Security Information and Event Management (SIEM)
- Investigate suspicious activity
- Identify Indicators of Compromise (IOCs)
- Map activity to MITRE ATT&CK
- Create security detections and alerts
- Document incident investigations

## Lab Environment

### Virtual Machines

| System | Operating System | Role |
|---|---|---|
| Kali Linux | Kali Linux | Security Testing / Attack Simulation |
| Windows 11 | Windows 11 | Monitored Endpoint |
| Metasploitable2 | Linux | Vulnerable Test System |

### Security Tools

| Tool | Purpose |
|---|---|
| Splunk | Security Information and Event Management (SIEM) |
| Sysmon | System Monitoring and Windows Event Logging |
| Wireshark | Network Traffic Analysis |
| Nmap | Network Discovery and Security Scanning |
| MITRE ATT&CK | Adversary Tactics, Techniques, and Common Knowledge |

### Network Architecture

The lab uses an isolated VirtualBox Host-Only network to allow the virtual machines to communicate within the lab environment.

```text
                    SOC HOME LAB

                       Splunk
                         |
                         | Security Logs
                         |
                  +------+------+
                  |             |
                  ▼             ▼
            Windows 11      Network Data
            Endpoint
                  ▲
                  |
          Controlled Activity
                  |
                  ▼
             Kali Linux
        Security Testing

                  |
                  ▼
           Metasploitable2
          Vulnerable System

## Phase 1: Network Configuration

### VirtualBox Network

The virtual machines were configured on an isolated VirtualBox Host-Only network.

### Connectivity Testing

Connectivity between Kali Linux and Windows 11 was verified using ICMP (Internet Control Message Protocol) ping testing.

Command:

```bash
ping -c 4 [Windows VM IP]
```
## Result

The connectivity test was successful.

- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%

Successful communication was established between the Kali Linux testing system and the Windows 11 monitored endpoint.


## Phase 2: Windows Log Collection

### Splunk Enterprise

Splunk Enterprise was configured to collect Windows Event Logs from the Windows 11 monitored endpoint.

### Event Logs

The following Windows Event Log channels were configured:

- Application
- System
- Security

### Log Collection Verification

Windows Security events were successfully indexed in Splunk Enterprise.

Search used:

```spl
index=main sourcetype="WinEventLog:Security"

### Sysmon Log Collection

Sysmon was installed on the Windows 11 victim machine and configured to generate detailed Windows process and system activity logs.

The Sysmon Operational event channel was configured in Splunk Enterprise:

- Microsoft-Windows-Sysmon/Operational

### Sysmon Log Collection Verification

Sysmon events were successfully indexed and searchable in Splunk Enterprise.

Search used:

```spl
index=default sourcetype="WinEventLog:Microsoft-Windows-Sysmon/Operational"



## Upcoming Phases


- Generate controlled security events
- Investigate suspicious activity
- Create Splunk detections
- Map activity to MITRE ATT&CK
- Complete Incident Response (IR) investigations

