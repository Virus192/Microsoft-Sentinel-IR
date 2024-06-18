# Microsoft-Sentinel-IR
Incident Detection and Response to HoneyPot Detection using NIST 800 SP-53 SC-7 (Boundary Protection) Compliance, This project focused on implementing incident detection and response strategies using a Honeypot to lure potential attackers. Compliance with NIST 800-53 SC-7 standards ensured robust boundary protection to safeguard organizational assets and data. 

# Orchestrating  a SOC + Honeynet in Azure with a live Attack Traffic Mapping
![Cloud Honeynet / SOC](https://imgur.com/CPWlFrz.jpg)

## Introduction

This project centers on the establishment of a state-of-the-art Security Operations Center (SOC) tailored to meet the demands of modern cloud security integration. 

- 👉 Within this project, I orchestrated the development of a comprehensive SOC LAB, leveraging Microsoft Sentinel as the cornerstone of our Security Information and Event Management (SIEM) solution. 

- 👉 Utilizing Log Analytics workspaces, I aggregate and analyze logs sourced from a diverse array of platforms including Windows VMs, Linux VMs, Azure Blob Storage, entreID, Activity logs, and MS SQL Database. Employing KQL for log querying.

- 👉 My focus was centered on meticulous data collection, correlation, and in-depth analysis to bolster threat detection capabilities in the cloud. 

- 👉 An integral aspect of this initiative involves the visualization of event locations on a global scale, providing actionable insights through geographical mapping. 

- ⭕ And lastly, This project underscores the critical importance of SOC in the cloud era, where proactive monitoring and swift response are paramount for safeguarding digital assets against ever-evolving cyber threats.

## The metrics we will show are:

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

## Architecture Before Hardening / Security Controls
![Architecture Diagram](https://imgur.com/OvrBFLs.jpg)

## Architecture After Hardening / Security Controls
![Architecture Diagram](https://imgur.com/48jqTjV.jpg)

The architecture of the mini honeynet in Azure consists of the following components:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic with the exception of my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint

## Attack Maps Before Hardening / Security Controls
![Windows RDP/SMB Auth Failures](https://imgur.com/tNjMcHi.png)<br>

## Microsoft Sentinel Workspace After Hardening Security Controls
![Windows RDP/SMB Auth Failures](https://imgur.com/K8JE1dc.png)<br>

## Expertise
- 🔰 Through the strategic deployment of a honeypot in the cloud, I successfully attracted and recorded a substantial influx of brute force attempts. Leveraging Sentinel's powerful geolocation mapping features, I was able to pinpoint adversary locations using three meticulously crafted workbook queries: Nsg-malicious-allowed-in, linux-ssh-auth-fail, and Windows-rdp-auth-fail.

- 🔰 I then developed 14 comprehensive analytic rules using Kusto Query Language (KQL). These rules were designed to trigger alerts on various suspicious activities, providing early warnings and facilitating prompt response to potential threats. Furthermore, I established detailed incident response playbooks tailored to address the specific incidents observed, including brute force attempts and malware detections. These playbooks ensured that our response was swift, coordinated, and effective.

- 🔰 Following the detection and response phase, I focused on fortifying the security posture thereby Implementing the NIST 800-53 SC-7 (Boundary Protection) standard, Then tightened the security of the resources and virtual machines. This included revising firewall rules and enhancing access controls to prevent unauthorized access and mitigate potential threats.

- 🔰 To validate the efficacy of the security measures, I monitored the environment for an additional 24 hours. During this period, and observed a complete absence of incidents, confirming a 100% compliance rate and demonstrating the robustness of the implemented security controls.

## 🔵 Key Skills

- **✔Threat Detection and Analysis:** Proficient in using SIEM tools, such as Azure Sentinel, for monitoring and analyzing security events to identify potential threats.

- **✔Incident Response:** Experienced in developing and executing incident response playbooks to effectively manage and mitigate security incidents.

- **✔Security Operations:** Skilled in the day-to-day operations of a SOC, including log analysis, intrusion detection, and vulnerability management.

- **✔Network Security:** Knowledgeable in configuring and managing firewall rules, intrusion prevention systems, and other network security controls.

- **✔Cloud Security:** Familiar with securing cloud environments, particularly Azure, and implementing security measures in line with industry standards such as NIST 800-53.

## Conclusion

⭕ In conclusion, the successful execution of this project underscores the critical role of proactive threat detection and incident response in maintaining a secure operational environment. By leveraging Microsoft Sentinel's advanced capabilities, and significantly improving the ability to detect, respond to, and mitigate cybersecurity threats, thereby ensuring the ongoing protection of digital assets. Additionally, metrics were measured in the insecure environment before security controls were applied, and then again after implementing security measures. It is noteworthy that the number of security events and incidents were drastically reduced after the security controls were applied, demonstrating their effectiveness.

It is worth noting that if the resources within the network were heavily utilized by regular users, it is likely that more security events and alerts may have been generated within the 24-hour period following the implementation of the security controls.

