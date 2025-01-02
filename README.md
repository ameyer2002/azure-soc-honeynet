# Live SOC & Honeynet in Azure
![image](https://github.com/user-attachments/assets/52baec98-74e0-46ec-aa60-713625423c1d)


As part of this project, I built a small honeynet in Azure and feed logs from many sources into a Log Analytics Workspace. Microsoft Sentinel used this data to generate attack maps, send out alarms, and create incidents. After a day of measuring security metrics in the unprotected environment, I implemented security measures to make the environment more resilient, measured metrics for an additional day, and then presented the findings below. I gathered the following:

SecurityEvent (Windows Event Logs)

Syslog (Linux Event Logs)

SecurityAlert (Log Analytics Alerts Triggered)

SecurityIncident (Incidents created by Sentinel)

AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

# Architecture Before Hardening / Security Controls
![image](https://github.com/user-attachments/assets/430246dc-734a-4d38-8c36-5fff8dcdc443)

# Architecture After Hardening / Security Controls
![image](https://github.com/user-attachments/assets/b16c471b-cfd2-45d5-80c1-9e1776ac724d)

The architecture of the mini honeynet in Azure consists of the following:

Virtual Network (VNet)

Network Security Group (NSG)

Virtual Machines (2 windows, 1 linux)

Log Analytics Workspace

Azure Key Vault

Azure Storage Account

Microsoft Sentinel

# Attack Maps Before Hardening / Security Controls
![image](https://github.com/user-attachments/assets/c504e1d8-b0b5-4801-8ac3-2e14cfe4ca31)
![image](https://github.com/user-attachments/assets/fec3ee3a-f0c1-4b06-9787-a2e6ce2e24a3)
![image](https://github.com/user-attachments/assets/5a36016f-eded-4dae-9d8d-cb3ce77ec676)

# Metrics Before Hardening / Security Controls
The following table shows the metrics we measured in our insecure environment for 24 hours:

Start Time 2024-12-29 05:05:48

Stop Time 2024-12-30 05:05:48

| Metric | Count |
| ---- | ---- |
| SecurityEvent | 8230 |
| Syslog | 743 |
| SecurityAlert | 8 |
| SecurityIncident | 55 |
| AzureNetworkAnalytics_CL | 600 |



