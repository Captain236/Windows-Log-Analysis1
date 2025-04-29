# Windows-Log-Analysis1
# What is Log?
- Log is a record of events that captures the important informations like errors , activity performed by usres , warninings . These logs contains the informations like
- **Timestamp**
- **Event Description**
- **Severity(critical,warning,error,information)**
- **source**
- Logs are essential for understanding system behaviour , detecting security incident , condtucting forensic investigation

## Log Sources on Windows
- **Event Viewer**: Provides access to logs such as:
- **System Logs**: Logs related to operating system events.
- **Security Logs**: Logs related to login attempts, permission changes, etc.
- **Application Logs**: Logs for system applications.
- **PowerShell Logs**: Logs for PowerShell commands, including suspicious execution.
## How Does a SOC Analyst Use Log Analysis?
- **Incident Detection**: SOC Analysts review logs to detect unusual or unauthorized activities, such as failed login attempts or suspicious processes.
- **Forensics**: Logs are used to trace back the actions taken by an attacker during or after an incident.
- **Security Monitoring**: Continuous log analysis helps detect potential security threats in real-time.
- **Compliance**: Logs assist in maintaining compliance with regulatory standards (e.g., GDPR, HIPAA).

## Popular Tools for Log Analysis:
- **ELK Stack (Elasticsearch, Logstash, Kibana)**: A powerful suite for log collection, storage, and visualization.
- **Splunk**: A leading tool for searching, analyzing, and visualizing machine-generated data.
- **Graylog**: An open-source log management solution.
- **Wazuh**: An open-source security monitoring platform that integrates well with ELK for log analysis and threat detection
  ## Objective:-
 - The objective of this task is to understand the windows security logs and understand how to analyze security logs for security related events. Goal is to learn how to analyze security ebvents like logging attempts , user account changes and other critical security events.
## Requirements:-
- **VMware or virtual box**
- **windows server installed in vmware or windows 10 etc**
- **Tools**
     - **Event viewer**
     - **NotePad**(to create custom events if needed)

     - **Administrative privilleges**(to access certain security logs)
## What are Windows Security Logs?
- Windows Security Logs contain records of security-related events on the system, such as:
- **Successful and Failed Login Attempts**: Track users who log in or fail to log in.
- **Account Lockouts**: Occurs when a user exceeds the maximum allowed number of incorrect login attempts.
- **Audit Policies**: Logs related to changes in system audit settings and configurations.
- **Group Membership Changes**: Tracks changes in group memberships and user privileges.
- **Privilege Escalation**: Logs events when a user gains elevated privileges.
## Understanding Event IDs in Security Logs:
- **Event ID 4624**: Successful Logon.
- **Event ID 4625**: Failed Logon.
 **Event ID 4740**: Account Lockout.
- **Event ID 4732**: A user was added to a security-enabled local group.
- **Event ID 4672**: Special privileges assigned to a new logon (Privilege escalation).
# Let's Begin....
# Task :-Simulating and Detecting Windows Powershell events
## Step1:- 
- On **Windows server** open **Group policy editor**(gpedit.msc)
![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_24_18](https://github.com/user-attachments/assets/598b09af-31c5-46d1-b63d-403f6f899b88)
## step2:-
- Navigate to Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell
![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_26_16](https://github.com/user-attachments/assets/681076f9-0f35-4abb-98a6-f5ad3eca57b8)


  

  
