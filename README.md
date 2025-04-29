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
![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_24_18](https://github.com/user-attachments/assets/598b09af-31c5-46d1-b63d-403f6f899b88)-
- **Navigate to Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell**
![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_26_16](https://github.com/user-attachments/assets/681076f9-0f35-4abb-98a6-f5ad3eca57b8)
-  **Enable Module Logging, Script Block Logging, and Script Execution**.
-  [windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_29_00](https://github.com/user-attachments/assets/bd7ca623-8a35-4901-adc6-681506e3adec)
- **Open the event Viewer**
- ![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_31_34](https://github.com/user-attachments/assets/cb7560ea-e2dc-4c98-bb05-c8701ac9965a)
## Step2:-
- **Now simulate the suspecious powershell command
- **open the powershell and execute the following commnad..
-  ( **Get-LocalUser | Select-Object Name, Enabled**)
-  **This command lists all local user accounts on the system, which could be used by attackers to enumerate users post-exploitation.**
- ![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_36_29](https://github.com/user-attachments/assets/9cda2918-368a-465f-8751-3854674c06e9)
## Step3:- Detect the Log in Windows Event Viewer
- **Open the Event Viewer ( windows+R and type eventvwr.msc)** and press enter.
- **Navigate to: Applications and Services Logs → Microsoft → Windows → PowerShell → Operational.**
- ![windows server - VMware Workstation 16 Player (Non-commercial use only) 18-04-2025 10_34_40](https://github.com/user-attachments/assets/3c764466-a3f4-40fb-a72f-83a7993fa011)
- **Click Filter Current Log, and filter for Event ID 4104 (which logs PowerShell script execution).**
- ![(1) Give me 30 Days and I promise - you won't be the same person again! _ Security Challenge - YouTube - Google Chrome 18-04-2025 10_49_22](https://github.com/user-attachments/assets/504b9e88-5cf4-4921-8a4d-afdc51b6fa39)
- **we can see an entry that shows the execution of the Get-LocalUser command**

# Conclusion:-
- **Understanding Log Analysis: Logs are crucial for detecting, investigating, and responding to security incidents. Through the use of Windows Event Viewer and Linux log files, you can monitor system activity and identify potential security issues.
SOC Analyst Role: SOC Analysts use log analysis to detect threats, investigate incidents, and ensure system compliance.**








  

  
