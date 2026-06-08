# Stellar Intune Baseline

## Windows Policy Reference

The table below lists all policies from the upstream [OpenIntuneBaseline](https://github.com/SkipToTheEndpoint/OpenIntuneBaseline) and their status in this baseline.

✅ Included — no changes from upstream
✏️ Modified — settings differ from upstream
❌ Excluded — not deployed

| Policy Name | Status | Reasoning |
|:---|:---:|:---|
| **Compliance Policies** | | |
| Win - OIB - Compliance - U - Device Health - v3.1 | ✅ | |
| Win - OIB - Compliance - U - Device Security - v3.1 | ✅ | |
| Win - OIB - Compliance - U - Password - v3.1 | ✅ | |
| Win - OIB - Compliance - U - Defender for Endpoint - v3.1 | ❌ | Third-party EDR/MDR solution in place |
| **Device Configuration** | | |
| Win - OIB - TP - Health Monitoring - D - Endpoint Analytics - v3.4 | ✅ | |
| **Endpoint Security** | | |
| Win - OIB - ES - Attack Surface Reduction - D - ASR Rules (Audit Mode) - v3.1 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Attack Surface Reduction - D - ASR Rules (L2) - v3.7 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Defender Antivirus - D - AV Configuration - v3.3 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Defender Antivirus - D - Security Experience - v3.3 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Defender Antivirus Updates - Ring 1 - Pilot - v3.4 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Defender Antivirus Updates - Ring 2 - UAT - v3.4 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Defender Antivirus Updates - Ring 3 - Production - v3.4 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - ES - Encryption - D - BitLocker (OS Disk) - v3.7 | ✅ | |
| Win - OIB - ES - Encryption - U - Personal Data Encryption - v3.4 | ❌ | Not supported on Windows 11 Pro / Microsoft 365 Business Premium |
| Win - OIB - ES - Windows Firewall - D - Firewall Configuration - v3.1 | ✏️ | Firewall logging disabled — see comparison below |
| Win - OIB - ES - Windows Firewall - D - Security Rules - v3.8 | ✅ | |
| Win - OIB - ES - Local Group Membership - D - Local Administrators - v3.7 | ✅ | |
| Win - OIB - ES - Windows Hello for Business - D - WHfB Configuration - v3.2 | ✅ | |
| Win - OIB - ES - Windows LAPS - D - LAPS Configuration (24H2+) - v3.6 | ✏️ | Post-authentication settings adjusted — see comparison below |
| Win - OIB - ES - Windows LAPS - D - LAPS Configuration - v3.1 | ❌ | All devices on Windows 11 24H2+; superseded by 24H2+ policy |
| **Settings Catalog** | | |
| Win - OIB - SC - Credential Management - D - Passwordless - v3.3 | ✅ | |
| Win - OIB - SC - Defender Antivirus - D - Additional Configuration - v3.8 | ❌ | Third-party EDR/MDR solution in place |
| Win - OIB - SC - Device Security - D - Administrator Protection - v3.7 | ❌ | Not yet assessed |
| Win - OIB - SC - Device Security - D - Audit and Event Logging - v3.7 | ✅ | |
| Win - OIB - SC - Device Security - D - Config Refresh - v3.2 | ✅ | |
| Win - OIB - SC - Device Security - D - Enhanced Phishing Protection - v3.0 | ✅ | |
| Win - OIB - SC - Device Security - D - Local Security Policies (24H2+) - v3.6 | ✏️ | UAC prompts use standard desktop — see comparison below |
| Win - OIB - SC - Device Security - D - Local Security Policies - v3.0 | ❌ | All devices on Windows 11 24H2+; superseded by 24H2+ policy |
| Win - OIB - SC - Device Security - D - Location and Privacy - v3.2 | ✏️ | Location access relaxed for operational needs — see comparison below |
| Win - OIB - SC - Device Security - D - Login and Lock Screen - v3.8 | ✅ | |
| Win - OIB - SC - Device Security - D - Printing - v3.7 | ✅ | |
| Win - OIB - SC - Device Security - D - Remote Desktop Services and RPC - v3.0 | ✅ | |
| Win - OIB - SC - Device Security - D - Script File Associations - v3.4 | ❌ | Breaks legitimate business scripts |
| Win - OIB - SC - Device Security - D - Security Hardening - v3.7 | ✏️ | Wireless display and network settings adjusted — see comparison below |
| Win - OIB - SC - Device Security - D - Timezone - v3.4 | ✅ | |
| Win - OIB - SC - Device Security - D - User Rights - v3.7 | ✅ | |
| Win - OIB - SC - Device Security - D - Windows Package Manager - v3.5 | ❌ | Restricting Winget causes issues with legitimate workflows |
| Win - OIB - SC - Device Security - D - Windows Subsystem for Linux - v3.2 | ✏️ | Custom networking enabled for developer use — see comparison below |
| Win - OIB - SC - Device Security - U - Device Guard, Credential Guard and HVCI - v3.7 | ❌ | Not supported on Windows 11 Pro |
| Win - OIB - SC - Device Security - U - Power and Device Lock - v3.6 | ✏️ | Sleep timeout extended for plugged-in devices — see comparison below |
| Win - OIB - SC - Device Security - U - Windows Sandbox - v3.4 | ✅ | |
| Win - OIB - SC - Device Security - U - Windows Spotlight and Org Messages - v3.0 | ❌ | Not supported on Windows 11 Pro |
| Win - OIB - SC - Internet Explorer (Legacy) - D - Security - v3.1.1 | ✅ | |
| Win - OIB - SC - Microsoft Accounts - D - Configuration - v3.2 | ✅ | |
| Win - OIB - SC - Microsoft Edge - D - Security - v3.8 | ✏️ | SSL override permitted; download restrictions relaxed — see comparison below |
| Win - OIB - SC - Microsoft Edge - D - Updates - v3.6 | ✅ | |
| Win - OIB - SC - Microsoft Edge - U - Extensions - v3.1 | ✏️ | Custom extension set deployed — see comparison below |
| Win - OIB - SC - Microsoft Edge - U - Password Management - v3.0 | ✏️ | Third-party password manager in use — see comparison below |
| Win - OIB - SC - Microsoft Edge - U - Profiles, Sign-In and Sync - v3.0 | ✏️ | Sign-in not enforced; profile management relaxed — see comparison below |
| Win - OIB - SC - Microsoft Edge - U - User Experience - v3.8 | ✏️ | Google search retained; notification controls omitted — see comparison below |
| Win - OIB - SC - Microsoft Office - D - Security - v3.6 | ❌ | Not supported with Microsoft 365 Business Premium |
| Win - OIB - SC - Microsoft Office - D - Updates - v3.0 | ✅ | |
| Win - OIB - SC - Microsoft Office - U - Config and Experience - v3.6 | ✅ | |
| Win - OIB - SC - Microsoft Office - U - Security - v3.6 | ✅ | |
| Win - OIB - SC - Microsoft OneDrive - D - Configuration - v3.2 | ✅ | |
| Win - OIB - SC - Microsoft OneDrive - U - Configuration - v3.8 | ✅ | |
| Win - OIB - SC - Microsoft Store - D - Configuration - v3.8 | ✅ | |
| Win - OIB - SC - Microsoft Store - U - Configuration - v3.3 | ✅ | |
| Win - OIB - SC - Network Security - D - Disable NTLM - v3.8 | ✅ | |
| Win - OIB - SC - Windows Apps - D - In-Box App Removal - v3.7 | ❌ | Not supported on Windows 11 Pro |
| Win - OIB - SC - Windows Hello for Business - D - Cloud Kerberos Trust - v3.5 | ✅ | |
| Win - OIB - SC - Windows Update for Business - D - Delivery Optimisation - v3.0 | ✅ | |
| Win - OIB - SC - Windows Update for Business - D - Reports and Telemetry - v3.0 | ✅ | |
| Win - OIB - SC - Windows User Experience - D - Automatic Restart Sign-On - v3.8 | ✅ | |
| Win - OIB - SC - Windows User Experience - D - Feature Configuration - v3.8 | ✏️ | News and interests (widgets) disabled — see comparison below |
| Win - OIB - SC - Windows User Experience - D - Settings Sync - v3.7 | ❌ | Settings sync permitted by choice |
| Win - OIB - SC - Windows User Experience - U - Copilot - v3.8 | ❌ | Copilot permitted by choice |
| **Update Policies** | | |
| Win - OIB - WUfB - Ring 1 - Pilot - v3.0 | ❌ | Third-party RMM solution manages Windows Update |
| Win - OIB - WUfB - Ring 2 - UAT - v3.0 | ❌ | Third-party RMM solution manages Windows Update |
| Win - OIB - WUfB - Ring 3 - Production - v3.0 | ❌ | Third-party RMM solution manages Windows Update |
| **Driver Update Profiles** | | |
| Win - OIB - WUfB Drivers - Ring 1 - Pilot - v3.0 | ❌ | Third-party RMM solution manages Windows Update |
| Win - OIB - WUfB Drivers - Ring 2 - UAT - v3.0 | ❌ | Third-party RMM solution manages Windows Update |
| Win - OIB - WUfB Drivers - Ring 3 - Production - v3.0 | ❌ | Third-party RMM solution manages Windows Update |

---

## OIB vs SIB Policy Comparison

This section summarises the functional differences between the upstream OpenIntuneBaseline (OIB) and the Stellar Intune Baseline (SIB). Only policies with setting-level differences are listed.

---

### ES - Windows Firewall - Firewall Configuration

**Versions:** OIB v3.1 / SIB v3.1 — ⚠️ **8 value differences (all logging/auditing)**

| Setting | OIB | SIB |
|---------|-----|-----|
| Audit: Filtering Platform Connection | `2` (Success auditing) | `0` (No auditing) |
| Audit: Filtering Platform Packet Drop | `2` (Success auditing) | `0` (No auditing) |
| Domain profile: Log dropped packets | `true` | `false` |
| Domain profile: Log successful connections | `true` | `false` |
| Private profile: Log dropped packets | `true` | `false` |
| Private profile: Log successful connections | `true` | `false` |
| Public profile: Log dropped packets | `true` | `false` |
| Public profile: Log successful connections | `true` | `false` |

> **Risk:** SIB has zero firewall logging across all profiles and no connection auditing. This significantly limits incident detection and investigation capability.

---

### ES - Windows LAPS - LAPS Configuration (24H2+)

**Versions:** OIB v3.6 / SIB v3.6 — ⚠️ **1 value difference, 1 setting missing from SIB**

**Value differences:**

| Setting | OIB | SIB |
|---------|-----|-----|
| Post-authentication reset delay | `1` hour | `0` (Immediate / disabled) |

**Settings missing from SIB entirely:**

| Setting | OIB Value |
|---------|-----------|
| Post-authentication actions | `11` (Reset password + sign out + terminate processes) |

> **Risk:** Missing post-authentication actions means SIB has no defined cleanup after LAPS credential use — the session may persist longer than intended.

---

### SC - Device Security - Local Security Policies (24H2+)

**Versions:** OIB v3.6 / SIB v3.6 — ⚠️ **3 value differences**

| Setting | OIB | SIB |
|---------|-----|-----|
| UAC: Behavior of elevation prompt for administrators | `2` (Prompt for consent — secure desktop) | `4` (Prompt for consent — standard desktop) |
| UAC: Behavior of elevation prompt for standard users | `1` (Prompt for credentials — secure desktop) | `3` (Prompt for credentials — standard desktop) |
| UAC: Switch to secure desktop when prompting for elevation | `1` (Enabled) | `0` (Disabled) |

> **Risk:** SIB disables the secure desktop for all UAC prompts. All three settings are consistent — UAC prompts appear on the standard desktop rather than the isolated secure desktop, which is more susceptible to spoofing by malicious foreground applications.

---

### SC - Device Security - Location and Privacy

**Versions:** OIB v3.2 / SIB v3.2 — ⚠️ **Multiple differences**

| Setting | OIB | SIB |
|---------|-----|-----|
| Let apps access location (`letappsaccesslocation`) | `0` (User in control) | `1` (Force allow) |
| Allow location (`system_allowlocation`) | `1` (Allowed, not user-overridable) | `2` (Allowed, user can override) |
| Let apps access location — force allow these apps | `windows.immersivecontrolpanel`, `Microsoft.OutlookForWindows` | ❌ Missing entirely |

> **Note:** OIB locks down location with a specific app allowlist. SIB is more permissive — all apps force-allowed and users can change system location settings.

---

### SC - Device Security - Security Hardening

**Versions:** OIB v3.7 / SIB v3.7 — ⚠️ **4 value differences, 5 settings missing from SIB**

**Value differences:**

| Setting | OIB | SIB |
|---------|-----|-----|
| WCM: Minimize simultaneous connections | `1` (Enabled) | `0` (Disabled) |
| Prohibit connection to non-domain networks when connected to domain | `1` (Enabled) | `0` (Disabled) |
| Wireless Display: Allow projection to this PC | `0` (Disabled) | `1` (Enabled) |
| Wireless Display: Require PIN for pairing | `1` (Required) | `0` (Not required) |

**Settings missing from SIB entirely:**

| Setting | OIB Value |
|---------|-----------|
| WCM: Minimize connections — options sub-setting | `3` |
| LanmanWorkstation: Audit insecure guest logon | `1` (Enabled) |
| LanmanWorkstation: Audit server doesn't support encryption | `1` (Enabled) |
| LanmanWorkstation: Audit server doesn't support signing | `1` (Enabled) |
| Sudo: Enable sudo | `0` (Disabled) |

> **Risk:** Wireless display projection allowed without PIN in SIB is a meaningful security regression. Missing LanmanWorkstation audit settings reduce visibility into SMB security issues. Missing sudo disable leaves the feature in its default state.

---

### SC - Device Security - Windows Subsystem for Linux

**Versions:** OIB v3.2 / SIB v3.2 — ⚠️ **1 value difference**

| Setting | OIB | SIB |
|---------|-----|-----|
| WSL: Custom networking user setting configurable | `0` (Disabled) | `1` (Enabled) |

> **Note:** SIB allows users to configure custom WSL networking. May be intentional for developer users.

---

### SC - Device Security - U - Power and Device Lock

**Versions:** OIB v3.6 / SIB v3.6 — ⚠️ **1 value difference**

| Setting | OIB | SIB |
|---------|-----|-----|
| Unattended sleep timeout (plugged in) | `900s` (15 min) | `2700s` (45 min) |

> **Note:** Likely a deliberate UX change — 15 minutes is aggressive for a plugged-in device.

---

### SC - Microsoft Edge - D - Security

**Versions:** OIB v3.8 / SIB v3.8 — ⚠️ **3 value differences**

| Setting | OIB | SIB |
|---------|-----|-----|
| Download restrictions | `1` (Enabled, block all) | `0` (Disabled) |
| SSL error override allowed | `0` (Blocked) | `1` (Users can bypass SSL errors) |
| Feature flag overrides control | `1` (Enabled) | `0` (Disabled) |

> **Risk:** SSL error override allowed in SIB lets users bypass certificate errors. Download restrictions disabled in SIB removes a meaningful defence against malicious downloads.

---

### SC - Microsoft Edge - U - Extensions

**Versions:** OIB v3.1 / SIB v3.1 — ⚠️ **Major differences**

**Value differences:**

| Setting | OIB | SIB |
|---------|-----|-----|
| Force-installed extensions | `nkbndigcebkoaejohleckhekfmcecfja`, `ofefcgjbeghpigppfmkologfjadafddi` | `lfochlioelphaglamdcakfjemolpichk`, `gaaceiggkkiffbfdpmfapegoiohkiipl` |

**Settings missing from SIB entirely:**

| Setting | OIB Value |
|---------|-----------|
| Extension install allow list | `0` (Disabled — blocklist controls access) |
| Block external extensions | `1` (Enabled) |
| Extension install block list | `*` (Block all extensions) |

> **Risk:** SIB has no blocklist, meaning users can install any Edge extension. Force-installed extension IDs are completely different between OIB and SIB — confirm SIB extensions are intentional.

---

### SC - Microsoft Edge - U - Password Management

**Versions:** OIB v3.0 / SIB v3.0 — ⚠️ **Major differences**

**Value differences:**

| Setting | OIB | SIB |
|---------|-----|-----|
| Password manager enabled | `1` (Enabled) | `0` (Disabled) |

**Settings missing from SIB entirely:**

| Setting | OIB Value |
|---------|-----------|
| Password monitor allowed (breach detection) | `1` (Enabled) |
| Password generator enabled | `1` (Enabled) |
| Primary password setting | `1` (Enabled, requires primary password to access saved passwords) |

> **Note:** SIB disables the Edge password manager entirely — likely intentional if a third-party password manager is in use.

---

### SC - Microsoft Edge - U - Profiles, Sign-In and Sync

**Versions:** OIB v3.0 / SIB v3.0 — ⚠️ **3 value differences, 1 extra setting in SIB**

**Value differences:**

| Setting | OIB | SIB |
|---------|-----|-----|
| Implicit sign-in enabled | `1` (Enabled) | `0` (Disabled) |
| Browser add profile enabled | `0` (Disabled) | `1` (Enabled) |
| Browser sign-in mode | `2` (Force sign-in) | `1` (Allow sign-in) |

**Only in SIB:**

| Setting | Value |
|---------|-------|
| Hide first run experience | `1` (Enabled — skips welcome screen) |

> **Note:** SIB does not force Edge sign-in and allows users to add profiles. The hide first run setting is a benign UX addition.

---

### SC - Microsoft Edge - U - User Experience

**Versions:** OIB v3.8 / SIB v3.8 — ⚠️ **4 settings missing from SIB, 5 extra settings in SIB**

**No value conflicts** — all shared settings are identical.

**Only in OIB (missing from SIB):**

| Setting | OIB Value |
|---------|-----------|
| What's New page for Entra profiles enabled | `0` (Disabled) |
| URL blocklist | Enabled, blocking `apps.microsoft.com` and variants |
| Default notifications setting | `2` (Block by default) |
| Notifications allowed for URLs | `*.microsoft.com`, `*.cloud.microsoft` |

**Only in SIB (not in OIB):**

| Setting | SIB Value |
|---------|-----------|
| New tab page search box | `redirect` (recommended) |
| Default search provider name | Google (recommended) |
| Default search provider URL | Full Google search URL (recommended) |
| Default search provider enabled | `1` (Enabled, recommended) |
| Homepage is new tab page | `1` (Enabled, recommended) |

> **Note:** SIB retains Google as the recommended default search provider (removed from OIB v3.8). The OIB URL blocklist for apps.microsoft.com and notification controls are not deployed in SIB.

---

### SC - Windows User Experience - D - Feature Configuration

**Versions:** OIB v3.8 / SIB v3.8 — ⚠️ **1 value difference**

| Setting | OIB | SIB |
|---------|-----|-----|
| Allow news and interests | `1` (Enabled) | `0` (Disabled) |

> **Note:** SIB disables the Windows news and interests / widgets feature on the taskbar.

---

## Policies Requiring Attention

The following policies have security-relevant differences that should be reviewed and remediated:

| Priority | Policy | Issue |
|----------|--------|-------|
| 🔴 High | ES - Windows Firewall - Firewall Configuration | All firewall logging disabled in SIB — no visibility into dropped packets or connections |
| 🔴 High | SC - Microsoft Edge - D - Security | SSL error override allowed in SIB; download restrictions disabled; feature flag overrides disabled |
| 🔴 High | SC - Microsoft Edge - U - Extensions | No extension blocklist in SIB — users can install any extension |
| 🔴 High | SC - Device Security - Security Hardening | Wireless display projection without PIN allowed in SIB; LanmanWorkstation auditing missing; sudo not explicitly disabled |
| 🟡 Medium | ES - Windows LAPS - LAPS Configuration (24H2+) | Post-authentication actions not configured in SIB; reset delay set to 0 (immediate) |
| 🟡 Medium | SC - Device Security - Local Security Policies (24H2+) | UAC secure desktop disabled in SIB; all three UAC prompt settings use standard desktop instead |
| 🟡 Medium | SC - Device Security - Location and Privacy | SIB significantly more permissive on location access |
| 🟡 Medium | SC - Microsoft Edge - U - Password Management | Edge password manager disabled in SIB with no alternative controls |
| 🟢 Low | SC - Device Security - Windows Subsystem for Linux | WSL custom networking user-configurable in SIB |
| 🟢 Low | SC - Microsoft Edge - U - Profiles, Sign-In and Sync | Sign-in not forced in SIB; users can add profiles |
| 🟢 Low | SC - Microsoft Edge - U - User Experience | SIB missing OIB URL blocklist (apps.microsoft.com) and notification controls; SIB adds Google as recommended search provider |
| 🟢 Low | SC - Windows User Experience - D - Feature Configuration | News and interests (widgets) disabled in SIB |
| 🟢 Low | SC - Device Security - U - Power and Device Lock | Sleep timeout tripled in SIB (likely intentional UX change) |
