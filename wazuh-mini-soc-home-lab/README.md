# Wazuh Mini-SOC Home Lab

## Project Overview

This project documents a hands-on cybersecurity home lab designed to practice security monitoring, endpoint visibility, File Integrity Monitoring (FIM), security alert investigation, and antivirus detection.

The lab uses Wazuh for security monitoring and includes a Windows endpoint and a virtualized server environment.

## Project Objectives

* Practice deploying and accessing a Wazuh security monitoring environment.
* Monitor a Windows endpoint.
* Investigate security alerts and file-related events.
* Practice File Integrity Monitoring.
* Explore VirusTotal threat intelligence integration.
* Investigate an active-response workflow.
* Validate antivirus detection using the EICAR test file.
* Document lab activities and findings.

## Lab Environment

* SIEM: Wazuh
* Virtualization platform: Proxmox VE
* Server operating system: Ubuntu Server
* Endpoint operating system: Windows
* Remote connectivity: Tailscale
* Command-line tool: PowerShell
* Antivirus: Microsoft Defender

## Project Evidence

### 1. Wazuh Dashboard

![Wazuh Dashboard](screenshots/01-wazuh-dashboard.png)

This screenshot documents the Wazuh dashboard and the monitoring environment.

### 2. File Integrity Monitoring

![File Integrity Monitoring](screenshots/02-fim-file-monitoring.png)

This screenshot documents the file monitoring activity observed during the lab.

### 3. Active Response

![Active Response](screenshots/03-active-response.png)

This screenshot documents the active-response workflow or execution evidence shown in the lab.

### 4. Malware File Detection

![Malware File Detection](screenshots/04-malware-file-detection.png)

This screenshot documents the file detection evidence shown in the lab. The specific detection source and outcome should be described according to the evidence.

### 5. EICAR Antivirus Detection

![EICAR Defender Detection](screenshots/05-eicar-defender-detection.png)

The EICAR test file was verified using PowerShell. Microsoft Defender subsequently detected or quarantined the test file.

This confirms the antivirus response observed in Windows Security. It does not, by itself, establish that Wazuh detected the file.

### 6. Wazuh Security Alert

![Wazuh Security Alert](screenshots/06-wazuh-security-alert.png)

This screenshot documents the Wazuh security alert reviewed during the project.

## Skills Practiced

* SIEM fundamentals
* Endpoint monitoring
* Security alert investigation
* File Integrity Monitoring
* Threat intelligence integration
* Active-response investigation
* Windows security
* PowerShell
* Linux server administration
* Virtualization
* Technical documentation

## Lessons Learned

This project provided practical experience with security monitoring concepts and reinforced the importance of validating alerts, reviewing response evidence, and distinguishing between antivirus detections and events confirmed in a SIEM.

## Future Improvements

* Investigate additional endpoint security events.
* Document Wazuh rule IDs and severity levels.
* Validate active-response outcomes.
* Add sanitized configuration examples.
* Document reproducible steps for rebuilding the lab.

## Disclaimer

This project was created for educational purposes in a controlled home lab. The EICAR test file is a standardized antivirus test pattern, not live malware.
