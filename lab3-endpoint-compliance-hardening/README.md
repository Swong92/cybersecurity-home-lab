# Lab 3: Endpoint Compliance & Hardening (MDM-Style)

## Objective
Simulate an MDM/endpoint security proof-of-concept by applying common “corporate laptop” security controls on a Windows VM, validating compliance, and performing a break/fix network test from a Kali VM.

## Lab Environment
- Host: VirtualBox
- Windows VM: Windows 10 (target endpoint)
- Kali VM: Kali Linux (validation/testing)
- Network Mode: NAT Network / Host-Only (document which you used)

## Tools / Features Used
- BitLocker (disk encryption)
- Local Security Policy (`secpol.msc`) for password + lockout policy
- Windows Defender Firewall
- Microsoft Defender Antivirus
- Event Viewer (audit evidence)

---

## Steps

### 1) Configure VirtualBox Networking
- Verified both VMs are on the same network mode for testing.

**Screenshot:** `screenshots/01-virtualbox-network-settings.png`

### 2) Enable Disk Encryption (BitLocker)
- Enabled BitLocker on the Windows system drive to simulate encryption enforcement.

**Screenshot:** `screenshots/02-windows-bitlocker-on.png`

### 3) Apply Password + Lockout Policy
- Set minimum password length (12)
- Enabled complexity requirements
- Configured lockout threshold (5 attempts)

**Screenshot:** `screenshots/03-password-policy.png`

### 4) Enable Windows Firewall (All Profiles)
- Enabled Domain / Private / Public firewall profiles.

**Screenshot:** `screenshots/04-firewall-profiles-on.png`

### 5) Verify Microsoft Defender
- Confirmed real-time protection enabled.

**Screenshot:** `screenshots/05-defender-status.png`

### 6) Break/Fix Validation Test (Kali → Windows)
**Goal:** Show how disabling a control increases exposure, then re-enabling restores protection.

- Firewall OFF: Kali ping succeeded
- Firewall ON: Kali ping blocked (or ICMP inbound rule disabled to enforce block)

**Screenshots:**
- `screenshots/06-kali-ping-firewall-off.png`
- `screenshots/07-kali-ping-firewall-on.png`

### 7) Collect Evidence (Logging)
- Reviewed Windows Security logs in Event Viewer as proof of system activity and audit trail.

**Screenshot:** `screenshots/08-eventviewer-security-log.png`

---

## Compliance Checklist (MDM-Style)
| Control | Expected | Result |
|---|---|---|
| Disk Encryption | Enabled | ✅ |
| Password Policy | Enforced | ✅ |
| Account Lockout | Enabled | ✅ |
| Firewall Profiles | ON | ✅ |
| Antivirus/Defender | ON | ✅ |
| Logging Evidence | Captured | ✅ |

**Screenshot:** `screenshots/09-compliance-checklist.png`

---

## Key Takeaways
- Endpoint hardening controls (encryption, firewall, AV, strong authentication) reduce exposure and support compliance.
- Break/fix testing demonstrates how controls affect real-world attack surface.
- Logs provide evidence for auditing and incident investigation.

## Next Improvements
- Add a simple vulnerability scan baseline (local)
- Expand logs review (Defender history, firewall logs)
- Map controls to CIS benchmarks
