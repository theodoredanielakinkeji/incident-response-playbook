# 🚨 Incident Response Playbook

> A structured playbook for identifying, containing, and recovering from common cybersecurity incidents.
> Based on industry best practices and hands-on experience as a Junior Cybersecurity Analyst.

---

## 📌 What is an Incident Response Playbook?

An Incident Response (IR) Playbook is a documented set of procedures that guides a security team through detecting, containing, and recovering from a cyberattack or security breach. Having a playbook ensures fast, consistent, and effective responses.

---

## 🔄 Incident Response Lifecycle

```
1. PREPARATION → 2. IDENTIFICATION → 3. CONTAINMENT
                                            ↓
6. LESSONS LEARNED ← 5. RECOVERY ← 4. ERADICATION
```

---

## 📖 Playbook 1: Phishing Attack

### 🔍 Detection Signals
- User reports suspicious email
- Email contains unusual links, attachments, or requests for credentials
- Email security gateway flags the message

### 🛑 Containment Steps
1. Instruct the user **not to click** any links or download attachments
2. Isolate the affected workstation from the network immediately
3. Block the sender's email address at the mail gateway
4. Preserve the email as evidence (forward to security team)

### 🧹 Eradication Steps
1. Scan the workstation with updated antivirus/antimalware
2. Check for any credentials that may have been entered on phishing sites
3. Reset compromised passwords immediately
4. Remove any malicious emails from all inboxes organisation-wide

### 🔁 Recovery Steps
1. Reconnect workstation after confirming it is clean
2. Monitor user account for unusual activity for 72 hours
3. Notify affected users and management

### 📋 Post-Incident
- Document the incident timeline
- Conduct staff awareness training reminder
- Update email filtering rules

---

## 📖 Playbook 2: Brute Force Attack

### 🔍 Detection Signals
- Multiple failed login attempts in a short period
- Account lockouts triggered repeatedly
- IDS/SIEM alerts on unusual authentication traffic

### 🛑 Containment Steps
1. Lock the targeted account immediately
2. Block the attacking IP address at the firewall
3. Alert the account owner
4. Preserve firewall and authentication logs as evidence

### 🧹 Eradication Steps
1. Identify all accounts targeted in the attack
2. Force password resets on all affected accounts
3. Enable Multi-Factor Authentication (MFA) on targeted accounts
4. Review firewall rules and tighten access controls

### 🔁 Recovery Steps
1. Restore account access after password reset and MFA setup
2. Monitor accounts for 48–72 hours post-incident
3. Review and update login attempt thresholds

### 📋 Post-Incident
- Document attacker IP, time, and accounts targeted
- Review password policy — enforce stronger requirements
- Consider implementing CAPTCHA or account lockout policies

---

## 📖 Playbook 3: Malware Infection

### 🔍 Detection Signals
- Antivirus alert triggered on a workstation
- Unusual system behaviour (slow performance, unexpected pop-ups)
- Unusual outbound network traffic detected
- Files being encrypted or deleted unexpectedly

### 🛑 Containment Steps
1. **Immediately isolate** the infected machine from the network (unplug LAN / disable Wi-Fi)
2. Do NOT shut down the machine (preserve volatile memory evidence)
3. Alert the security team and management
4. Identify the malware type using antivirus or VirusTotal

### 🧹 Eradication Steps
1. Run a full antivirus/antimalware scan
2. Manually remove identified malicious files and registry entries
3. Check for persistence mechanisms (startup entries, scheduled tasks)
4. If uncleanable — wipe and reimage the machine

### 🔁 Recovery Steps
1. Restore data from last known clean backup
2. Reconnect machine to network only after full clearance
3. Patch the vulnerability that allowed the infection
4. Monitor network traffic from recovered machine for 1 week

### 📋 Post-Incident
- Identify the infection vector (email, USB, download)
- Block the malware hash/signature at the gateway
- Update antivirus definitions across all endpoints
- Brief staff on the infection method

---

## 📊 Severity Classification

| Level | Description | Response Time |
|-------|-------------|--------------|
| 🔴 Critical | Active breach, data exfiltration, ransomware | Immediate — within 15 mins |
| 🟠 High | Confirmed malware, brute force success | Within 1 hour |
| 🟡 Medium | Phishing attempt, suspicious activity | Within 4 hours |
| 🟢 Low | Policy violation, minor anomaly | Within 24 hours |

---

## 📁 Incident Log Template

Incident ID     : IR-2024-09-15-001
Date/Time       : 15 September 2024, 10:32 AM
Reported By     : IT Security Team
Incident Type   : Phishing
Affected System : Staff email accounts (3 users)
Severity Level  : Medium
Actions Taken   : Isolated affected accounts, blocked sender domain,
                  reset passwords, scanned workstations, notified staff
Resolved By     : Daniel Theodore Akinkeji
Resolution Date : 15 September 2024, 2:45 PM
Notes           : Staff were reminded of email security best practices.
                  Email filtering rules updated to block similar attempts.

---

*Prepared by: Daniel Theodore Akinkeji | Cybersecurity Analyst*
