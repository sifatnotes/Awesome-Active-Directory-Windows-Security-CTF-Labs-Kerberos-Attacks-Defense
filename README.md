# Awesome-Active-Directory-Windows-Security-CTF-Labs-Kerberos-Attacks-Defense
A curated index of hands-on Active Directory attacks, Kerberos abuse, Windows privilege escalation, and lateral movement labs from Learn SecByte for pentesters and red/blue teams.
# Active Directory & Windows Security CTF Labs Collection

A structured, searchable index of hands-on cybersecurity labs focusing on Active Directory (AD) attacks, Kerberos ticket forgery, Windows credential dumping, lateral movement, and local privilege escalation hosted on Learn SecByte.

This resource is tailored for cybersecurity students, CTF participants, penetration testers, red teamers, and SOC analysts practicing enterprise Windows environment attack and defense methodologies.

---

## Table of Contents
- [Introduction](#introduction)
- [Lab Collection & Index](#lab-collection--index)
- [Categories](#categories)
  - [Active Directory & Kerberos Security](#active-directory--kerberos-security)
  - [Authentication Abuse & Lateral Movement](#authentication-abuse--lateral-movement)
  - [Windows Host Security & Privilege Escalation](#windows-host-security--privilege-escalation)
- [Learning Path](#learning-path)
- [How to Use the Labs](#how-to-use-the-labs)
- [Disclaimer](#disclaimer)

---

## Introduction

Active Directory forms the backbone of enterprise identity and access management in modern IT environments. Understanding how attackers compromise domain credentials, forge authentication tickets, relay hashes, and abuse Kerberos delegation is essential for modern offensive and defensive security professionals.

This repository catalogs hands-on cybersecurity labs from Learn SecByte into clear, organized domain paths covering enterprise identity security and host-based exploitation.

---

## Lab Collection & Index

| Lab Title | Target Focus | Primary Category | Access Link |
| :--- | :--- | :--- | :--- |
| **Unquoted Service Paths** | Windows Host | Privilege Escalation | [Access Lab](https://learn.secbyte.org/ctf/unquoted-service-paths) |
| **DLL Hijacking** | Windows Host | Post-Exploitation & Defense | [Access Lab](https://learn.secbyte.org/ctf/dll-hijacking-from-discovery-to-defense) |
| **DCSync Attack** | Active Directory | Directory Replication Abuse | [Access Lab](https://learn.secbyte.org/ctf/dcsync-attack-directory-replication-abuse) |
| **Shadow Credentials** | Active Directory | Key Trust / PKINIT | [Access Lab](https://learn.secbyte.org/ctf/shadow-credentials-key-trust-active-directory) |
| **Delegation Abuse** | Active Directory | Kerberos Delegation | [Access Lab](https://learn.secbyte.org/ctf/delegation-abuse-from-kerberos-theory-to-domain-takeover) |
| **Silver Ticket Attack** | Kerberos | Ticket Forgery & Detection | [Access Lab](https://learn.secbyte.org/ctf/silver-ticket-kerberos-forgery-detection) |
| **Golden Ticket Attack** | Kerberos | Domain Takeover & Persistence | [Access Lab](https://learn.secbyte.org/ctf/golden-ticket-ad-kerberos-forgery-detection) |
| **Pass-the-Ticket (PtT)** | Kerberos | Ticket Reuse & Abuse | [Access Lab](https://learn.secbyte.org/ctf/pass-the-ticket-kerberos-ticket-abuse-and-defense) |
| **Pass-the-Hash (PtH)** | Windows Auth | Credential Reuse & Defense | [Access Lab](https://learn.secbyte.org/ctf/pass-the-hash-windows-authentication-abuse-and-defense) |
| **NTLM Relay Attacks** | Network Auth | Relay & MitM Defense | [Access Lab](https://learn.secbyte.org/ctf/ntlm-relay-from-theory-to-detection-and-defense) |
| **LLMNR/NBT-NS Poisoning** | Network Auth | Name Resolution Poisoning | [Access Lab](https://learn.secbyte.org/ctf/llmnr-poisoning-name-resolution-to-credential-capture) |
| **Passwords in SYSVOL** | Active Directory | Domain Enumeration | [Access Lab](https://learn.secbyte.org/ctf/password-in-sysvol) |

---

## Categories

### Active Directory & Kerberos Security
Hands-on labs detailing Kerberos architecture, ticket forgery, domain dominance, and Active Directory object manipulation:

* **Passwords in SYSVOL:** Enumerating legacy Group Policy Preferences (GPP) for embedded domain credentials.
  * Lab Link: https://learn.secbyte.org/ctf/password-in-sysvol
* **DCSync Attacks:** Simulating Directory Replication Service (DRS) Remote Protocol calls to extract NT hashes without running code on a Domain Controller.
  * Lab Link: https://learn.secbyte.org/ctf/dcsync-attack-directory-replication-abuse
* **Shadow Credentials:** Modifying the `msDS-KeyCredentialLink` attribute to configure public key authentication (PKINIT) for account takeover.
  * Lab Link: https://learn.secbyte.org/ctf/shadow-credentials-key-trust-active-directory
* **Kerberos Delegation Abuse:** Exploiting Unconstrained, Constrained, and Resource-Based Constrained Delegation (RBCD) for domain dominance.
  * Lab Link: https://learn.secbyte.org/ctf/delegation-abuse-from-kerberos-theory-to-domain-takeover
* **Silver Ticket Forgery:** Crafting service tickets using compromised service account password hashes.
  * Lab Link: https://learn.secbyte.org/ctf/silver-ticket-kerberos-forgery-detection
* **Golden Ticket Forgery:** abusing the KRBTGT account hash to generate valid TGTs for domain persistence.
  * Lab Link: https://learn.secbyte.org/ctf/golden-ticket-ad-kerberos-forgery-detection

### Authentication Abuse & Lateral Movement
Labs focusing on legacy network protocols, ticket injection, hash reuse, and man-in-the-middle credential harvesting:

* **LLMNR/NBT-NS Poisoning:** Capturing NetNTLM hashes by spoofing broadcast name resolution requests on local networks.
  * Lab Link: https://learn.secbyte.org/ctf/llmnr-poisoning-name-resolution-to-credential-capture
* **NTLM Relay Attacks:** Relaying captured NTLM authentication to unauthenticated target machines with SMB/HTTP signing disabled.
  * Lab Link: https://learn.secbyte.org/ctf/ntlm-relay-from-theory-to-detection-and-defense
* **Pass-the-Hash (PtH):** Authenticating to remote Windows systems using stolen NTLM hashes.
  * Lab Link: https://learn.secbyte.org/ctf/pass-the-hash-windows-authentication-abuse-and-defense
* **Pass-the-Ticket (PtT):** Extracting and injecting Kerberos tickets (TGT/TGS) into session memory for lateral movement.
  * Lab Link: https://learn.secbyte.org/ctf/pass-the-ticket-kerberos-ticket-abuse-and-defense

### Windows Host Security & Privilege Escalation
Local privilege escalation and post-exploitation mechanisms on individual Windows endpoints:

* **Unquoted Service Paths:** Exploiting unquoted space binary paths in Windows services to gain elevated privileges.
  * Lab Link: https://learn.secbyte.org/ctf/unquoted-service-paths
* **DLL Hijacking:** Analyzing DLL search order vulnerability mechanics from identification to defense.
  * Lab Link: https://learn.secbyte.org/ctf/dll-hijacking-from-discovery-to-defense

---

## Learning Path

Follow this structured roadmap to build domain security expertise:

1. **Host Misconfigurations & Local Escalation**
   - Identify unquoted service paths and vulnerable DLL loading logic.
2. **Network Reconnaissance & Initial Credential Capture**
   - Harvest local credentials via LLMNR poisoning and GPP SYSVOL searching.
   - Perform NTLM relay attacks across domain networks.
3. **Lateral Movement & Credential Reuse**
   - Practice Pass-the-Hash and Pass-the-Ticket techniques across workstations and servers.
4. **Active Directory Domain Takeover & Persistence**
   - Execute DCSync attacks, Shadow Credentials abuse, and Kerberos Delegation exploitation.
   - Maintain persistence via Golden and Silver Ticket generation.

---

## How to Use the Labs

1. Select any target topic from the index table or categories above.
2. Access the practice environment on Learn SecByte using the direct link.
3. Work through the hands-on tasks to perform enumeration, credential dumping, ticket manipulation, and defense verification.
4. Review recommended security baselines and mitigation steps provided in each lab.

---

## Disclaimer

This repository is strictly intended for authorized security research, educational purposes, and defensive hardening. All concepts and lab materials are designed to help cybersecurity practitioners analyze domain threats and harden Windows environments. Unauthorized testing against infrastructure without prior written authorization is illegal.
