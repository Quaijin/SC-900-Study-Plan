# SC-900 — Domain 3: Capabilities of Microsoft Security Solutions

> **Exam Weight:** 35–40% &nbsp;|&nbsp; **Difficulty:** Intermediate–Advanced  
> **Official Study Guide:** [SC-900 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-900)  
> **Learning Path:** [Describe capabilities of Microsoft security solutions](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-security-solutions/)

---

> ⚠️ **Highest-weight domain on the exam (35–40%).** Prioritize this domain in your study time. Focus especially on distinguishing the three major pillars: Defender for Cloud, Microsoft Sentinel, and the Defender XDR suite.

---

## Table of Contents

1. [Azure DDoS Protection](#1-azure-ddos-protection)
2. [Azure Firewall](#2-azure-firewall)
3. [Web Application Firewall (WAF)](#3-web-application-firewall-waf)
4. [Network Security Groups (NSGs)](#4-network-security-groups-nsgs)
5. [Azure Bastion](#5-azure-bastion)
6. [Azure Key Vault](#6-azure-key-vault)
7. [Microsoft Defender for Cloud](#7-microsoft-defender-for-cloud)
8. [Microsoft Sentinel (SIEM + SOAR)](#8-microsoft-sentinel-siem--soar)
9. [Microsoft Defender XDR Suite](#9-microsoft-defender-xdr-suite)
10. [Microsoft Defender for Endpoint](#10-microsoft-defender-for-endpoint)
11. [Microsoft Defender for Office 365](#11-microsoft-defender-for-office-365)
12. [Microsoft Defender for Cloud Apps](#12-microsoft-defender-for-cloud-apps)
13. [Microsoft Defender for Identity](#13-microsoft-defender-for-identity)
14. [Microsoft Defender Vulnerability Management](#14-microsoft-defender-vulnerability-management)
15. [Microsoft Defender Portal](#15-microsoft-defender-portal)
16. [Exam Tips & Key Takeaways](#16-exam-tips--key-takeaways)

---

## 1. Azure DDoS Protection

A **Distributed Denial of Service (DDoS)** attack floods a resource with traffic to make it unavailable to legitimate users. Azure DDoS Protection defends against these attacks at scale.

### Service Tiers

| Tier | Cost | Coverage | Key Features |
|---|---|---|---|
| **DDoS Network Protection** (formerly Basic) | Free | All Azure services automatically | Always-on monitoring, basic volumetric attack mitigation |
| **DDoS Network Protection** (Standard/paid) | Paid per VNet | Resources in protected VNets | Adaptive tuning, real-time attack telemetry, attack analytics, DDoS Rapid Response team, SLA guarantee, cost protection |

### Types of DDoS Attacks Mitigated

| Attack Type | Description |
|---|---|
| **Volumetric** | Flood network bandwidth (e.g., UDP floods) |
| **Protocol** | Exploit weaknesses in Layer 3/4 protocols (e.g., SYN floods) |
| **Resource (Application)** | Target web application layer (Layer 7) — requires WAF for full protection |

> 💡 **DDoS Network Protection (paid)** includes adaptive tuning, which learns normal traffic patterns and adjusts mitigation policies automatically. It also includes a financial cost protection guarantee.

📖 **References:**
- [Azure DDoS Protection overview](https://learn.microsoft.com/en-us/azure/ddos-protection/ddos-protection-overview)
- [DDoS Protection pricing tiers](https://learn.microsoft.com/en-us/azure/ddos-protection/ddos-protection-sku-comparison)

---

## 2. Azure Firewall

**Azure Firewall** is a managed, cloud-native, stateful network security service that protects Azure Virtual Network resources. It is a fully managed Platform as a Service (PaaS) offering — no infrastructure to manage.

### Key Features

| Feature | Description |
|---|---|
| **Stateful inspection** | Tracks active connections; allows return traffic automatically |
| **Built-in high availability** | Scales automatically; no additional load balancers needed |
| **FQDN filtering** | Filter outbound traffic by domain name (e.g., allow *.microsoft.com) |
| **Network traffic filtering** | Allow/deny rules based on source IP, destination IP, port, and protocol |
| **Application rules** | FQDN-based filtering for HTTP/HTTPS traffic |
| **Threat intelligence** | Deny traffic from known malicious IP addresses and domains |
| **IDPS** | Intrusion Detection and Prevention System (Azure Firewall Premium) |
| **TLS inspection** | Inspect encrypted HTTPS traffic (Azure Firewall Premium) |

### Azure Firewall SKUs

| SKU | Best For |
|---|---|
| **Standard** | General network protection with FQDN filtering and threat intelligence |
| **Premium** | Highly sensitive environments requiring IDPS and TLS inspection |
| **Basic** | Small businesses needing essential firewall capabilities |

> ⚠️ **NSG vs Azure Firewall:** NSGs are simple allow/deny rules at the subnet/NIC level. Azure Firewall is a fully managed, stateful firewall with advanced features like FQDN filtering and threat intelligence. They are complementary, not mutually exclusive.

📖 **Reference:** [Azure Firewall overview](https://learn.microsoft.com/en-us/azure/firewall/overview)

---

## 3. Web Application Firewall (WAF)

**Web Application Firewall (WAF)** provides centralized protection for web applications from common exploits and vulnerabilities, particularly the **OWASP Top 10** (SQL injection, cross-site scripting, etc.).

### Where WAF Can Be Deployed

| Service | Use Case |
|---|---|
| **Azure Application Gateway** | WAF for web apps hosted in Azure (regional deployment) |
| **Azure Front Door** | WAF for globally distributed web apps and CDN traffic |
| **Azure CDN** | WAF for content delivery network endpoints |

### What WAF Protects Against (OWASP Top 10)

- SQL Injection
- Cross-Site Scripting (XSS)
- Broken authentication
- Sensitive data exposure
- XML External Entities (XXE)
- Security misconfigurations
- And more...

> 💡 **Key distinction:** Azure Firewall protects **network-level** traffic. WAF specifically protects **web applications** (HTTP/HTTPS) from application-layer attacks.

📖 **Reference:** [Azure Web Application Firewall overview](https://learn.microsoft.com/en-us/azure/web-application-firewall/overview)

---

## 4. Network Security Groups (NSGs)

**Network Security Groups (NSGs)** filter network traffic to and from Azure resources using **inbound and outbound security rules**.

### How NSGs Work

Each rule defines:
- **Source** — IP address, CIDR range, service tag, or application security group
- **Destination** — IP address, CIDR range, service tag, or application security group
- **Port** — Specific port or port range
- **Protocol** — TCP, UDP, or Any
- **Action** — Allow or Deny
- **Priority** — Lower number = higher priority (100–4096)

### Where NSGs Can Be Applied

| Level | Description |
|---|---|
| **Subnet** | Rules apply to all resources within the subnet |
| **Network Interface (NIC)** | Rules apply to a specific VM's network interface |

### NSG vs Azure Firewall Comparison

| | NSG | Azure Firewall |
|---|---|---|
| **Type** | Basic packet filter | Managed stateful firewall |
| **FQDN filtering** | ❌ No | ✅ Yes |
| **Threat intelligence** | ❌ No | ✅ Yes |
| **Cost** | Free | Paid |
| **Management** | Manual rules | Managed service |
| **Best for** | Simple subnet/NIC filtering | Advanced, centralized network protection |

📖 **Reference:** [Network security groups overview](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)

---

## 5. Azure Bastion

**Azure Bastion** provides secure, browser-based RDP and SSH access to Azure Virtual Machines **directly from the Azure portal**, without exposing VMs to the public internet.

### Key Benefits

| Benefit | Description |
|---|---|
| **No public IP required** | VMs do not need a public IP address for remote access |
| **No jump hosts needed** | Access is provided through Azure Bastion's PaaS infrastructure |
| **TLS encryption** | All sessions are encrypted over TLS |
| **NSG protection** | Azure Bastion is deployed in a dedicated subnet (AzureBastionSubnet) |
| **Hardened access** | Protects against port scanning since no RDP/SSH ports are open on the VM |

### How It Works

```
User (browser) → Azure Portal → Azure Bastion → Private IP of VM
                                (TLS/443)       (RDP/3389 or SSH/22)
```

> ⚠️ **Exam Note:** Azure Bastion does **NOT** require a public IP on the VM. Access is fully through the Azure portal using TLS on port 443.

📖 **Reference:** [Azure Bastion overview](https://learn.microsoft.com/en-us/azure/bastion/bastion-overview)

---

## 6. Azure Key Vault

**Azure Key Vault** is a cloud service for securely storing and controlling access to secrets, encryption keys, and certificates.

### What Azure Key Vault Stores

| Type | Examples |
|---|---|
| **Secrets** | Passwords, API keys, database connection strings, storage account keys |
| **Keys** | Cryptographic keys for data encryption (RSA, EC keys) |
| **Certificates** | SSL/TLS certificates (with auto-renewal support) |

### Key Features

| Feature | Description |
|---|---|
| **Centralized secret management** | Apps retrieve secrets via API — no hardcoded credentials |
| **Access control** | RBAC and Key Vault access policies control who can read/write |
| **Audit logging** | Every access is logged to Azure Monitor / Event Hub |
| **HSM-backed keys** | Keys can be protected by FIPS 140-2 Level 2 validated Hardware Security Modules |
| **Soft delete** | Deleted secrets/keys are recoverable for a configurable retention period |
| **Integration** | Native integration with Azure VMs, App Service, Azure Functions, AKS, and more |

📖 **Reference:** [Azure Key Vault overview](https://learn.microsoft.com/en-us/azure/key-vault/general/overview)

---

## 7. Microsoft Defender for Cloud

**Microsoft Defender for Cloud** is a **Cloud Security Posture Management (CSPM)** and **Cloud Workload Protection Platform (CWPP)** solution that identifies weaknesses in cloud configurations and protects workloads across Azure, AWS, and GCP.

### Two Core Pillars

| Pillar | Name | Cost | Purpose |
|---|---|---|---|
| **CSPM** | Cloud Security Posture Management | Free tier available | Continuously assess posture, provide Secure Score and recommendations |
| **CWPP** | Cloud Workload Protection Platform | Paid Defender plans | Advanced threat detection for specific workload types |

### Secure Score

The **Secure Score** is a single numeric value (percentage) that summarizes your current security posture. The higher the score, the lower your identified risk.

- Implement **security recommendations** to raise the score
- Recommendations are grouped into **security controls** (logical sets of related security checks)
- Each control has a maximum score contribution

### Security Recommendations & Policies

- **Security policies** define desired configuration standards for workloads
- Defender for Cloud continuously assesses resources against these policies
- Non-compliant resources generate **security recommendations** with remediation steps

### Defender Plans (CWPP Workload Protection)

| Defender Plan | Protects |
|---|---|
| Defender for Servers | Windows and Linux VMs |
| Defender for Containers | AKS clusters, container registries |
| Defender for Databases | SQL, Cosmos DB, PostgreSQL, MySQL |
| Defender for Storage | Azure Storage accounts |
| Defender for App Service | Azure App Service web apps |
| Defender for Key Vault | Azure Key Vault |
| Defender for APIs | Azure API Management APIs |

### Multi-Cloud Support

Defender for Cloud supports **Azure, AWS, and GCP** through native connectors, providing a unified security posture view across multi-cloud environments.

> ⚠️ **Exam Alert:** Defender for Cloud has a **free CSPM tier** (Secure Score + recommendations). CWPP (workload protection) requires **paid Defender plans**. This distinction is tested directly.

📖 **References:**
- [What is Microsoft Defender for Cloud?](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction)
- [Secure Score in Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/secure-score-security-controls)

---

## 8. Microsoft Sentinel (SIEM + SOAR)

**Microsoft Sentinel** is a cloud-native **Security Information and Event Management (SIEM)** and **Security Orchestration, Automation, and Response (SOAR)** solution built on Azure.

### SIEM vs SOAR

| | SIEM | SOAR |
|---|---|---|
| **Function** | Collect, aggregate, and analyze security data to detect threats | Automate and orchestrate security responses |
| **In Sentinel** | Log analytics, analytics rules, incidents | Playbooks (Logic Apps) |
| **Output** | Alerts and incidents | Automated actions (block IP, disable user, etc.) |

### The Four Core Capabilities

| Capability | Description | Key Components |
|---|---|---|
| **Collect** | Ingest data from across the organization at cloud scale | Data Connectors, Log Analytics workspace |
| **Detect** | Identify threats with built-in and custom analytics | Analytics Rules, Fusion (ML-based detection) |
| **Investigate** | Explore threats using AI and hunt for suspicious activity | Incident investigation, Hunting queries, Notebooks |
| **Respond** | Automate responses to detected threats | Playbooks (Logic Apps), Automation rules |

### Key Sentinel Components

| Component | Purpose |
|---|---|
| **Data Connectors** | Connect data sources — Microsoft services, AWS, GCP, and 300+ third-party solutions |
| **Log Analytics Workspace** | The underlying data store for all ingested logs |
| **Analytics Rules** | Detect threats and create incidents/alerts (built-in or custom KQL queries) |
| **Incidents** | Grouping of related alerts representing a potential attack |
| **Playbooks** | Azure Logic Apps workflows that automate responses to incidents |
| **Workbooks** | Interactive dashboards for visualizing and monitoring collected data |
| **Hunting Queries** | Proactive, manual threat-hunting queries using KQL |
| **Notebooks** | Jupyter notebooks for advanced hunting and threat investigation |
| **UEBA** | User and Entity Behavior Analytics — detects anomalous behavior using ML |
| **Threat Intelligence** | Import and correlate threat intelligence indicators (IoCs) |

### Common Data Sources

- Microsoft 365 Defender (Endpoint, Office 365, Identity, Cloud Apps)
- Microsoft Entra ID (sign-in logs, audit logs)
- Azure Activity and resource logs
- AWS CloudTrail / GCP Audit logs
- Third-party firewalls, SIEMs, and security solutions

> ⚠️ **Exam Alert:** Know what each component does. **Analytics Rules create incidents. Playbooks respond to incidents. Workbooks visualize data. Hunting queries are proactive (they do NOT automatically create alerts).** Sentinel is a SIEM — it is different from Defender for Cloud (CSPM) and Defender XDR (endpoint/email/identity protection).

📖 **References:**
- [What is Microsoft Sentinel?](https://learn.microsoft.com/en-us/azure/sentinel/overview)
- [Sentinel data connectors](https://learn.microsoft.com/en-us/azure/sentinel/connect-data-sources)
- [Automation with playbooks](https://learn.microsoft.com/en-us/azure/sentinel/automate-responses-with-playbooks)

---

## 9. Microsoft Defender XDR Suite

**Microsoft Defender XDR** (Extended Detection and Response) is an integrated threat protection suite that natively coordinates detection, prevention, investigation, and response across **endpoints, identity, email, and cloud applications**.

### What is XDR?

XDR breaks down security silos by:
- Correlating signals across multiple security domains (endpoints, email, identity, cloud apps)
- Providing a unified incident view and investigation experience
- Automating cross-domain response actions

### The Defender XDR Product Suite

| Product | Protects | Key Capability |
|---|---|---|
| **Defender for Endpoint** | Devices (Windows, macOS, Linux, iOS, Android) | EDR, threat & vulnerability management, attack surface reduction |
| **Defender for Office 365** | Email, SharePoint, OneDrive, Teams | Anti-phishing, Safe Links, Safe Attachments, BEC protection |
| **Defender for Cloud Apps** | Cloud applications (SaaS) | CASB — shadow IT discovery, data protection, threat detection |
| **Defender for Identity** | On-premises Active Directory | Detect lateral movement, privilege escalation, compromised accounts |
| **Defender Vulnerability Management** | Endpoints and software | Continuous vulnerability discovery, prioritization, and remediation |
| **Defender Threat Intelligence** | Security operations | Threat actor profiles, IoCs, TTP intelligence |

### Three Major Microsoft Security Pillars — Distinguished

| Solution | Type | Focus |
|---|---|---|
| **Defender XDR** | XDR | Endpoint, email, identity, cloud app threats |
| **Defender for Cloud** | CSPM + CWPP | Cloud infrastructure posture and workload threats |
| **Microsoft Sentinel** | SIEM + SOAR | Aggregate all signals, investigate, automate response |

> ⚠️ **Exam Alert:** These three are the most commonly confused products on the SC-900 exam. Memorize their definitions and scopes clearly.

📖 **Reference:** [Microsoft Defender XDR overview](https://learn.microsoft.com/en-us/microsoft-365/security/defender/microsoft-365-defender)

---

## 10. Microsoft Defender for Endpoint

**Microsoft Defender for Endpoint** is an enterprise endpoint security platform providing prevention, detection, investigation, and response across devices.

### Core Capabilities

| Capability | Description |
|---|---|
| **Threat & Vulnerability Management (TVM)** | Continuously discover and prioritize vulnerabilities and misconfigurations on devices |
| **Attack Surface Reduction (ASR)** | Rules that prevent common attack techniques (e.g., block Office macros, block process injection) |
| **Next-Generation Protection** | AI-powered antivirus and antimalware |
| **Endpoint Detection & Response (EDR)** | Detect advanced attacks; provides timeline of device activity for investigation |
| **Automated Investigation & Response (AIR)** | Automatically investigate alerts and take remediation actions |
| **Threat Hunting** | Proactively search for threats across device telemetry using KQL queries |
| **Microsoft Secure Score for Devices** | Measures device security posture |

### Supported Platforms

Windows, Windows Server, macOS, Linux, iOS, Android

📖 **Reference:** [Microsoft Defender for Endpoint overview](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

---

## 11. Microsoft Defender for Office 365

**Microsoft Defender for Office 365** protects organizations against malicious threats posed by email messages, links (URLs), and collaboration tools (SharePoint, OneDrive, Teams).

### Key Features

| Feature | Description |
|---|---|
| **Safe Attachments** | Detonates email attachments in a sandbox (virtual environment) before delivery to detect malware |
| **Safe Links** | Scans URLs in emails and Office documents at time-of-click for malicious content |
| **Anti-phishing** | ML-based detection of phishing attempts including spear-phishing and whaling |
| **Anti-spoofing** | Protects against email domain spoofing |
| **Business Email Compromise (BEC) Protection** | Detects impersonation of executives and trusted parties |
| **Attack Simulator** | Run simulated phishing campaigns to train users |

### Plans

| Plan | Included In |
|---|---|
| **Plan 1** | Microsoft 365 Business Premium, Microsoft 365 E3 |
| **Plan 2** | Microsoft 365 E5, Office 365 E5 (includes Attack Simulator, Threat Trackers, Explorer) |

> 💡 **Safe Attachments** opens attachments in a detonation chamber (sandbox) to detect zero-day malware **before** the email is delivered to the recipient's inbox.

📖 **Reference:** [Microsoft Defender for Office 365 overview](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/defender-for-office-365)

---

## 12. Microsoft Defender for Cloud Apps

**Microsoft Defender for Cloud Apps** is a **Cloud Access Security Broker (CASB)** that provides visibility and control over cloud app usage across your organization.

### What is a CASB?

A CASB sits between users and cloud services to enforce security policies and provide visibility into cloud app usage.

### Key Capabilities

| Capability | Description |
|---|---|
| **Shadow IT Discovery** | Identify all cloud apps being used — including unsanctioned apps employees use without IT approval |
| **App Sanctioning** | Mark apps as sanctioned (approved) or unsanctioned (blocked) |
| **Data Loss Prevention** | Apply DLP policies to data stored in cloud apps (Box, Salesforce, etc.) |
| **Threat Protection** | Detect anomalous user behavior and threats in cloud apps |
| **Compliance Assessment** | Assess app compliance with regulations (GDPR, HIPAA, etc.) |
| **Session Control** | Monitor and control user sessions in real time (requires Conditional Access App Control) |
| **Connected Apps** | Direct API connectors to popular apps (Microsoft 365, Salesforce, Box, Dropbox, etc.) |

> 💡 **Shadow IT** refers to cloud apps used by employees without IT knowledge or approval — a significant security risk. Defender for Cloud Apps can discover shadow IT from firewall and proxy logs.

📖 **Reference:** [What is Microsoft Defender for Cloud Apps?](https://learn.microsoft.com/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps)

---

## 13. Microsoft Defender for Identity

**Microsoft Defender for Identity** (formerly Azure Advanced Threat Protection / Azure ATP) uses **on-premises Active Directory signals** to detect, identify, and investigate advanced threats, compromised identities, and malicious insider actions.

### Key Detections

| Threat | Description |
|---|---|
| **Lateral movement** | Attackers moving from one system to another using stolen credentials |
| **Pass-the-hash / Pass-the-ticket** | Using stolen Kerberos tickets or NTLM hashes to authenticate |
| **Privilege escalation** | Gaining higher-level permissions than originally assigned |
| **Reconnaissance** | Enumeration of users, computers, and groups in Active Directory |
| **Compromised credentials** | Detecting credential theft via golden ticket attacks, DCSync, etc. |

### How It Works

1. **Sensors** installed on domain controllers capture AD traffic
2. Sensor data is sent to the Defender for Identity cloud service
3. ML and behavioral analytics detect suspicious activity
4. Alerts appear in the **Microsoft Defender portal**

> ⚠️ **Exam Note:** Defender for Identity protects **on-premises Active Directory** — not Entra ID. Entra ID Protection handles cloud identity risk. They are complementary but distinct.

📖 **Reference:** [What is Microsoft Defender for Identity?](https://learn.microsoft.com/en-us/defender-for-identity/what-is)

---

## 14. Microsoft Defender Vulnerability Management

**Microsoft Defender Vulnerability Management** (MDVM) provides continuous asset visibility, intelligent risk-based assessment, and built-in remediation tools.

### Core Capabilities

| Capability | Description |
|---|---|
| **Asset inventory** | Continuous discovery of all devices and software in the organization |
| **Vulnerability discovery** | Identify CVEs, security misconfigurations, and missing patches |
| **Risk-based prioritization** | Score vulnerabilities based on exploitability, business impact, and threat intelligence |
| **Remediation workflows** | Create remediation tickets directly integrated with IT ticketing systems |
| **Security recommendations** | Specific actionable steps to reduce risk |
| **Weaknesses view** | CVE-based view of vulnerabilities across the organization |

📖 **Reference:** [Microsoft Defender Vulnerability Management overview](https://learn.microsoft.com/en-us/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management)

---

## 15. Microsoft Defender Portal

The **Microsoft Defender portal** (security.microsoft.com) is the **unified security operations center** for the entire Defender XDR suite. It integrates all signals, incidents, and response capabilities in one place.

### What the Defender Portal Provides

| Feature | Description |
|---|---|
| **Unified incidents queue** | All alerts from all Defender products correlated into incidents |
| **Advanced Hunting** | KQL-based queries across all Defender XDR data |
| **Threat Analytics** | Reports on current threat campaigns and vulnerabilities |
| **Secure Score** | Microsoft Secure Score for identities, devices, and apps |
| **Action Center** | View and manage automated investigation and response actions |
| **Threat Intelligence** | Threat actor profiles and indicators of compromise (IoCs) |
| **Microsoft Sentinel integration** | Unified SecOps experience combining XDR and SIEM in one portal |

📖 **Reference:** [Microsoft Defender portal overview](https://learn.microsoft.com/en-us/microsoft-365/security/defender/microsoft-365-defender-portal)

---

## 16. Exam Tips & Key Takeaways

### 🎯 The Three Pillars — Know These Cold

| Product | Type | Protects |
|---|---|---|
| **Microsoft Sentinel** | SIEM + SOAR | Aggregate logs organization-wide; detect, investigate, respond via playbooks |
| **Defender for Cloud** | CSPM + CWPP | Cloud infrastructure posture (Azure/AWS/GCP) + workload threat protection |
| **Defender XDR** | XDR | Endpoints, email, identity (on-prem AD), cloud apps |

### 🎯 Network Security — Know the Differences

| Service | Purpose | Key Feature |
|---|---|---|
| **NSG** | Filter traffic at subnet/NIC level | Simple allow/deny rules (free) |
| **Azure Firewall** | Managed stateful network firewall | FQDN filtering, threat intelligence |
| **WAF** | Protect web apps from OWASP Top 10 | SQL injection, XSS protection |
| **Azure Bastion** | Secure RDP/SSH without public IP | Browser-based via Azure portal |
| **DDoS Protection** | Defend against volumetric attacks | Free basic tier; paid for advanced |

### 🎯 Sentinel Component Functions

| Component | Does What |
|---|---|
| Data Connectors | Bring logs IN to Sentinel |
| Analytics Rules | Detect threats, CREATE incidents |
| Playbooks | Automated RESPONSE to incidents |
| Workbooks | VISUALIZE data |
| Hunting Queries | PROACTIVE manual threat search |
| Incidents | Grouped alerts representing a potential attack |

### ⚡ Common Exam Traps

- **Defender for Cloud ≠ Defender XDR ≠ Microsoft Sentinel** — all three are different products
- **Defender for Identity** = on-premises AD protection; **Entra ID Protection** = cloud identity risk
- **Safe Attachments** uses a **sandbox/detonation chamber** before email delivery
- **Shadow IT** is discovered by **Defender for Cloud Apps (CASB)**
- **DDoS Network Protection (free)** is always on for all Azure services — the paid tier adds SLA and telemetry
- Azure Bastion requires **no public IP** on the VM — this is tested directly
- **Hunting queries** in Sentinel are proactive — they do **NOT** automatically create alerts

---

## 📚 Official Microsoft Learn Resources

| Resource | Link |
|---|---|
| Learning Path: Describe capabilities of Microsoft security solutions | [Open](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-security-solutions/) |
| Module: Describe basic security capabilities in Azure | [Open](https://learn.microsoft.com/en-us/training/modules/describe-basic-security-capabilities-azure/) |
| Module: Describe security management capabilities of Azure | [Open](https://learn.microsoft.com/en-us/training/modules/describe-security-management-capabilities-of-azure/) |
| Module: Describe security capabilities of Microsoft Sentinel | [Open](https://learn.microsoft.com/en-us/training/modules/describe-security-capabilities-of-azure-sentinel/) |
| Module: Describe threat protection with Microsoft Defender XDR | [Open](https://learn.microsoft.com/en-us/training/modules/describe-threat-protection-with-microsoft-365-defender/) |
| Azure DDoS Protection docs | [Open](https://learn.microsoft.com/en-us/azure/ddos-protection/ddos-protection-overview) |
| Azure Firewall docs | [Open](https://learn.microsoft.com/en-us/azure/firewall/overview) |
| Microsoft Sentinel docs | [Open](https://learn.microsoft.com/en-us/azure/sentinel/overview) |
| Defender for Cloud docs | [Open](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction) |
| Defender XDR docs | [Open](https://learn.microsoft.com/en-us/microsoft-365/security/defender/microsoft-365-defender) |
| Defender for Endpoint docs | [Open](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) |
| Defender for Office 365 docs | [Open](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/defender-for-office-365) |
| Defender for Cloud Apps docs | [Open](https://learn.microsoft.com/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps) |
| Defender for Identity docs | [Open](https://learn.microsoft.com/en-us/defender-for-identity/what-is) |
| SC-900 Certification Page | [Open](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/) |
| Free Practice Assessment | [Open](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/practice/assessment?assessment-type=practice&assessmentId=11) |

---

*Last updated: May 2026 · Aligned with SC-900 exam objectives (November 2025 update)*
