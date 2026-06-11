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
| MacOS - OIB - Device Security - D - Accounts and Login - v1.0 | ✏️ | Hiding admin accounts at the login window reduces the attack surface by not advertising privileged account names |
| MacOS - OIB - Device Security - D - Restrictions - v1.0 | ✏️ | OIB restrictions relaxed to support normal user productivity; iCloud services, AirDrop, Siri and sharing features enabled |
| MacOS - OIB - Disk Encryption - D - FileVault - v1.0 | ✏️ | Explicitly set showrecoverykey to false to prevent the personal recovery key being displayed to the user during FileVault setup |
| MacOS - OIB - Firewall - D - Gatekeeper - v1.0 | ✏️ | OIB restrictions relaxed to support normal user productivity; firewall stealth mode disabled |
| MacOS - OIB - Microsoft AutoUpdate - D - MAU Configuration - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - D - Password Management - v1.0 | ✏️ | Edge built-in password manager and breach monitoring disabled in favour of a third-party password manager |
| MacOS - OIB - Microsoft Edge - D - Security - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Edge - U - Extensions - v1.0 | ✏️ | Allows ability to install extensions |
| MacOS - OIB - Microsoft Edge - U - Profiles, Sign-In and Sync - v1.0 | ✏️ | Users permitted to add additional Edge profiles |
| MacOS - OIB - Microsoft Edge - U - Updates - v1.0 | ✅ | |
| MacOS - OIB - Microsoft Office - D - Office Configuration - v1.0 | ✅ | |
| MacOS - OIB - Microsoft OneDrive - D - Service and Access - v1.0 | ✏️ | Deprecated `allowed` key removed from TCC Full Disk Access entry to prevent policy application issues |
| MacOS - OIB - Microsoft OneDrive - U - Known Folder Move - v1.0 | ✅ | |
| MacOS - OIB - Updates - D - Update Configuration - v1.0 | ✅ | |
| **SIB Custom Policies** | | |
| MacOS - SIB - Microsoft Edge - D - Privacy and Search - v1.0 | ➕ | Enforces Google as the default search provider and directs new tab search to the address bar |
