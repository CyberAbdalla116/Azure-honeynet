# Azure-honeynet

### Introduction

In this project, I built a mini honeynet in Azure and ingested logs from various resources into a Log Analytics Workspace. I then used Microsoft Sentinel to create attack maps, trigger alerts, and generate incidents. To assess security effectiveness, I measured key security metrics in the insecure environment over 24 hours, implemented security controls to harden the system, and then re-evaluated the metrics over another 24-hour period. The collected metrics include:

SecurityEvent – Windows Event Logs
Syslog – Linux Event Logs
SecurityAlert – Alerts triggered in Log Analytics
SecurityIncident – Incidents created by Sentinel
AzureNetworkAnalytics_CL – Malicious network flows detected in the honeynet

### Architecture Before Hardening / Security Controls

![image](https://github.com/user-attachments/assets/2efbfcbf-0ee1-4ecf-abdf-e2cc1a8169bb)

### Architecture After Hardening / Security Controls

![image](https://github.com/user-attachments/assets/413d1173-9f42-43f7-823f-ba754ac0c4e0)

The architecture of the mini honeynet in Azure consisted of the following components:

Virtual Network (VNet)
Network Security Group (NSG)
Virtual Machines (2 windows, 1 linux)
Log Analytics Workspace
Microsoft Sentinel

### Attack Maps Before Hardening / Security Controls

![image](https://github.com/user-attachments/assets/32257ddd-50d8-41ee-9efe-b19c2563998a)

![image](https://github.com/user-attachments/assets/af3a1038-67dd-449f-a870-b291bedc0389)

![image](https://github.com/user-attachments/assets/567ea29e-b2cd-454b-b364-b6ba88daca89)


### Metrics Before Hardening / Security Controls

The following table shows the metrics we measured in our insecure environment for 24 hours: 

| Start Time 2025-03-06 13:53:48 
| Stop Time 2025-03-07 14:07:13

Metric	Count
SecurityEvent	12,332
Syslog	10,783
SecurityAlert	50
SecurityIncident	51
AzureNetworkAnalytics_CL	18,819

### Attack Maps After Hardening / Security Controls

![image](https://github.com/user-attachments/assets/3fb6446e-8571-42eb-9a9f-1e74ee64657f)

After hardening the environment, map queries returned no results, indicating that the applied security controls successfully mitigated malicious activity over the 24-hour period.

### Metrics After Hardening / Security Controls

The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls: 

| Start Time 2025-03-07 18:50:28 
| Stop Time 2025-03-08 19:12:32

Metric	Count
SecurityEvent	1093
Syslog	6
SecurityAlert	0
SecurityIncident	0
AzureNetworkAnalytics_CL	0

![image](https://github.com/user-attachments/assets/5bc23560-f33f-4a3c-96cc-b8a643c17eaf)

### Summary

In this project, a mini honeynet was set up in Microsoft Azure, with logs sent to a Log Analytics Workspace for analysis. Microsoft Sentinel was utilised to trigger alerts and generate incidents based on the ingested logs. Metrics were recorded in the unsecured environment before security controls were applied and then again after their implementation. The results showed a significant reduction in both security events and incidents, highlighting the effectiveness of the applied security measures.
