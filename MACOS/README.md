# macOS Policy Reference

The table below lists all policies from the upstream [OpenIntuneBaseline](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline) and their status in this baseline.

✅ Included — no changes from upstream
✏️ Modified — settings differ from upstream
❌ Excluded — not deployed
➕ SIB custom policy — not from OIB

| Policy Name | Status | Reasoning |
|:---|:---:|:---|
| **Compliance Policies** | | |
| MacOS - OIB - Compliance - U - Device Health - v1.0 | ✅ | |
| MacOS - OIB - Compliance - U - Device Security - v1.0 | ✏️ | Block all incoming connections disabled to permit AirDrop and approved network services |
| MacOS - OIB - Compliance - U - Password - v1.0 | ✅ | |
| **Settings Catalog** | | |
| MacOS - OIB - Authentication - D - Platform SSO - v1.0 | ✅ | |
| MacOS - OIB - Defender Antivirus - D - Antivirus Configuration - v1.0 | ✅ | |
| MacOS - OIB - Defender Antivirus - D - MDE Configuration - v1.0 | ✅ | |
| MacOS - OIB - Device Security - D - Accounts and Login - v1.0 | ✅ | |
| MacOS - OIB - Device Security - D - Restrictions - v1.0 | ✅ | |
| MacOS - OIB - Disk Encryption - D - FileVault - v1.0 | ✅ | |
| MacOS - OIB - Firewall - D - Gatekeeper - v1.0 | ✅ | |
| MacOS - OIB - Microsoft AutoUpdate - D - MAU Configuration - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - D - Password Management - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - D - Security - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - U - Extensions - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - U - Profiles, Sign-In and Sync - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - U - Updates - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Office - D - Office Configuration - v1.0 | ✅ | |
| MacOS - OIB - Microsoft OneDrive - D - Service and Access - v1.0 | ✅ | |
| MacOS - OIB - Microsoft OneDrive - U - Known Folder Move - v1.0 | ✅ | |
| MacOS - OIB - Updates - D - Update Configuration - v1.0 | ✅ | |
