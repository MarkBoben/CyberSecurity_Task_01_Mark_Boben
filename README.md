# Cyber Security Task 01 — Personal Security Audit & Cyber Awareness Assessment

**Intern:** Mark
**Organization:** White Band Associates
**Program:** IT Internship 2026
**Environment:** Kali GNU/Linux Rolling 2026.2 (Kernel 6.19.14+kali-amd64)

The purpose of this task is to understand basic cyber security concepts by assessing personal digital security practices and identifying potential risks. Cyber security starts with securing yourself before securing systems and networks.

## Table of Contents

- [Part A — Device Security Assessment](#part-a--device-security-assessment)
- [Part B — Password Security Review](#part-b--password-security-review)
- [Part C — Online Account Security Check](#part-c--online-account-security-check)
- [Part D — Cyber Threat Research](#part-d--cyber-threat-research)
- [Part E — Cyber Security Awareness Poster](#part-e--cyber-security-awareness-poster)
- [Part F — Security Reflection](#part-f--security-reflection)
- [Key Takeaways](#key-takeaways)

---

## Part A — Device Security Assessment

Full assessment: [`DEVICE_SECURITY_ASSESSMENT.txt`](./DEVICE_SECURITY_ASSESSMENT.txt)

**System Information**

| Property | Value |
|---|---|
| Operating System | Kali GNU/Linux Rolling |
| OS Version | 2026.2 |
| Kernel Version | Linux 6.19.14+kali-amd64 |
| Architecture | x86_64 |

**Security Checks**

| Check | Status | Evidence |
|---|:---:|---|
| System fully updated | ❌ No | `apt list --upgradable` showed 67 packages pending |
| Antivirus installed | ✅ Yes | `dpkg -l \| grep clamav` confirmed ClamAV, ClamAV-Base, ClamAV-Freshclam |
| Firewall enabled | ✅ Yes | `sudo iptables -L` showed active INPUT, FORWARD, OUTPUT chains |

**Summary:** The system has ClamAV antivirus active for malware detection and an iptables-based firewall providing network traffic filtering. However, 67 packages are pending upgrade, meaning the system is not fully patched against known vulnerabilities. Applying these updates is the immediate next step to close this gap.

**Commands Used**

```bash
hostnamectl
cat /etc/os-release
sudo apt update
apt list --upgradable
dpkg -l | grep clamav
sudo iptables -L
```

---

## Part B — Password Security Review

Full policy document: [`PASSWORD_POLICY.txt`](./PASSWORD_POLICY.txt)

A strong password is long, unique, and difficult to guess, combining uppercase letters, lowercase letters, numbers, and special characters. Unique passwords per account prevent a single breach from compromising multiple services — reusing passwords exposes users to **credential stuffing**, where attackers replay stolen credentials across other sites.

**Policy Summary**

| # | Rule |
|---|------|
| 1 | Minimum 12 characters |
| 2 | Mix of uppercase and lowercase letters |
| 3 | Include numbers and special characters |
| 4 | No personal information (names, birthdays, phone numbers) |
| 5 | Unique password per account |
| 6 | Enable Multi-Factor Authentication wherever possible |
| 7 | Change passwords immediately if a breach is suspected |
| 8 | Store passwords securely using a password manager |
| 9 | Never share passwords with others |
| 10 | Regularly review and update important account passwords |

**Multi-Factor Authentication (MFA):** a security method requiring two or more verification factors (e.g. password + mobile authentication code or biometric verification) before granting account access.

---

## Part C — Online Account Security Check

Full review: [`ACCOUNT_SECURITY_REVIEW.txt`](./ACCOUNT_SECURITY_REVIEW.txt)

Three personal accounts were audited for MFA status, password strength, and recovery configuration.

| Account | MFA Enabled | Strong Password | Recovery Configured |
|---|:---:|:---:|:---:|
| Google | ✅ Yes | ✅ Yes | ✅ Yes |
| LinkedIn | ❌ No | ✅ Yes | ✅ Yes |
| GitHub | ❌ No | ✅ Yes | ✅ Yes |

**Analysis:** Google has the strongest security configuration of the three, since MFA (2-Step Verification) is enabled alongside a configured recovery method. LinkedIn and GitHub both use strong passwords and have recovery methods set up, but neither has MFA enabled — leaving both accounts vulnerable to unauthorized access if the password alone is ever compromised.

**Recommended action:** Enable MFA on LinkedIn and GitHub to bring all three accounts to the same security baseline.

*No actual passwords are shared anywhere in this review.*

---

## Part D — Cyber Threat Research

Full research: [`THREAT_RESEARCH.txt`](./THREAT_RESEARCH.txt) · [`CYBER_THREAT_RESEARCH.txt`](./CYBER_THREAT_RESEARCH.txt)

Five major cyber threat categories were researched, each with a definition, a real-world example, and prevention methods.

### 1. Phishing
Attackers impersonate trusted organizations or individuals to trick users into revealing sensitive information such as usernames, passwords, or banking details.
**Example:** Fake emails pretending to be from Google or banks, asking users to "verify" their account via a malicious link.
**Prevention:** Verify the sender, avoid suspicious links, check URLs carefully, enable MFA, use spam filters and antivirus software.

### 2. Malware
Software intentionally designed to damage, disrupt, steal data from, or gain unauthorized access to computer systems.
**Example:** The ILOVEYOU malware infected millions of computers worldwide by spreading through email attachments.
**Prevention:** Install and update antivirus software, download only from trusted sources, keep the OS updated, avoid suspicious attachments, run regular scans.

### 3. Ransomware
Malware that encrypts files or locks systems, demanding payment to restore access.
**Example:** The WannaCry ransomware attack (2017) affected hospitals, businesses, and government organizations in over 150 countries.
**Prevention:** Regular backups, keep systems updated, avoid suspicious attachments, use endpoint protection, enable MFA.

### 4. Social Engineering
Psychological manipulation of people into revealing confidential information or performing actions that compromise security.
**Example:** An attacker impersonates an IT support technician to convince a victim to disclose login credentials.
**Prevention:** Verify identities before sharing information, be cautious of urgent requests, follow organizational security policy, participate in awareness training.

### 5. Data Breach
Unauthorized access, disclosure, or theft of sensitive or protected information.
**Example:** The Equifax data breach exposed personal information of approximately 147 million individuals due to an unpatched vulnerability.
**Prevention:** Strong unique passwords, MFA, encryption of sensitive data, regular security updates, account activity monitoring.

**Conclusion:** Cyber threats continue to evolve and pose serious risks to individuals and organizations alike. Recognizing these threat categories and applying consistent prevention practices — updated systems, strong authentication, and cautious digital habits — significantly reduces the risk of becoming a victim.

---

## Part E — Cyber Security Awareness Poster

**Topic chosen:** Strong Passwords
**Tool used:** Canva (AI design generation)

A public-facing cyber security awareness poster was designed to reinforce password best practices for a general audience, intended for display at a corporate training workshop.

![Strong Passwords Matter awareness poster](./AWARENESS%20POSTER.png)

The poster covers the workshop title, date, venue, and RSVP details, using a dark tech-themed design with a circuit-pattern padlock graphic to visually reinforce the security theme.

---

## Part F — Security Reflection

Full report: [`REFLECTION_REPORT.txt`](./REFLECTION_REPORT.txt)

This audit surfaced several gaps in personal digital hygiene: while strong passwords were already in place across most accounts, MFA was not enabled everywhere, and the primary working OS had a backlog of pending updates — both of which leave room for exploitation even when other defenses are solid.

**Immediate action items identified:**
- Enable MFA on all important accounts, including GitHub and LinkedIn
- Keep the OS and applications updated regularly
- Stay cautious when opening emails, clicking links, or downloading files from unknown sources
- Use unique passwords per account, stored securely in a password manager

Cyber security is foundational to how people communicate, bank, learn, and work today. A single security incident can lead to financial loss, privacy violations, and lasting damage to personal or organizational data — making consistent cyber hygiene a practical necessity, not an optional extra.

---

## Key Takeaways

- A strong password policy alone isn't sufficient — MFA closes the gap that password strength can't cover on its own.
- Account security reviews quickly surface inconsistent protection across services, even when password hygiene is otherwise good.
- Device hardening is an ongoing process: antivirus and firewall protection mean little if the system itself is running outdated, vulnerable packages.
- The same five threat categories (phishing, malware, ransomware, social engineering, data breaches) recur across most real-world incidents, reinforcing the value of recognizing patterns rather than memorizing isolated cases.
- Awareness materials like the Part E poster translate technical findings into a format non-technical audiences can act on.
