# SC-900 — Domain 4: Capabilities of Microsoft Compliance Solutions

> **Exam Weight:** 20–25% &nbsp;|&nbsp; **Difficulty:** Intermediate–Advanced  
> **Official Study Guide:** [SC-900 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-900)  
> **Learning Path:** [Describe capabilities of Microsoft compliance solutions](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-compliance-solutions/)

---

## Table of Contents

1. [Microsoft Service Trust Portal](#1-microsoft-service-trust-portal)
2. [Microsoft Privacy Principles](#2-microsoft-privacy-principles)
3. [Microsoft Priva](#3-microsoft-priva)
4. [Microsoft Purview Portal](#4-microsoft-purview-portal)
5. [Microsoft Purview Compliance Manager](#5-microsoft-purview-compliance-manager)
6. [Data Classification](#6-data-classification)
7. [Sensitivity Labels](#7-sensitivity-labels)
8. [Data Loss Prevention (DLP)](#8-data-loss-prevention-dlp)
9. [Retention Policies & Retention Labels](#9-retention-policies--retention-labels)
10. [Records Management](#10-records-management)
11. [Insider Risk Management](#11-insider-risk-management)
12. [Communication Compliance](#12-communication-compliance)
13. [eDiscovery](#13-ediscovery)
14. [Microsoft Purview Audit](#14-microsoft-purview-audit)
15. [Exam Tips & Key Takeaways](#15-exam-tips--key-takeaways)

---

## 1. Microsoft Service Trust Portal

The **Microsoft Service Trust Portal (STP)** is the public-facing hub where Microsoft publishes audit reports, compliance documentation, and trust information about its cloud services.

**URL:** [servicetrust.microsoft.com](https://servicetrust.microsoft.com)

### What You'll Find on the STP

| Section | Contents |
|---|---|
| **Certifications, Regulations & Standards** | ISO 27001, SOC 1/2/3, FedRAMP, GDPR, HIPAA/HITECH reports |
| **Reports & Documents** | Third-party audit reports, data protection white papers, penetration test results |
| **Industry & Regional** | Compliance resources tailored by industry (financial, healthcare) and region |
| **My Library** | Save and bookmark documents for quick access |
| **Data Protection Resources** | FAQs, data protection overviews, Microsoft Privacy Statement |

### Who Uses the STP?

- **IT Administrators** — assessing cloud risk and compliance posture
- **Compliance Officers** — verifying regulatory adherence for audits
- **Legal teams** — reviewing Microsoft's contractual commitments
- **Auditors** — accessing third-party audit evidence

> 💡 The STP is a **read-only, publicly accessible** resource (some documents require a Microsoft account). It does not manage your organization's compliance — that is Compliance Manager's role.

📖 **Reference:** [Get started with the Microsoft Service Trust Portal](https://learn.microsoft.com/en-us/microsoft-365/compliance/get-started-with-service-trust-portal)

---

## 2. Microsoft Privacy Principles

Microsoft's six core privacy principles govern how Microsoft collects, uses, and protects customer data across all its products and services.

| Principle | Description |
|---|---|
| **Control** | Customers are in control of their own data and privacy choices |
| **Transparency** | Microsoft is transparent about what data it collects and how it uses it |
| **Security** | Customer data is protected using strong security and encryption |
| **Strong Legal Protections** | Microsoft respects local privacy laws and fights for legal protections for customers |
| **No Content-Based Targeting** | Microsoft does not use customer email, files, or chats to target advertising |
| **Benefits to You** | Any data Microsoft collects is used to benefit the customer, not for unrelated purposes |

> ⚠️ **Exam Note:** The **"No Content-Based Targeting"** principle is the one that specifically prohibits using email or document content for advertising — this is commonly tested.

📖 **Reference:** [Microsoft Privacy Principles](https://learn.microsoft.com/en-us/training/modules/describe-compliance-management-capabilities-microsoft/2-describe-microsoft-privacy-principles)

---

## 3. Microsoft Priva

**Microsoft Priva** helps organizations proactively identify and manage privacy risks, and handle data subject rights requests efficiently.

### Two Core Modules

| Module | Purpose |
|---|---|
| **Privacy Risk Management** | Proactively identify and manage privacy risks such as data overexposure, data transfers, and data minimization issues. Uses policies and alerts. |
| **Subject Rights Requests** | Streamline the process of handling GDPR/CCPA data subject rights requests (right to access, right to erasure, right to portability) |

### Privacy Risk Management — Risk Types Detected

| Risk | Description |
|---|---|
| **Data overexposure** | Personal data accessible to more people than necessary |
| **Data transfers** | Personal data being moved to locations that may have lower privacy standards |
| **Data minimization** | Personal data retained longer than needed |

> 💡 Microsoft Priva is distinct from Microsoft Purview compliance tools. Priva focuses specifically on **privacy** (personal data and data subject rights), while Purview focuses on broader compliance, information protection, and governance.

📖 **Reference:** [Learn about Microsoft Priva](https://learn.microsoft.com/en-us/privacy/priva/priva-overview)

---

## 4. Microsoft Purview Portal

The **Microsoft Purview portal** (purview.microsoft.com) is the unified compliance and data governance hub that consolidates all Microsoft Purview compliance and governance solutions.

> It replaces the older **Microsoft 365 Compliance Center** (compliance.microsoft.com).

### Solutions Available in the Purview Portal

| Category | Solutions |
|---|---|
| **Information Protection** | Sensitivity labels, DLP, information barriers |
| **Information Governance** | Retention policies, retention labels, records management |
| **Insider Risk** | Insider Risk Management, Communication Compliance |
| **eDiscovery & Legal** | Content Search, eDiscovery Standard, eDiscovery Premium |
| **Audit & Compliance** | Audit (Standard), Audit (Premium), Compliance Manager |
| **Data Catalog** | Data Map, Data Catalog (governance for data assets) |

📖 **Reference:** [Microsoft Purview portal overview](https://learn.microsoft.com/en-us/purview/purview-portal)

---

## 5. Microsoft Purview Compliance Manager

**Compliance Manager** is a risk-based compliance management tool in the Microsoft Purview portal that helps organizations manage, measure, and improve their compliance posture across regulations and standards.

### Key Components

| Component | Description |
|---|---|
| **Compliance Score** | A risk-based score (higher = better compliance posture) that tracks how well your configuration aligns with applicable regulations |
| **Assessments** | Groups of controls mapped to a specific regulation or standard (e.g., GDPR, HIPAA, ISO 27001, NIST) |
| **Improvement Actions** | Specific, actionable steps you can take to implement controls and raise your score |
| **Controls** | The specific requirements of a regulation (mapped to both Microsoft-managed and customer-managed actions) |
| **Templates** | Pre-built assessment templates for 350+ regulations and standards globally |

### How the Compliance Score Works

| Action Type | Description |
|---|---|
| **Microsoft-managed actions** | Controls implemented by Microsoft (automatic — Microsoft maintains these for cloud services) |
| **Customer-managed actions** | Controls you must implement in your own environment (manually marked as implemented) |

> ⚠️ **Critical:** The Compliance Score is **NOT a legal guarantee** of compliance with any regulation. It reflects the extent to which specified controls have been implemented. Legal and regulatory interpretation still requires your own legal counsel.

### Supported Regulations & Standards (Examples)

GDPR, HIPAA/HITECH, ISO 27001, ISO 27018, NIST CSF, NIST 800-53, FedRAMP, SOC 2, PCI DSS, CCPA, and 350+ more.

📖 **References:**
- [What is Compliance Manager?](https://learn.microsoft.com/en-us/microsoft-365/compliance/compliance-manager)
- [Compliance Manager assessments](https://learn.microsoft.com/en-us/microsoft-365/compliance/compliance-manager-assessments)

---

## 6. Data Classification

Before you can protect sensitive data, you need to know where it is and what kind of data it is. Microsoft Purview provides several tools to **discover, classify, and understand** your data.

### Classification Methods

| Method | How It Works | Best For |
|---|---|---|
| **Sensitive Information Types (SITs)** | Pattern-based matching using keywords, regular expressions, and checksum validation | Known structured data: credit card numbers, SSNs, passport numbers, IBAN |
| **Trainable Classifiers** | Machine learning models trained on example content to recognize categories | Unstructured content: resumes, contracts, source code, financial documents |
| **Exact Data Match (EDM)** | Match against a specific database of sensitive records (e.g., your customer list) | High-accuracy detection for known specific records |

### Classification Tools

| Tool | Purpose |
|---|---|
| **Content Explorer** | Browse and view all items containing sensitive information or sensitivity labels across your organization |
| **Activity Explorer** | Monitor what's being done with labeled and sensitive content (label changes, policy matches, file activities) |
| **Data Map** | Discover and map data sources across your hybrid data estate (Microsoft Purview governance) |

> 💡 **Content Explorer** shows you **what** sensitive data exists. **Activity Explorer** shows you **what's happening** to that data. Both require appropriate RBAC roles to access.

📖 **References:**
- [Learn about sensitive information types](https://learn.microsoft.com/en-us/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Learn about trainable classifiers](https://learn.microsoft.com/en-us/microsoft-365/compliance/classifier-learn-about)
- [Get started with content explorer](https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-content-explorer)

---

## 7. Sensitivity Labels

**Sensitivity labels** are metadata tags applied to content (documents, emails, meetings, sites) that define the sensitivity of the content and enforce protection settings wherever the content travels.

### What Sensitivity Labels Can Do

| Action | Description |
|---|---|
| **Encryption** | Restrict who can open, read, print, or edit the content |
| **Access control** | Define who can access the content and what they can do |
| **Visual markings** | Add headers, footers, or watermarks to documents |
| **Container protection** | Protect SharePoint sites, Teams, and Microsoft 365 Groups |
| **Auto-labeling** | Automatically apply labels based on detected sensitive content |
| **Co-authoring** | Supports encrypted documents with real-time collaboration in Microsoft 365 apps |

### Label Application Methods

| Method | Description |
|---|---|
| **Manual** | Users choose a label when creating or modifying content |
| **Default label** | A label is automatically applied to new content without one |
| **Recommended** | Users are prompted to apply a suggested label |
| **Automatic** | Labels are applied automatically based on SITs or trainable classifiers (requires P2) |

### Label Scope

| Scope | What It Covers |
|---|---|
| **Files & emails** | Word, Excel, PowerPoint files; Outlook emails |
| **Meetings & calendar items** | Teams meetings and calendar invites |
| **Groups & sites** | SharePoint sites, Teams, Microsoft 365 Groups |
| **Schematized data assets** | Azure SQL, Synapse, Azure Purview data assets |

### Licensing

| Feature | License Required |
|---|---|
| Manual sensitivity labels | Microsoft 365 E3 / Business Premium |
| Auto-labeling (client-side) | Microsoft 365 E3 |
| Auto-labeling (service-side) | **Microsoft 365 E5 / Compliance E5** |

📖 **References:**
- [Learn about sensitivity labels](https://learn.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels)
- [Apply sensitivity labels automatically](https://learn.microsoft.com/en-us/microsoft-365/compliance/apply-sensitivity-label-automatically)

---

## 8. Data Loss Prevention (DLP)

**Data Loss Prevention (DLP)** policies help prevent the accidental or intentional sharing of sensitive information outside your organization.

### How DLP Works

1. **Detect** — DLP scans content for sensitive information using SITs, sensitivity labels, or keywords
2. **Evaluate** — Content is evaluated against configured policy rules
3. **Act** — When a rule is matched, DLP takes the configured action

### Where DLP Policies Apply

| Location | Description |
|---|---|
| **Exchange Online** | Email messages sent or received |
| **SharePoint Online** | Files stored in SharePoint sites |
| **OneDrive for Business** | Files stored in OneDrive |
| **Microsoft Teams** | Teams chat and channel messages |
| **Microsoft 365 apps** | Word, Excel, PowerPoint (endpoint DLP) |
| **Endpoints** | Windows 10/11 devices (Endpoint DLP — detect USB transfers, print, clipboard) |
| **Third-party apps** | Via Microsoft Defender for Cloud Apps integration |
| **On-premises** | On-premises file shares and SharePoint (requires DLP scanner) |

### DLP Policy Actions

| Action | Description |
|---|---|
| **Block sharing** | Prevent the content from being sent or shared |
| **Block with override** | Block but allow users to provide a business justification to override |
| **Notify user** | Show a policy tip in the app, educating the user |
| **Generate alert** | Send an alert to compliance administrators |
| **Restrict access** | Remove external sharing permissions from a SharePoint item |
| **Quarantine** | Move the item to a quarantine folder (Endpoint DLP) |

### DLP Policy Tips

**Policy tips** are in-app notifications shown to users when they are about to violate a DLP policy (e.g., before sending an email containing credit card numbers). They educate users in real time without blocking the action by default.

📖 **References:**
- [Learn about DLP](https://learn.microsoft.com/en-us/microsoft-365/compliance/dlp-learn-about-dlp)
- [Get started with DLP](https://learn.microsoft.com/en-us/microsoft-365/compliance/get-started-with-dlp-policy-recommendations)

---

## 9. Retention Policies & Retention Labels

**Retention policies** and **retention labels** ensure that content is kept for as long as legally required and deleted when no longer needed.

### Why Retention Matters

Organizations face legal and regulatory requirements to:
- **Retain** specific content for minimum periods (e.g., financial records for 7 years)
- **Delete** content after a period to minimize legal exposure and storage costs
- **Declare** content as immutable records that cannot be modified

### Retention Policies vs. Retention Labels

| | Retention Policies | Retention Labels |
|---|---|---|
| **Applied to** | Entire locations (all mailboxes, all SharePoint sites) | Individual items (specific documents, emails) |
| **Granularity** | Coarse — applies broadly | Fine — item-level control |
| **User interaction** | None (applied automatically in the background) | Can be applied manually or automatically |
| **Records declaration** | No | ✅ Yes — can declare items as records |
| **Event-based retention** | No | ✅ Yes — trigger retention based on an event |

### Retention Outcomes

| Setting | Description |
|---|---|
| **Retain only** | Keep content for the specified period; no action at end |
| **Delete only** | Delete content after the specified period |
| **Retain then delete** | Keep for the period, then permanently delete |

### Event-Based Retention

**Event-based retention** starts the retention clock when a specific event occurs (e.g., an employee leaves, a contract expires, a product is discontinued). Used for records management.

📖 **References:**
- [Learn about retention policies and labels](https://learn.microsoft.com/en-us/microsoft-365/compliance/retention)
- [Create and configure retention policies](https://learn.microsoft.com/en-us/microsoft-365/compliance/create-retention-policies)

---

## 10. Records Management

**Records management** in Microsoft Purview manages regulatory, legal, and business-critical records throughout their lifecycle — from creation, through active use, to final disposition.

### What Makes Something a "Record"?

When content is declared a **record** (via a retention label configured for records):
- It **cannot be modified or deleted** until the retention period ends
- All changes and deletions are blocked and logged
- At the end of the retention period, a **disposition review** may be triggered

### Record vs. Regulatory Record

| Type | Editable | Deletable by User | Deletable by Admin |
|---|---|---|---|
| **Record** | ❌ No | ❌ No | ✅ Yes (with justification) |
| **Regulatory Record** | ❌ No | ❌ No | ❌ No (even admins cannot delete) |

### Disposition Reviews

At the end of a retention period, items can go through a **disposition review** where authorized reviewers decide whether to:
- Delete the item permanently
- Extend the retention period
- Relabel the item

📖 **Reference:** [Learn about records management](https://learn.microsoft.com/en-us/microsoft-365/compliance/records-management)

---

## 11. Insider Risk Management

**Microsoft Purview Insider Risk Management** identifies, investigates, and acts on malicious or inadvertent insider risks within an organization. It correlates signals from Microsoft 365, HR systems, and endpoints.

### Types of Risks Detected

| Risk Category | Examples |
|---|---|
| **Data theft** | Employee copying files to USB or personal cloud storage before leaving |
| **Data leaks** | Sensitive data being emailed externally or posted to collaboration tools |
| **Security policy violations** | Installing unauthorized software, accessing restricted systems |
| **Offensive content** | Harassment, threats, or discriminatory content in communications |
| **Workplace fraud** | Manipulating financial records or falsifying expense reports |

### Key Design Principles

| Principle | Description |
|---|---|
| **Privacy by default** | User identities are **pseudonymized** (anonymized) by default — shown as "User1", "User2" etc. Only authorized reviewers can de-anonymize |
| **Configurable policies** | Define thresholds and triggers to minimize false positives |
| **Workflow built-in** | End-to-end workflow from alert → triage → investigation → action (notify, escalate, HR case) |
| **Integration** | Integrates with HR systems, Conditional Access, eDiscovery, and Microsoft Teams |

### Policy Trigger Examples

| Trigger | Description |
|---|---|
| **Resignation / termination date** | HR system signals a user is leaving — heightened monitoring for data exfiltration |
| **Repeated security alerts** | Multiple Defender for Endpoint alerts for the same user |
| **Anomalous download volume** | A user downloads significantly more data than their baseline |

> ⚠️ **Privacy note:** Insider Risk Management is privacy-conscious by design. Pseudonymization ensures that analysts cannot see real user names until a case is formally opened and appropriate approvals are granted.

📖 **Reference:** [Learn about insider risk management](https://learn.microsoft.com/en-us/microsoft-365/compliance/insider-risk-management)

---

## 12. Communication Compliance

**Microsoft Purview Communication Compliance** helps organizations detect, capture, and investigate inappropriate communications across Microsoft Teams, Exchange, Viva Engage (Yammer), and third-party platforms.

### What It Monitors

| Category | Examples |
|---|---|
| **Regulatory compliance** | Financial advisors discussing securities (SEC/FINRA requirements) |
| **Code of conduct violations** | Harassment, threats, discriminatory language |
| **Conflict of interest** | Internal communications that reveal inappropriate relationships |
| **Sensitive information** | Unauthorized sharing of confidential business information |

### How It Works

1. **Configure policies** — define what to monitor, who is in scope, and what reviewers will investigate
2. **Capture communications** — the service captures matching messages across configured channels
3. **Review & investigate** — designated reviewers receive alerts and investigate flagged content
4. **Take action** — notify the user, escalate to HR/Legal, or create an eDiscovery case

> 💡 Communication Compliance is distinct from **DLP**. DLP prevents data from leaving; Communication Compliance monitors the **content of communications** for inappropriate or non-compliant messaging.

📖 **Reference:** [Learn about communication compliance](https://learn.microsoft.com/en-us/microsoft-365/compliance/communication-compliance)

---

## 13. eDiscovery

**eDiscovery** (Electronic Discovery) is the process of identifying, collecting, and producing electronically stored information (ESI) for use as evidence in legal, regulatory, or internal investigations.

### eDiscovery Solutions in Microsoft Purview

| Solution | Description | Key Capabilities |
|---|---|---|
| **Content Search** | Basic search across Microsoft 365 content locations | Search Exchange, SharePoint, OneDrive, Teams; export results |
| **eDiscovery (Standard)** | Case-based eDiscovery with hold capabilities | Case management, legal holds, export |
| **eDiscovery (Premium)** | End-to-end enterprise eDiscovery workflow | Custodian management, review sets, analytics, AI-driven deduplication, predictive coding |

### eDiscovery Standard vs. Premium

| Feature | Standard | Premium |
|---|---|---|
| Case management | ✅ | ✅ |
| Legal holds | ✅ | ✅ |
| Content search & export | ✅ | ✅ |
| Custodian management | ❌ | ✅ |
| Review sets | ❌ | ✅ |
| Advanced analytics | ❌ | ✅ |
| AI deduplication / near-duplicate detection | ❌ | ✅ |
| Predictive coding (ML relevance) | ❌ | ✅ |
| License required | E3 | **E5 or Compliance add-on** |

### Legal Hold

A **legal hold** (also called a litigation hold) preserves content that may be relevant to a legal matter. It prevents users from deleting or modifying content for the duration of the hold — even if a retention policy would normally delete it.

### Custodians

In eDiscovery Premium, a **custodian** is a person who has control over data relevant to a case (e.g., the employee whose mailbox and OneDrive need to be preserved and searched).

📖 **References:**
- [eDiscovery solutions in Microsoft Purview](https://learn.microsoft.com/en-us/microsoft-365/compliance/ediscovery)
- [eDiscovery (Premium) overview](https://learn.microsoft.com/en-us/microsoft-365/compliance/overview-ediscovery-20)

---

## 14. Microsoft Purview Audit

**Microsoft Purview Audit** records user and administrator activities across Microsoft 365 services to support security investigations, forensic analysis, and regulatory compliance.

### Audit Tiers

| | Audit (Standard) | Audit (Premium) |
|---|---|---|
| **Log retention** | 90 days | **1 year** (default; extendable to **10 years** with add-on) |
| **Access** | Included in Microsoft 365 E3 | Requires **Microsoft 365 E5** or Compliance add-on |
| **Intelligent insights** | ❌ | ✅ (MailItemsAccessed and other high-value events) |
| **API bandwidth** | Standard | **Higher bandwidth** access for large-scale exports |
| **Audit log search** | ✅ | ✅ |

### What Gets Logged

| Activity Category | Examples |
|---|---|
| **Exchange Online** | Mailbox access, email sends, folder operations |
| **SharePoint & OneDrive** | File access, sharing, permission changes |
| **Microsoft Teams** | Messages sent, meetings created, member changes |
| **Microsoft Entra ID** | Sign-ins, user creation, role assignments |
| **Microsoft Purview** | Label changes, DLP policy matches, content searches |
| **Azure** | Azure resource operations (via Azure Activity Log) |

> ⚠️ **Exam Note:** Audit (Standard) retains logs for **90 days**. Audit (Premium) retains for **1 year** by default (extendable to 10 years). The higher-bandwidth API and intelligent insights (like MailItemsAccessed) are Premium-only features. These distinctions are tested.

📖 **Reference:** [Microsoft Purview Audit solutions overview](https://learn.microsoft.com/en-us/microsoft-365/compliance/auditing-solutions-overview)

---

## 15. Exam Tips & Key Takeaways

### 🎯 Must-Know for the Exam

| Topic | What to Remember |
|---|---|
| **Service Trust Portal** | Public hub for Microsoft audit reports & compliance docs (servicetrust.microsoft.com) |
| **Compliance Manager** | Risk-based compliance score + improvement actions — NOT a legal guarantee |
| **Compliance Score** | Higher = better posture; reflects control implementation, not legal compliance |
| **Sensitivity Labels** | Travel with content; can encrypt, apply visual markings, restrict access |
| **DLP** | Prevents sensitive data from leaving the org; policy tips notify users in real time |
| **Retention vs. DLP** | Retention = how long to keep/delete; DLP = prevent inappropriate sharing |
| **Retention Labels vs. Policies** | Labels = item-level, can declare records; Policies = location-level, broad coverage |
| **Records** | Cannot be modified or deleted until retention period ends |
| **Regulatory Records** | Even more restrictive — admins cannot delete them either |
| **Insider Risk** | Uses pseudonymization by default; detects data theft, leaks, violations |
| **Communication Compliance** | Monitors communication content for conduct violations and regulatory requirements |
| **eDiscovery Standard vs Premium** | Premium adds custodians, review sets, analytics, predictive coding |
| **Audit Standard vs Premium** | Standard = 90 days; Premium = 1 year (default) with intelligent insights |
| **Microsoft Priva** | Privacy Risk Management + Subject Rights Requests (GDPR/CCPA) |

### 📊 Purview Solutions Quick Reference

| Need | Solution |
|---|---|
| Know where sensitive data is | Data Classification (Content Explorer) |
| Label and protect sensitive documents | Sensitivity Labels |
| Prevent sharing sensitive data externally | DLP Policies |
| Keep financial records for 7 years | Retention Labels / Policies |
| Immutably preserve legal records | Records Management |
| Detect risky employee behavior | Insider Risk Management |
| Monitor messaging for conduct violations | Communication Compliance |
| Respond to GDPR right to erasure requests | Microsoft Priva — Subject Rights Requests |
| Collect evidence for legal case | eDiscovery (Standard or Premium) |
| Investigate who accessed a mailbox | Microsoft Purview Audit |
| Measure compliance against GDPR / ISO 27001 | Compliance Manager |
| View Microsoft's own audit reports | Service Trust Portal |

### ⚡ Common Exam Traps

- **Compliance Score ≠ legal compliance** — it's a risk indicator, not a guarantee
- **Retention labels** can declare records; **Retention policies** cannot
- **DLP** prevents *sharing*; **Retention** controls *keeping* vs *deleting*
- **Insider Risk Management** pseudonymizes identities by default — reviewers cannot see real names until a case is opened
- **Audit (Standard) = 90 days** — not 1 year; that requires Premium
- **eDiscovery (Premium)** adds custodian management and review sets — Standard does not have these
- **Microsoft Priva** is a privacy tool (for personal data / data subjects) — it is separate from Purview compliance tools
- **Communication Compliance** ≠ **DLP** — they solve different problems (messaging conduct vs. data exfiltration)

---

## 📚 Official Microsoft Learn Resources

| Resource | Link |
|---|---|
| Learning Path: Describe capabilities of Microsoft compliance solutions | [Open](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-compliance-solutions/) |
| Module: Describe compliance management capabilities | [Open](https://learn.microsoft.com/en-us/training/modules/describe-compliance-management-capabilities-microsoft/) |
| Module: Describe information protection and data lifecycle management | [Open](https://learn.microsoft.com/en-us/training/modules/describe-information-protection-governance-capabilities-microsoft-365/) |
| Module: Describe insider risk capabilities | [Open](https://learn.microsoft.com/en-us/training/modules/describe-insider-risk-capabilities-microsoft-365/) |
| Module: Describe eDiscovery and audit capabilities | [Open](https://learn.microsoft.com/en-us/training/modules/describe-ediscovery-capabilities-of-microsoft-365/) |
| Microsoft Service Trust Portal | [Open](https://servicetrust.microsoft.com) |
| Compliance Manager documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/compliance-manager) |
| Sensitivity labels documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels) |
| DLP documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/dlp-learn-about-dlp) |
| Retention policies documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/retention) |
| Insider Risk Management documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/insider-risk-management) |
| eDiscovery documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/ediscovery) |
| Microsoft Purview Audit documentation | [Open](https://learn.microsoft.com/en-us/microsoft-365/compliance/auditing-solutions-overview) |
| Microsoft Priva documentation | [Open](https://learn.microsoft.com/en-us/privacy/priva/priva-overview) |
| SC-900 Certification Page | [Open](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/) |
| Free Practice Assessment | [Open](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/practice/assessment?assessment-type=practice&assessmentId=11) |

---

*Last updated: May 2026 · Aligned with SC-900 exam objectives (November 2025 update)*
