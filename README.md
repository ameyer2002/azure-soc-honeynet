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

Start Time 2024-12-29 09:05:48

Stop Time 2024-12-30 09:05:48

| Metric | Count |
| ---- | ---- |
| SecurityEvent | 8230 |
| Syslog | 743 |
| SecurityAlert | 8 |
| SecurityIncident | 55 |
| AzureNetworkAnalytics_CL | 600 |

# Attack Maps After Hardening / Security Control
![image](https://github.com/user-attachments/assets/752436f0-b403-467e-8c0a-52ffd433bcb5)

No map queries were returned 24 hours after hardening.

# Metrics After Hardening / Security Controls
The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:

Start Time 2025-01-01 12:34:01

Stop Time 2025-01-02 12:34:01

| Metric | Count |
| ---- | ---- |
| SecurityEvent | 4109 |
| Syslog | 4 |
| SecurityAlert | 0 |
| SecurityIncident | 0 |
| AzureNetworkAnalytics_CL | 0 |

| Metric | Change after hardening security environment |
| ---- | ---- |
| SecurityEvent | 50.07% |
| Syslog | 99.46% |
| SecurityAlert | 100.00% |
| SecurityIncident | 100.00% |
| AzureNetworkAnalytics_CL | 100.00% |

# Summary
This project involved building a small honeynet in Microsoft Azure and pushing the logs into a Log Analytics Workspace for analysis. On the basis of the ingested data, Microsoft Sentinel was also used to generate incidents and set off alerts. Metrics were also taken in the unprotected setting prior to the application of security controls and again with security measures in place. After the security controls were implemented, the quantity of security events and incidents significantly decreased.






