## Objective:
The objective of this lab is to understand the basics of **log analysis** and demonstrate how logs from different systems can be collected, analyzed, and used for security monitoring. I will learn how to generate simple logs on both Windows and Linux systems and how SOC Analysts use logs to detect security incidents.

## What is a Log:
  A log is a record of events in a system that captures important actions like errors, warnings, or user activities. These logs contain key information such as:
    - Timestamp
    - Event Description    
    - Severity (Critical, Error, Warning, Information)
    - Source (User, Process, Service)
  
Logs are essential for understanding system behavior, detecting security incidents, and conducting forensic investigations.

## How Does a SOC Analyst Use Log Analysis?
  - Incident Detection: SOC Analysts review logs to detect unusual or unauthorized activities, such as failed login attempts or suspicious processes.
  - Forensics: Logs are used to trace back the actions taken by an attacker during or after an incident.
  - Security Monitoring: Continuous log analysis helps detect potential security threats in real-time.
  - Compliance: Logs assist in maintaining compliance with regulatory standards (e.g., GDPR, HIPAA).

## Popular Tools for Log Analysis:
  - ELK Stack (Elasticsearch, Logstash, Kibana): A powerful suite for log collection, storage, and visualization.
  - Splunk: A leading tool for searching, analyzing, and visualizing machine-generated data.
  - Graylog: An open-source log management solution.
  - Wazuh: An open-source security monitoring platform that integrates well with ELK for log analysis and threat detection.

## Lab Task: Simulating and Detecting Windows Powershell events
**Lab Requirements:**
  Systems: Windows 10/11 or Windows Server 2019/2022, Linux (Ubuntu or CentOS)

Tools:
  - Windows Event Viewer
  - PowerShell (Pre-installed on Windows)

For this lab, you will need to set up log collection on both Windows and Linux systems. Follow these steps to ensure everything is ready:
On Windows:
Open #Group Policy Editor (gpedit.msc):
  - Navigate to `Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell`.
  - Ensure that Module Logging, Script Block Logging, and Script Execution are enabled.
  - Open Event Viewer:
    - Go to `Applications` and `Services Logs → Microsoft → Windows → PowerShell → Operational`.

**Step 1: Simulate a Suspicious PowerShell Command**
  To simulate a suspicious activity, open an elevated PowerShell session and run the following command:
    ```powershell
    Get-LocalUser | Select-Object Name, Enabled
    ```
  This command lists all local user accounts on the system, which could be used by attackers to enumerate users post-exploitation.

**Step 2: Detect the Log in Windows Event Viewer**
  - Press `Win + R`, type eventvwr.msc, and press Enter.
  - Navigate to: `Applications and Services Logs → Microsoft → Windows → PowerShell → Operational`.
  - Click Filter Current Log, and filter for Event ID 4104 (which logs PowerShell script execution).
  - Look for an entry that shows the execution of the Get-LocalUser command.
  - Take a screenshot of the event details.

## Conclusion:
  Understanding Log Analysis: Logs are crucial for detecting, investigating, and responding to security incidents. Through the use of Windows Event Viewer and Linux log files, you can monitor system activity and identify potential security issues.
