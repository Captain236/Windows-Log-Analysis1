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
