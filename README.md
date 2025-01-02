Live SOC & Honeynet in Azure
![image](https://github.com/user-attachments/assets/52baec98-74e0-46ec-aa60-713625423c1d)


As part of this project, I built a small honeynet in Azure and feed logs from many sources into a Log Analytics Workspace. Microsoft Sentinel used this data to generate attack maps, send out alarms, and create incidents. After a day of measuring security metrics in the unprotected environment, I implemented security measures to make the environment more resilient, measured metrics for an additional day, and then presented the findings below. I gathered the following:

SecurityEvent (Windows Event Logs)

Syslog (Linux Event Logs)

SecurityAlert (Log Analytics Alerts Triggered)

SecurityIncident (Incidents created by Sentinel)

AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

# Architecture Before Hardening / Security Controls
![image](https://github.com/user-attachments/assets/430246dc-734a-4d38-8c36-5fff8dcdc443)

Architecture After Hardening / Security Controls
![image](https://github.com/user-attachments/assets/b16c471b-cfd2-45d5-80c1-9e1776ac724d)

