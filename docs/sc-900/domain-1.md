# SC-900 — Domain 1: Security, Compliance & Identity Concepts

> **Exam Weight:** 10–15% &nbsp;|&nbsp; **Difficulty:** Foundational  
> **Official Study Guide:** [SC-900 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-900)  
> **Learning Path:** [Describe concepts of security, compliance, and identity](https://learn.microsoft.com/en-us/training/paths/describe-concepts-of-security-compliance-identity/)

---

## Table of Contents

1. [Shared Responsibility Model](#1-shared-responsibility-model)
2. [Defense-in-Depth](#2-defense-in-depth)
3. [Zero Trust Model](#3-zero-trust-model)
4. [Encryption & Hashing](#4-encryption--hashing)
5. [Identity Concepts](#5-identity-concepts)
6. [Authentication & Authorization](#6-authentication--authorization)
7. [Federation & Single Sign-On](#7-federation--single-sign-on)
8. [Governance, Risk & Compliance (GRC)](#8-governance-risk--compliance-grc)
9. [CIA Triad](#9-cia-triad)
10. [Exam Tips & Key Takeaways](#10-exam-tips--key-takeaways)

---

## 1. Shared Responsibility Model

The **Shared Responsibility Model** defines how security obligations are divided between a cloud provider (Microsoft Azure) and the customer. Responsibility shifts depending on the cloud service type.

| Responsibility | On-Premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Data & Identity | Customer | Customer | Customer | Customer |
| Applications | Customer | Customer | Customer | Provider |
| Runtime / Middleware | Customer | Customer | Provider | Provider |
| Operating System | Customer | Customer | Provider | Provider |
| Virtualization | Customer | Provider | Provider | Provider |
| Physical Infra | Customer | Provider | Provider | Provider |

### Service Model Definitions

- **IaaS (Infrastructure as a Service)** — Customer manages OS, applications, and data. Provider manages physical infrastructure, networking, and virtualization. *(e.g., Azure Virtual Machines)*
- **PaaS (Platform as a Service)** — Provider manages OS and runtime; customer manages applications and data. *(e.g., Azure App Service, Azure SQL Database)*
- **SaaS (Software as a Service)** — Provider manages nearly everything; customer manages only data and user access. *(e.g., Microsoft 365, Dynamics 365)*

> ⚠️ **Critical Rule:** In **all** cloud models, the customer always retains responsibility for **data**, **identity**, and **endpoint devices**.

📖 **Reference:** [Describe the shared responsibility model](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/2-describe-shared-responsibility-model)

---

## 2. Defense-in-Depth

**Defense-in-Depth** is a layered security strategy where multiple independent defensive controls protect data. If one layer is breached, subsequent layers continue to provide protection.

### The 7 Layers (outer → inner)

| # | Layer | Purpose | Examples |
|---|---|---|---|
| 1 | **Physical** | Protect physical data centers | Badge readers, surveillance, locked doors |
| 2 | **Identity & Access** | Authenticate and authorize access | MFA, Conditional Access, RBAC |
| 3 | **Perimeter** | Protect network boundary | DDoS Protection, Azure Firewall |
| 4 | **Network** | Limit communication between resources | NSGs, network segmentation, VPNs |
| 5 | **Compute** | Secure endpoints and VMs | Antimalware, OS patches, Defender for Endpoint |
| 6 | **Application** | Ensure apps are secure | Secure coding, vulnerability scanning |
| 7 | **Data** | Protect data at rest and in transit | Encryption, Azure Key Vault |

> ⚠️ **Exam Alert:** The **order** of these layers is frequently tested. Memorize: Physical → Identity → Perimeter → Network → Compute → Application → Data.

📖 **Reference:** [Describe defense-in-depth](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/3-describe-defense-depth)

---

## 3. Zero Trust Model

**Zero Trust** is a security model that operates on the principle of **"Never trust, always verify."** It assumes every access request could be compromised, regardless of whether it originates inside or outside the network perimeter.

### The Three Guiding Principles

| Principle | Description |
|---|---|
| **Verify Explicitly** | Always authenticate and authorize based on all available data points: identity, location, device health, service/workload, data classification, and anomalies |
| **Use Least Privilege Access** | Limit user access with just-in-time (JIT) and just-enough-access (JEA), risk-based adaptive policies, and data protection |
| **Assume Breach** | Minimize blast radius, segment access, verify end-to-end encryption, and use analytics to detect and improve defenses |

### The Six Foundational Pillars

| Pillar | Focus |
|---|---|
| **Identities** | Verify and secure every identity with strong authentication |
| **Devices** | Ensure device compliance and health before granting access |
| **Applications** | Discover all apps in use (including shadow IT), control permissions |
| **Data** | Classify, label, and protect data based on its sensitivity |
| **Infrastructure** | Use telemetry to detect attacks and anomalies in real time |
| **Networks** | Segment networks, use real-time threat protection and encryption |

> 💡 **Zero Trust ≠ Zero Access.** It means verify before trusting — even for internal users. This contrasts with the traditional "castle-and-moat" perimeter model where internal traffic was implicitly trusted.

📖 **Reference:** [Describe the Zero Trust model](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/4-describe-zero-trust-model)

---

## 4. Encryption & Hashing

### Encryption

Encryption converts data into an unreadable format (ciphertext) using an algorithm and a key. It is **reversible** — data can be decrypted with the appropriate key.

#### Types of Encryption

| Type | Description | Use Case |
|---|---|---|
| **Symmetric** | Same key for encryption and decryption (e.g., AES) | Fast; used for large data volumes |
| **Asymmetric** | Public/private key pair (e.g., RSA, TLS/SSL) | Authentication, key exchange, digital signatures |

#### Encryption States

| State | Description | Example |
|---|---|---|
| **At Rest** | Data stored on disk, database, or storage | Azure Storage Service Encryption |
| **In Transit** | Data moving over a network | TLS / HTTPS |
| **In Use** | Data actively being processed | Confidential computing |

### Hashing

Hashing is a **one-way, irreversible** function that converts data into a fixed-length hash value. It is used for:
- Password storage (store the hash, not the password)
- Data integrity verification (verify file hasn't been altered)

| Algorithm | Output Size | Notes |
|---|---|---|
| MD5 | 128-bit | Deprecated; collision vulnerabilities |
| SHA-256 | 256-bit | Current standard |
| SHA-3 | Variable | Latest generation |

#### Salting

**Salting** adds a unique random value to each password before hashing. This prevents:
- **Rainbow table attacks** — pre-computed hash lookups
- **Identical passwords producing identical hashes**

> 🔑 **Key Distinction:** Encryption = reversible (with a key). Hashing = irreversible (one-way). This difference is tested directly.

### Azure Key Vault

**Azure Key Vault** is a cloud service for securely storing and managing:

| Type | Examples |
|---|---|
| **Secrets** | API keys, passwords, connection strings |
| **Keys** | Cryptographic keys for data encryption |
| **Certificates** | SSL/TLS certificates |

📖 **References:**
- [Describe encryption and hashing](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/5-describe-encryption-hashing)
- [Azure Key Vault overview](https://learn.microsoft.com/en-us/azure/key-vault/general/overview)

---

## 5. Identity Concepts

In modern cloud environments, **identity has become the new security perimeter**. Traditional network-based perimeters are no longer sufficient as users work from anywhere, on any device.

### Core Identity Terms

| Term | Definition |
|---|---|
| **Identity** | A set of attributes that uniquely identifies a user, device, or service |
| **Identity Provider (IdP)** | A service that creates, maintains, and manages digital identities (e.g., Microsoft Entra ID) |
| **Active Directory (AD)** | Microsoft's on-premises directory service for managing users and resources |
| **Directory Services** | An organized collection of identity data enabling centralized management |
| **Tenant** | A dedicated, isolated instance of Microsoft Entra ID representing an organization |

### Types of Identities

| Identity Type | Description |
|---|---|
| **User** | Human identity — employees, students, external guests |
| **Service Principal** | Identity for an application or automated service |
| **Managed Identity** | Azure-managed identity for Azure services (no credential management needed) |
| **Device** | Physical or virtual device registered with Entra ID |

📖 **Reference:** [Describe identity concepts](https://learn.microsoft.com/en-us/training/modules/describe-identity-principles-concepts/2-describe-identity-as-the-primary-security-perimeter)

---

## 6. Authentication & Authorization

### Authentication (AuthN)

**Authentication** is the process of **proving who you are** — verifying an identity before granting access.

### Authorization (AuthZ)

**Authorization** determines **what an authenticated identity is allowed to do** — defining permissions and access levels.

> ⚠️ **Order matters:** Authentication always occurs **before** authorization. You must first prove who you are, then the system decides what you can access.

| Aspect | Authentication | Authorization |
|---|---|---|
| **Question** | Who are you? | What can you do? |
| **Verifies** | Identity | Permissions |
| **Result** | Identity confirmed | Access granted/denied |
| **Example** | Entering a password | Accessing a specific file share |

📖 **Reference:** [Describe authentication and authorization](https://learn.microsoft.com/en-us/training/modules/describe-identity-principles-concepts/3-describe-concept-of-authentication)

---

## 7. Federation & Single Sign-On

### Federation

**Federation** establishes a **trust relationship** between two or more identity providers. It allows users to authenticate with their home IdP and access resources in a federated partner's environment — without creating separate accounts.

**Example:** A user logs in with their company Microsoft Entra ID credentials and can also access a partner's AWS environment without a second login.

### Single Sign-On (SSO)

**SSO** allows a user to sign in once and access multiple applications without re-authenticating. Benefits:
- Reduces password fatigue
- Centralizes access management
- Easier to enforce consistent security policies

📖 **References:**
- [Describe federation](https://learn.microsoft.com/en-us/training/modules/describe-identity-principles-concepts/5-describe-concept-of-federation)
- [What is SSO in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/what-is-single-sign-on)

---

## 8. Governance, Risk & Compliance (GRC)

**GRC** is a framework that helps organizations balance business goals with IT operations while managing risk and meeting regulatory requirements.

| Pillar | Definition | Examples |
|---|---|---|
| **Governance** | Rules, practices, and processes for managing and directing an organization | IT policies, data governance frameworks |
| **Risk** | Identifying, assessing, and mitigating potential threats to the organization | Risk registers, vulnerability assessments |
| **Compliance** | Adhering to external laws, regulations, and standards | GDPR, HIPAA, ISO 27001, SOC 2 |

> 💡 **Tip:** These three pillars are related but distinct. Compliance = external regulations. Governance = internal rules. Risk = threat management.

📖 **Reference:** [Describe GRC concepts](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/6-describe-grc-concepts)

---

## 9. CIA Triad

The **CIA Triad** is the foundational security model describing the three core goals of information security:

| Pillar | Definition | Threat Example |
|---|---|---|
| **Confidentiality** | Ensure data is accessible only to authorized parties | Data breach, unauthorized access |
| **Integrity** | Ensure data is accurate and has not been tampered with | Man-in-the-middle attack, data corruption |
| **Availability** | Ensure systems and data are available when needed | DDoS attack, ransomware |

📖 **Reference:** [Describe the CIA triad](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/2-describe-shared-responsibility-model)

---

## 10. Exam Tips & Key Takeaways

### 🎯 Must-Know for the Exam

| Topic | What to Remember |
|---|---|
| **Shared Responsibility** | Customer ALWAYS owns Data + Identity in every model (IaaS/PaaS/SaaS) |
| **Defense-in-Depth Layers** | Order: Physical → Identity → Perimeter → Network → Compute → Application → Data |
| **Zero Trust Principles** | Verify Explicitly, Use Least Privilege, Assume Breach — all three required |
| **Encryption vs Hashing** | Encryption = reversible; Hashing = one-way/irreversible |
| **Symmetric vs Asymmetric** | Symmetric = same key (fast); Asymmetric = key pair (secure key exchange) |
| **AuthN vs AuthZ** | AuthN = prove identity; AuthZ = determine permissions. AuthN always first. |
| **Federation** | Trust relationship between IdPs — enables SSO across organizations |
| **Azure Key Vault** | Stores three types: Keys, Secrets, Certificates |
| **GRC** | Governance (internal rules), Risk (threat management), Compliance (external regulations) |

### ⚡ Common Exam Traps

- Zero Trust is NOT about denying all access — it means **verify before trusting**
- SaaS customers are responsible for **data and user access** — NOT the application layer
- Salting prevents **rainbow table attacks** (not brute force directly)
- **Authentication comes before authorization** — never confuse the order

---

## 📚 Official Microsoft Learn Resources

| Resource | Link |
|---|---|
| Learning Path: Describe concepts of security, compliance, and identity | [Open](https://learn.microsoft.com/en-us/training/paths/describe-concepts-of-security-compliance-identity/) |
| Module: Describe security concepts and methodologies | [Open](https://learn.microsoft.com/en-us/training/modules/describe-security-concepts-methodologies/) |
| Module: Describe identity principles and concepts | [Open](https://learn.microsoft.com/en-us/training/modules/describe-identity-principles-concepts/) |
| SC-900 Certification Page | [Open](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/) |
| SC-900 Study Guide (Nov 2025) | [Open](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-900) |
| Free Practice Assessment | [Open](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/practice/assessment?assessment-type=practice&assessmentId=11) |

---

*Last updated: May 2026 · Aligned with SC-900 exam objectives (November 2025 update)*
