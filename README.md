# Microsoft Azure SOC and Honeynet Lab
<img src="https://imgur.com/nP8qbly.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>



## Introduction

In this project, I constructed a compact honeynet within the Microsoft Azure environment, seamlessly integrating log sources from diverse platforms into a Log Analytics workspace. This meticulously curated data was subsequently harnessed by Microsoft Sentinel to craft comprehensive attack maps, generate alerts, and curate detailed incident reports. Over a 24-hour period, I systematically gauged pertinent security metrics within the initially insecure environment, providing a baseline for subsequent evaluation. Following this assessment, a series of targeted security controls were implemented to fortify the system's resilience. Another 24-hour metric measurement cycle ensued, capturing the impact of the applied security measures on the environment's overall security posture. The results of this comparative analysis offer valuable insights into the effectiveness of the implemented controls and their influence on the observed security metrics. In this comprehensive exploration, I delve into key security indicators, shedding light on the dynamic evolution of the security landscape within the Azure-based honeynet environment. The metrics we will show include:

- SecurityEvent (Windows Event Logs) 
- Syslog (Linux Event Logs) 
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

## Architecture Before Hardening / Security Controls<BR>

<img src="https://imgur.com/3uESg96.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
In deliberately configuring the firewalls or network security groups on the virtual machines to be wide open, the intention is to create an enticing environment for ethical hacking or penetration testing purposes. This strategic decision serves a dual purpose: first, it simulates a scenario where the virtual network mimics a vulnerable system, similar to real-world scenarios where inadequate security configurations may be exploited. This simulated vulnerability provides a controlled space for ethical hackers to assess and identify potential weaknesses.

Intentionally exposing the virtual machines with lenient firewall settings, encourages active attempts by hackers to exploit these vulnerabilities. This proactive engagement aids in the identification and analysis of potential threat vectors and attack patterns. The insights gained from such simulated attacks contribute significantly to the enhancement of security measures, allowing for the refinement of defensive strategies, incident response protocols, and the overall fortification of the virtual network against real-world cyber threats.

It is important to note that this approach should only be undertaken in a controlled, ethical, and monitored environment to ensure that the simulated attacks do not pose any actual risks to sensitive data or systems. The ultimate goal is to strengthen the security posture of the virtual network through the identification and mitigation of potential vulnerabilities.

## Architecture After Hardening / Security Controls
<img src="https://imgur.com/VIUbiId.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>

The architecture of the mini honeynet in Azure encompasses several key components, including:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 Windows, 1 Linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel

In the refined configuration ("AFTER" metrics), notable improvements were implemented in security measures. Network Security Groups were strengthened by blocking ALL traffic, allowing communication exclusively with my Private Virtual Network. Moreover, all other resources were bolstered with their built-in firewalls, and communication was strictly confined to the internal private virtual network. This thorough security update aims to minimize potential risks, guaranteeing that access is restricted solely to authorized entities within the bounds of the internal private virtual network. These measures adhere to industry best practices and significantly enhance the security posture of the mini honeynet environment in Azure.

## NSG-Malicious-Allowed-in
<img src="https://imgur.com/nngjJBR.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

## Linux-SSH-Auth-Fail
<img src="https://imgur.com/ODqxutg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

## MSSQL-Auth-Fail
<img src="https://imgur.com/JqfC5bA.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

## Windows-RDP-Auth-Fails
<img src="https://imgur.com/W3BTWV7.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

## Metrics Before Hardening / Security Controls
The following table shows the metrics we measured in our insecure environment for 24 hours:
Start Time 11-08-2023 18:02:44
Stop Time 11-09-2023 18:02:45

| Metric                                                         | Count
| -------------------------------------------------------------- | -----
| SecurityEvent (windows-Vm)                                     | 66,985
| Syslog (Linux-VM)                                              | 1,449
| SecurityAlert (Microsoft Fedender for Cloud)                   | 6
| SecurityIncident (Sentinel Incidents)                          | 146
| AzureNetworkAnalytics_CL (NSG Inbound Malicious Flows Allowed) | 2,646


## Metrics After Hardening / Security Controls

The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:
Start Time 11-13-2023 16:28:27
Stop Time	11-14-2023 16:28:27

| Metric                                                         | Count
| -------------------------------------------------------------- | -----
| SecurityEvent (windows-Vm)                                     | 0
| Syslog (Linux-VM)                                              | 1
| SecurityAlert (Microsoft Fedender for Cloud)                   | 0
| SecurityIncident (Sentinel Incidents)                          | 0
| AzureNetworkAnalytics_CL (NSG Inbound Malicious Flows Allowed) | 0

## Conclusion

In the culmination of this project, the construction of a mini honeynet within the Microsoft Azure environment marked a pivotal step towards fortifying the cybersecurity infrastructure. The integration of log sources into a centralized Log Analytics workspace facilitated a comprehensive and centralized approach to monitoring and analyzing security-related events. The deployment of Microsoft Sentinel as a vigilant guardian further heightened the project's efficacy, autonomously triggering alerts and orchestrating incident responses based on the rich data sets ingested.

A crucial facet of the project involved the meticulous measurement of security metrics within the initial, insecure environment, providing a baseline for comparison. Subsequent to the strategic implementation of security controls, the environment underwent a transformation. The measured metrics post-implementation revealed a substantial reduction in both security events and incidents, underscoring the tangible impact of the applied security measures.

This noteworthy decline in security events and incidents serves as compelling evidence of the effectiveness of the implemented security controls. The project not only demonstrated the capability of Microsoft Azure, Log Analytics, and Sentinel in creating a resilient security ecosystem but also emphasized the tangible outcomes achievable through proactive cybersecurity measures. These results affirm the significance of continuous monitoring, timely incident response, and the implementation of robust security controls in safeguarding digital environments against evolving cyber threats.

## The End
