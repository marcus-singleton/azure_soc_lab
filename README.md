# azure_soc_lab

# Build and Secure a Public-Facing Security Operations Center + Honeynet in Azure

--- Network Diagram Screenshot ---

## Introduction

In this project, I created a mini honeynet in Azure and ingested log sources from various resources into a Log Analytics workspace. This data was then utilized by Microsoft Sentinel to generate attack maps, trigger alerts, and create incidents. I measured several security metrics in the unsecured environment over a 24-hour period, applied security controls to strengthen the environment, and measured the metrics again for another 24 hours. The results are presented below. The metrics included are:

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

## Architecture Before Hardening / Security Controls
Screenshot

## Architecture After Hardening / Security Controls
Screenshot

Mini Honeynet Architecture:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic except my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint

## Attack Maps Before Hardening / Security Controls
Screenshot
Screenshot
Screenshot

## Metrics Before Hardening / Security Controls

The following table shows the metrics we measured in our insecure environment for 24 hours:
Start Time - ####
Stop Time - ####

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | #
| Syslog                   | #
| SecurityAlert            | #
| SecurityIncident         | #
| AzureNetworkAnalytics_CL | #

## Attack Maps Before Hardening / Security Controls

```All map queries returned no results due to no instances of malicious activity for the 24 hours after hardening.```

## Metrics After Hardening / Security Controls

The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:
Start Time - ####
Stop Time	- ####

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | #
| Syslog                   | #
| SecurityAlert            | #
| SecurityIncident         | #
| AzureNetworkAnalytics_CL | #

## Conclusion

In this project, a mini honeynet was established in Microsoft Azure, and log sources were integrated into a Log Analytics workspace. Microsoft Sentinel was utilized to trigger alerts and generate incidents based on the ingested logs. Furthermore, metrics were collected in the unsecured environment before the application of security controls and again after implementing these measures. Significantly, the number of security events and incidents was greatly reduced following the application of the security controls, highlighting their effectiveness.
Final Point: If the network resources had been heavily utilized by regular users, a greater number of security events and alerts would likely have been generated within the 24 hours following the implementation of the security controls.
