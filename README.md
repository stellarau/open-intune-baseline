# Stellar Intune Baseline

## Windows Policy Reference

The table below lists all policies from the upstream [OpenIntuneBaseline](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline) and their status in this baseline.

| Policy Name | Status |
|---|---|
| **Compliance Policies** | |
| Win - OIB - Compliance - U - Device Health - v3.1 | Included |
| Win - OIB - Compliance - U - Device Security - v3.1 | Included |
| Win - OIB - Compliance - U - Password - v3.1 | Included |
| Win - OIB - Compliance - U - Defender for Endpoint - v3.1 | Excluded |
| **Device Configuration** | |
| Win - OIB - TP - Health Monitoring - D - Endpoint Analytics - v3.4 | Included |
| **Driver Update Profiles** | |
| Win - OIB - WUfB Drivers - Ring 1 - Pilot - v3.0 | Excluded |
| Win - OIB - WUfB Drivers - Ring 2 - UAT - v3.0 | Excluded |
| Win - OIB - WUfB Drivers - Ring 3 - Production - v3.0 | Excluded |
| **Endpoint Security — Attack Surface Reduction** | |
| Win - OIB - ES - Attack Surface Reduction - D - ASR Rules (Audit Mode) - v3.1 | Excluded |
| Win - OIB - ES - Attack Surface Reduction - D - ASR Rules (L2) - v3.7 | Excluded |
| **Endpoint Security — Defender Antivirus** | |
| Win - OIB - ES - Defender Antivirus - D - AV Configuration - v3.3 | Excluded |
| Win - OIB - ES - Defender Antivirus - D - Security Experience - v3.3 | Excluded |
| Win - OIB - ES - Defender Antivirus Updates - Ring 1 - Pilot - v3.4 | Excluded |
| Win - OIB - ES - Defender Antivirus Updates - Ring 2 - UAT - v3.4 | Excluded |
| Win - OIB - ES - Defender Antivirus Updates - Ring 3 - Production - v3.4 | Excluded |
| **Endpoint Security — Encryption** | |
| Win - OIB - ES - Encryption - D - BitLocker (OS Disk) - v3.7 | Included |
| Win - OIB - ES - Encryption - U - Personal Data Encryption - v3.4 | Excluded |
| **Endpoint Security — Firewall** | |
| Win - OIB - ES - Windows Firewall - D - Firewall Configuration - v3.1 | Included |
| Win - OIB - ES - Windows Firewall - D - Security Rules - v3.8 | Included |
| **Endpoint Security — Local Group Membership** | |
| Win - OIB - ES - Local Group Membership - D - Local Administrators - v3.7 | Included |
| **Endpoint Security — Windows Hello for Business** | |
| Win - OIB - ES - Windows Hello for Business - D - WHfB Configuration - v3.2 | Included |
| **Endpoint Security — Windows LAPS** | |
| Win - OIB - ES - Windows LAPS - D - LAPS Configuration (24H2+) - v3.6 | Included |
| Win - OIB - ES - Windows LAPS - D - LAPS Configuration - v3.1 | Excluded |
| **Settings Catalog — Credential Management** | |
| Win - OIB - SC - Credential Management - D - Passwordless - v3.3 | Included |
| **Settings Catalog — Defender Antivirus** | |
| Win - OIB - SC - Defender Antivirus - D - Additional Configuration - v3.8 | Excluded |
| **Settings Catalog — Device Security** | |
| Win - OIB - SC - Device Security - D - Administrator Protection - v3.7 | Excluded |
| Win - OIB - SC - Device Security - D - Audit and Event Logging - v3.7 | Included |
| Win - OIB - SC - Device Security - D - Config Refresh - v3.2 | Included |
| Win - OIB - SC - Device Security - D - Enhanced Phishing Protection - v3.0 | Included |
| Win - OIB - SC - Device Security - D - Local Security Policies (24H2+) - v3.6 | Included |
| Win - OIB - SC - Device Security - D - Local Security Policies - v3.0 | Excluded |
| Win - OIB - SC - Device Security - D - Location and Privacy - v3.2 | Included |
| Win - OIB - SC - Device Security - D - Login and Lock Screen - v3.8 | Included |
| Win - OIB - SC - Device Security - D - Printing - v3.7 | Included |
| Win - OIB - SC - Device Security - D - Remote Desktop Services and RPC - v3.0 | Included |
| Win - OIB - SC - Device Security - D - Script File Associations - v3.4 | Excluded |
| Win - OIB - SC - Device Security - D - Security Hardening - v3.7 | Included |
| Win - OIB - SC - Device Security - D - Timezone - v3.4 | Included |
| Win - OIB - SC - Device Security - D - User Rights - v3.7 | Included |
| Win - OIB - SC - Device Security - D - Windows Package Manager - v3.5 | Excluded |
| Win - OIB - SC - Device Security - D - Windows Subsystem for Linux - v3.2 | Included |
| Win - OIB - SC - Device Security - U - Device Guard, Credential Guard and HVCI - v3.7 | Excluded |
| Win - OIB - SC - Device Security - U - Power and Device Lock - v3.6 | Included |
| Win - OIB - SC - Device Security - U - Windows Sandbox - v3.4 | Included |
| Win - OIB - SC - Device Security - U - Windows Spotlight and Org Messages - v3.0 | Excluded |
| **Settings Catalog — Internet Explorer (Legacy)** | |
| Win - OIB - SC - Internet Explorer (Legacy) - D - Security - v3.1.1 | Included |
| **Settings Catalog — Microsoft Accounts** | |
| Win - OIB - SC - Microsoft Accounts - D - Configuration - v3.2 | Included |
| **Settings Catalog — Microsoft Edge** | |
| Win - OIB - SC - Microsoft Edge - D - Security - v3.8 | Included |
| Win - OIB - SC - Microsoft Edge - D - Updates - v3.6 | Included |
| Win - OIB - SC - Microsoft Edge - U - Extensions - v3.1 | Included |
| Win - OIB - SC - Microsoft Edge - U - Password Management - v3.0 | Included |
| Win - OIB - SC - Microsoft Edge - U - Profiles, Sign-In and Sync - v3.0 | Included |
| Win - OIB - SC - Microsoft Edge - U - User Experience - v3.8 | Included |
| **Settings Catalog — Microsoft Office** | |
| Win - OIB - SC - Microsoft Office - D - Security - v3.6 | Included |
| Win - OIB - SC - Microsoft Office - D - Updates - v3.0 | Included |
| Win - OIB - SC - Microsoft Office - U - Config and Experience - v3.6 | Included |
| Win - OIB - SC - Microsoft Office - U - Security - v3.6 | Included |
| **Settings Catalog — Microsoft OneDrive** | |
| Win - OIB - SC - Microsoft OneDrive - D - Configuration - v3.2 | Included |
| Win - OIB - SC - Microsoft OneDrive - U - Configuration - v3.8 | Included |
| **Settings Catalog — Microsoft Store** | |
| Win - OIB - SC - Microsoft Store - D - Configuration - v3.8 | Included |
| Win - OIB - SC - Microsoft Store - U - Configuration - v3.3 | Included |
| **Settings Catalog — Network Security** | |
| Win - OIB - SC - Network Security - D - Disable NTLM - v3.8 | Included |
| **Settings Catalog — Windows Apps** | |
| Win - OIB - SC - Windows Apps - D - In-Box App Removal - v3.7 | Excluded |
| **Settings Catalog — Windows Hello for Business** | |
| Win - OIB - SC - Windows Hello for Business - D - Cloud Kerberos Trust - v3.5 | Included |
| **Settings Catalog — Windows Update for Business** | |
| Win - OIB - SC - Windows Update for Business - D - Delivery Optimisation - v3.0 | Included |
| Win - OIB - SC - Windows Update for Business - D - Reports and Telemetry - v3.0 | Included |
| **Settings Catalog — Windows User Experience** | |
| Win - OIB - SC - Windows User Experience - D - Automatic Restart Sign-On - v3.8 | Included |
| Win - OIB - SC - Windows User Experience - D - Feature Configuration - v3.8 | Included |
| Win - OIB - SC - Windows User Experience - D - Settings Sync - v3.7 | Excluded |
| Win - OIB - SC - Windows User Experience - U - Copilot - v3.8 | Excluded |
| **Update Policies** | |
| Win - OIB - WUfB - Ring 1 - Pilot - v3.0 | Excluded |
| Win - OIB - WUfB - Ring 2 - UAT - v3.0 | Excluded |
| Win - OIB - WUfB - Ring 3 - Production - v3.0 | Excluded |
