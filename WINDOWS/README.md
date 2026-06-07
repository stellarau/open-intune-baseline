# OpenIntuneBaseline - Windows

## Intended Use-Case
The baseline has been designed for, and tested on the following:

### Device:
* Windows 11 Enterprise (though should also work on Windows 10 Enterprise)
* Enrolled into Autopilot
* Autopilot configuration:
    * Deployment Mode - User Driven
    * Join Type - Microsoft Entra Joined
    * User Account Type - Standard
* Single-user device

### User:
* Cloud-Only or Hybrid Identity with Entra ID as IdP
* MFA configured via Conditional Access

### Licensing:
* M365 Business Premium or M365 E5/A5, or M365 E3/A3 + MDE P1/P2 
<br>**OR**:
    * Entra ID P1 or P2
    * Office 365 E3/E5, A3/A5 or F3
    * Intune P1
    * Defender for Business or Endpoint P1/P2

> [!NOTE]
> Some settings may report errors or as "Not Applicable" if the device is running Pro/Business rather than Enterprise.

> [!CAUTION]
> While many policies should work fine on a Multi-user (Shared) device, there are additional considerations required for these that are not covered by this baseline.

### Addressing Hybrid Join
The Windows OIB has **not** been designed for hybrid scenarios, and will likely **not work as expected or intended** on hybrid-joined devices. 

It is _**Microsoft's recommendation**_ that you move to cloud-native for new devices: https://aka.ms/CloudNativeEndpoints

I would personally recommend maintaining GPO for on-prem devices, and using Intune for cloud-native devices, with the exception of things like Endpoint Analytics, Windows Update for Business and Application Deployment. Applying Intune policy over the top of GPO can cause unexpected results, and should be avoided where possible. Similarly, GPOs may well leave registry keys behind that can cause unexpected results when applying Intune policy.

> [!IMPORTANT]
> Successful application of the baseline outside of this configuration cannot be guaranteed.

---

## Importing the Baseline:
Please reference [Importing the Baseline](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki#importing-the-baseline) for information.

---

## Baseline Security Posture
Primary information regarding adherence to security frameworks can be found in the [Wiki](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki#security-framework-adherence), however there are some notable deviations from security Windowss guidance frameworks. These are detailed below:

| Policy | Setting Name | Framework Recommendation | Baseline Setting | Rationale |
|---|---|---|---|---|
| Device Security - Local Security Policies |  |  |  |  |
|  | Accounts Enable Administrator Account Status | Disabled | Enabled | Allows usage of Windows LAPS without additional configuration or creating a new local user account. |
|  | User Account Control Behavior Of The Elevation Prompt For Standard Users | Automatically deny elevation requests | Prompt for credentials on secure desktop | Maintains standard helpdesk remote support processes capabilities. |

### Comparison against other Security Baselines
Please see [Baseline Comparison](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki/win-comparison) wiki page for more information.

As of v3.4, I have documented the rationale for not implementing specific settings against the CIS Intune Benchmark.
[OIB v3.4 vs CIS Intune v3.0.1](OIBvsCIS-Rationale.csv)

### Security Recommendations
The results of the Defender for Endpoint Security Recommendations page on a baseline-configured device can be viewed below:

[export-tvm-security-recommendations.csv](/WINDOWS/export-tvm-security-recommendations.csv)

Please note that **all** security tools, including Microsoft's own seem to have problems with the fact that CSP's put settings in different registry key locations. This is not an issue with the baseline, and is something that needs to be addressed by the security tool vendors. See the FAQ for more information:

[Security tool _y_ says setting _x_ is not configured but Intune says it's applied correctly!](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki/faq#security-tool-y-says-setting-x-is-not-configured-but-intune-says-its-applied-correctly)

### Included Settings
* Core device security hardening
* Device Encryption via BitLocker
* Google Chrome (Note: Policies are quite "Anti-Chrome" to encourage the use of Edge)
* Microsoft Edge (Split into multiple policies for easier management)
* Microsoft Office (Including OneDrive Known Folder Move)
* Microsoft Defender for Endpoint (AV, Firewall, ASR Rules)
* Windows LAPS
* Windows Update for Business (Delivery Optimisation, Telemetry & WUfB Reports)
* Windows Update Rings (3-ring model of Pilot, UAT & Production)
* Windows Hello for Business

Almost all policies are Settings Catalog-backed and will show in Devices>Configuration Profiles, however the following will appear in the Endpoint Security section of Intune:
* Defender Antivirus
* BitLocker Encryption
* Windows Firewall
* Windows Hello for Business
* Windows LAPS

For a complete list of settings, please consult [SETTINGSOUTPUT](/WINDOWS/SETTINGSOUTPUT.md).

### Policy Reference

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

### Known Limitations:
Due to the wildly differing nature of environments, it is not possible to create a "baseline" for AppLocker or Windows Defender Application Control (WDAC). While the baseline ensures standard users cannot elevate to install applications, apps that do not require elevation or install to a user's AppData folder may not be blocked.

---

## Known Issues
Please see the [Known Issues](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki/win-knownissues) wiki page for more information.

---

## Supporting Configuration:
- **Windows Autopatch** - If your licensing supports it, I would **strongly** recommend implementing Autopatch for management of your Windows Quality, Driver and Feature updates. - [Autopatch Overview](https://learn.microsoft.com/en-us/windows/deployment/windows-autopatch/overview/windows-autopatch-overview)
- **Windows Update for Business Reports** - With an appropriate Azure subscription, a Log Analytics Workspace can be created to monitor update compliance of devices. - [Additional information](https://learn.microsoft.com/en-us/windows/deployment/update/wufb-reports-overview) 
- **M365 Apps Updates** - Enabling [Cloud Update](https://learn.microsoft.com/en-us/deployoffice/admincenter/cloud-update) through [config.office.com](https://config.office.com/officeSettings/serviceprofile) can ensure Office Apps for Business/Enterprise remain up-to-date on the Monthly Enterprise Channel. Settings in the "Office - Update Settings" policy can remain as Cloud Update takes priority over any other Office management. Ensure the [Inventory](https://config.office.com/officeSettings/inventory) is enabled.

> [!NOTE]
> Guidance on this can be found in the [Settings Guidance](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki/win-settingsguidance) wiki page.

---

## Additional Information:

> [!TIP]
> For further information, please consult the [FAQ](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline/wiki/faq)
