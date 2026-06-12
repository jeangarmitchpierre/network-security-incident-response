# Network Security and Incident Response Playbook

This repository serves as an operational playbook for handling mid-sized corporate network anomalies, vulnerability mitigation, and standard incident response workflows.

## Network Environment Base
* Core Protocols: IPv4 routing secured via OSPF authentication areas.
* Environment: Hybrid corporate infrastructure utilizing virtualized Hyper-V environments for internal staging servers.
* Monitoring: Packet inspection and traffic baseline analysis using Wireshark to isolate network anomalies.

## Incident Response Lifecycle

### 1. Detection and Identification
* Trigger: Unusual inbound traffic spikes detected on internal subnets.
* Analysis: Utilizing Wireshark to filter for malicious network scans or protocol floods. 
* Action: Validate if traffic stems from misconfigured internal assets or unauthorized external routing attempts.

### 2. Containment Strategy
* Short-Term: Isolate affected network segments or Hyper-V virtual switches immediately to halt lateral movement without taking down core operations.
* Long-Term: Update access control lists (ACLs) and restrict routing neighbors to verified devices.

### 3. Remediation and Hardening
* Deploy vulnerability assessment scripts to locate unpatched endpoints.
* Re-verify OSPF security keys across all active network nodes.
* Clear and restore systems from verified local offline backups if corruption is discovered.

## Security Operations Matrix

| Incident ID | Threat Category | Containment Action | Validation Tool | Status |
| :--- | :--- | :--- | :--- | :--- |
| INC-01 | Unauthorized Port Scan | Block source IP via Firewall | Wireshark Logs | Resolved |
| INC-02 | OSPF Routing Anomaly | Reset MD5 Neighbor Auth | Router Console | Resolved |
| INC-03 | Localized Malware Trace | Isolate Staging Hyper-V VM | System Logs | Active |
