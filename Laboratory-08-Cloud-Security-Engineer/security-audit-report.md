# Security Audit Report






## Core Security Concepts

### 1. The Principle of Least Privilege (PoLP)

The Principle of Least Privilege states that every user, service, or process should be granted only the minimum level of access necessary to perform its intended function  nothing more. In cloud environments, this matters because a compromised account with excessive permissions can become a launching pad for lateral movement, data exfiltration, and privilege escalation. By scoping permissions tightly, the "blast radius" of any breach is dramatically reduced.

**Why it matters for cloud user accounts:** Cloud IAM roles are powerful a single over-privileged account  can expose an entire organization's infrastructure. PoLP limits the damage.

---

### 2. Attack Surface

The attack surface of a virtual machine is the total sum of all points where an unauthorized user could attempt to enter, extract data from, or disrupt the system  this includes open network ports, running services, user accounts, enabled APIs, and even installed software versions. Every additional exposed port or service increases the number of potential vulnerabilities an attacker can probe. Reducing the attack surface means disabling or blocking anything that isn't strictly required.

**Applied to a VM:** An Ubuntu server with SSH, HTTP, a database, and a monitoring agent all exposed has a much larger attack surface than the same server exposing only SSH and HTTP behind a firewall.

---

### 3. Default Deny Policy

A Default Deny policy is a firewall philosophy where **all** traffic is blocked by default, and only explicitly whitelisted traffic is permitted. This is fundamentally safer than trying to block known attackers one by one, because it operates on the assumption that *anything not explicitly allowed is a threat*. Attackers constantly change IPs, use botnets, and scan random ports — you cannot enumerate them. Default Deny inverts the problem: instead of chasing bad traffic, you only open doors you intentionally need (SSH, 8080) and keep everything else shut.

**Why safer than blocking specific hackers:** You can't keep an up-to-date blacklist of every malicious actor or new automated scanner. An allowlist model means unknown/zero-day traffic is denied automatically.

---

## Security Audit Baseline (Pre-Firewall)

Before enabling UFW, the server exposes:

| Port | Service | Status |
|------|---------|--------|
| 22   | SSH     | OPEN (required) |
| 8080 | Nginx web app | OPEN (required) |
| *    | Everything else | OPEN (vulnerable) |

**Action taken:** Apply Default Deny via UFW, then explicitly allow 22 and 8080.
