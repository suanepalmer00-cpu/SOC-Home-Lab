# SOC Home Lab

A hands-on Security Operations Center (SOC) home lab focused on security monitoring, log analysis, threat detection, investigation, and incident response.

This project demonstrates practical experience using Splunk, Windows Event Logs, Sysmon, MITRE ATT&CK, Kali Linux, and controlled security events to simulate SOC analyst workflows.

---

## Objectives

- Build and configure a virtualized SOC environment
- Collect and analyze Windows security logs
- Configure and use Splunk as a SIEM
- Configure Sysmon for endpoint monitoring
- Investigate suspicious activity
- Create security detections using Splunk
- Identify Indicators of Compromise (IOCs)
- Map security activity to MITRE ATT&CK
- Document security investigations
- Practice incident response procedures

---

# 1. Lab Environment

## Virtual Machines

| System | Operating System | Role |
|---|---|---|
| Kali Linux | Kali Linux | Security Testing / Attack Simulation |
| Windows 11 | Windows 11 | Monitored Endpoint |
| Metasploitable2 | Linux | Vulnerable Test System |

## Security Tools

| Tool | Purpose |
|---|---|
| Splunk Enterprise | SIEM, log collection, searching, and detection |
| Sysmon | Windows endpoint monitoring and process logging |
| Wireshark | Network traffic analysis |
| Nmap | Network discovery and security scanning |
| MITRE ATT&CK | Adversary behavior and technique mapping |

---

# 2. Network Architecture

The lab uses an isolated VirtualBox Host-Only network to allow communication between the virtual machines while keeping the testing environment separated from the normal network.

```text
                    SOC HOME LAB

                       Splunk
                          |
                          |
                    Security Logs
                          |
                +---------+---------+
                |                   |
                ▼                   ▼
          Windows 11           Network Data
          Monitored             Analysis
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
Lab Setup
    ↓
Log Collection
    ↓
SIEM Monitoring
    ↓
Security Event Generation
    ↓
Detection
    ↓
Investigation
    ↓
MITRE ATT&CK Mapping
    ↓
Incident Response

The project is continuously being expanded with additional SOC investigations and detection scenarios.

