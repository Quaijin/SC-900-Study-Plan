# SC-900 — Domain 2: Capabilities of Microsoft Entra

> **Exam Weight:** 25–30% &nbsp;|&nbsp; **Difficulty:** Intermediate  
> **Official Study Guide:** [SC-900 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/sc-900)  
> **Learning Path:** [Describe capabilities of Microsoft Entra](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-entra/)

---

## Table of Contents

1. [Microsoft Entra ID Overview](#1-microsoft-entra-id-overview)
2. [Types of Identities](#2-types-of-identities)
3. [Hybrid Identity](#3-hybrid-identity)
4. [Authentication Methods & MFA](#4-authentication-methods--mfa)
5. [Self-Service Password Reset (SSPR)](#5-self-service-password-reset-sspr)
6. [Passwordless Authentication](#6-passwordless-authentication)
7. [Conditional Access](#7-conditional-access)
8. [Role-Based Access Control (RBAC)](#8-role-based-access-control-rbac)
9. [Identity Governance](#9-identity-governance)
10. [Privileged Identity Management (PIM)](#10-privileged-identity-management-pim)
11. [Microsoft Entra ID Protection](#11-microsoft-entra-id-protection)
12. [External Identities (B2B & B2C)](#12-external-identities-b2b--b2c)
13. [Entitlement Management](#13-entitlement-management)
14. [Exam Tips & Key Takeaways](#14-exam-tips--key-takeaways)

---

## 1. Microsoft Entra ID Overview

**Microsoft Entra ID** (formerly Azure Active Directory / Azure AD) is Microsoft's cloud-native identity and access management (IAM) service. It is the backbone of authentication and authorization for Microsoft cloud services and thousands of third-party SaaS applications.

### What Entra ID Provides

| Capability | Description |
|---|---|
| **Authentication** | Verify identity for Microsoft 365, Azure, and integrated apps |
| **Single Sign-On (SSO)** | One login to access thousands of applications |
| **MFA & Passwordless** | Stronger authentication than passwords alone |
| **Conditional Access** | Policy-based access control (Zero Trust enforcement) |
| **Application Management** | Register and manage app access |
| **Device Management** | Register and manage devices |
| **Identity Governance** | Manage access lifecycle with reviews, PIM, and entitlement management |
| **External Identities** | Collaborate with guests (B2B) or serve customers (B2C) |

### Entra ID vs. Windows Server Active Directory

| | Microsoft Entra ID | Windows Server AD |
|---|---|---|
| **Type** | Cloud-native IAM | On-premises directory service |
| **Protocol** | OAuth 2.0, OpenID Connect, SAML | Kerberos, NTLM, LDAP |
| **Queried via** | REST APIs (HTTPS) | LDAP |
| **Structure** | Flat (no OUs, no GPOs) | Hierarchical (OUs, GPOs, forests) |
| **MFA built-in** | ✅ Yes | ❌ No (requires add-ons) |
| **Use case** | Cloud & SaaS app access | On-prem Windows network resources |

> ⚠️ **Exam Alert:** Entra ID is **NOT** a cloud version of Windows AD — they are fundamentally different services. An Entra Global Admin does **not** automatically have access to on-premises AD, and vice versa.

📖 **Reference:** [What is Microsoft Entra ID?](https://learn.microsoft.com/en-us/entra/fundamentals/whatis)

---

## 2. Types of Identities

Microsoft Entra ID manages several types of identities:

### User Identities

| Type | Description |
|---|---|
| **Member user** | Standard internal employee account in the organization's tenant |
| **Guest user (B2B)** | External partner or collaborator invited to access resources |

### Workload Identities

| Type | Description |
|---|---|
| **Service Principal** | Identity for an application or service registered in Entra ID. Allows apps to authenticate and access resources. |
| **Managed Identity** | A special type of service principal managed entirely by Azure. No credentials to store or rotate. |

#### Managed Identity Types

| Type | Lifecycle | Sharing |
|---|---|---|
| **System-assigned** | Tied to the Azure resource — deleted when the resource is deleted | Cannot be shared across resources |
| **User-assigned** | Created independently of any resource; has its own lifecycle | Can be shared across multiple resources |

### Device Identities

| Registration Type | Description |
|---|---|
| **Entra Registered** | Personal (BYOD) devices. User can access work resources. No domain join required. |
| **Entra Joined** | Company-owned devices. Fully cloud-managed, no on-prem AD needed. |
| **Hybrid Entra Joined** | Devices joined to both on-prem AD and Entra ID. Common in hybrid environments. |

📖 **References:**

- [Identity types in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/fundamentals/identity-types-and-workloads)
- [Managed identities overview](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview)

---

## 3. Hybrid Identity

**Hybrid identity** connects an organization's on-premises Active Directory with Microsoft Entra ID, enabling a single identity to work across both environments.

### Microsoft Entra Connect

**Microsoft Entra Connect** (formerly Azure AD Connect) is the tool that synchronizes identities from on-premises AD to Entra ID.

### Authentication Methods for Hybrid Identity

| Method | How It Works | On-Prem AD Required |
|---|---|---|
| **Password Hash Sync (PHS)** | Hash of the on-prem password is synced to Entra ID. Auth happens in the cloud. | No (auth is cloud-side) |
| **Pass-Through Authentication (PTA)** | Authentication request is passed to an on-prem agent for validation by AD. | Yes |
| **Federation (AD FS)** | Full federation using Active Directory Federation Services. Entra ID trusts AD FS for authentication. | Yes |

> 💡 **Password Hash Sync** is the simplest and most resilient option — authentication works even if on-prem AD is unavailable. PTA and Federation require on-prem connectivity.

📖 **References:**

- [What is hybrid identity?](https://learn.microsoft.com/en-us/entra/identity/hybrid/whatis-hybrid-identity)
- [Microsoft Entra Connect overview](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/whatis-azure-ad-connect)

---

## 4. Authentication Methods & MFA

### Authentication Methods Available in Entra ID

| Method | Category | Strength |
|---|---|---|
| **Password** | Something you know | Weakest |
| **SMS / Voice call** | Something you have | Weak (susceptible to SIM swap) |
| **OATH Software Token** | Something you have | Moderate |
| **OATH Hardware Token** | Something you have | Moderate-Strong |
| **Microsoft Authenticator (push)** | Something you have | Strong |
| **Microsoft Authenticator (passwordless)** | Passwordless | Very Strong |
| **Windows Hello for Business** | Biometric / PIN + device | Very Strong |
| **FIDO2 Security Keys** | Something you have | Strongest (hardware-bound) |

### Multi-Factor Authentication (MFA)

MFA requires **two or more** verification factors from **independent categories**:

| Factor Category | Examples |
|---|---|
| **Something you know** | Password, PIN, security question |
| **Something you have** | Phone, authenticator app, hardware token |
| **Something you are** | Fingerprint, face recognition, iris scan |

> 💡 MFA blocks over **99.9%** of account compromise attacks (Microsoft research). Any two factors from different categories qualify as MFA.

### MFA Licensing

| Feature | License Required |
|---|---|
| Security Defaults (basic MFA for all) | Free (Entra ID Free) |
| Per-user MFA | Microsoft 365 plans |
| Conditional Access–based MFA | **Entra ID P1 or P2** |
| Risk-based MFA (ID Protection) | **Entra ID P2** |

📖 **References:**

- [Authentication methods in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-methods)
- [How MFA works](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-mfa-howitworks)

---

## 5. Self-Service Password Reset (SSPR)

**SSPR** allows users to reset their own passwords without contacting IT support, reducing helpdesk burden and improving security.

### How SSPR Works

1. User goes to the SSPR portal (account.activedirectory.windowsazure.com/passwordreset)
2. Entra ID verifies the user's identity using pre-registered methods
3. User resets their password

### Supported Verification Methods

- Mobile app notification
- Mobile app code
- Email to external address
- Mobile phone (SMS or call)
- Office phone
- Security questions *(not recommended for highly sensitive accounts)*

### Licensing

| Scenario | License Required |
|---|---|
| Cloud-only SSPR | Entra ID P1 or P2 (or Microsoft 365 Business Premium) |
| On-premises password writeback | **Entra ID P1 or P2** |

📖 **Reference:** [How SSPR works](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-sspr-howitworks)

---

## 6. Passwordless Authentication

Passwordless methods eliminate the password entirely while still satisfying MFA requirements (they combine two factors by design).

| Method | Best For | Technology |
|---|---|---|
| **Windows Hello for Business** | Windows devices | Biometric (face/fingerprint) or PIN bound to device hardware (TPM) |
| **Microsoft Authenticator** | Mobile devices | Push notification + biometric/PIN on phone |
| **FIDO2 Security Keys** | Shared workstations, high-security environments | USB/NFC hardware key (phishing-resistant) |

> ⚠️ **Exam Note:** FIDO2 security keys are considered the **strongest** passwordless authentication method because they are phishing-resistant and hardware-bound. SMS is the **weakest** MFA method.

📖 **References:**

- [Passwordless authentication options](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-passwordless)
- [Windows Hello for Business overview](https://learn.microsoft.com/en-us/windows/security/identity-protection/hello-for-business/)
- [FIDO2 security keys](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-passwordless#fido2-security-keys)

---

## 7. Conditional Access

**Conditional Access** is Entra ID's policy engine — the primary tool for enforcing Zero Trust. It works as an **"if-then"** system: if certain signals are present, then enforce a specific access control decision.

### How Conditional Access Works

```
SIGNALS (IF)  ──►  DECISIONS (THEN)  ──►  ENFORCEMENT
```

#### Signals (Conditions)

| Signal | Examples |
|---|---|
| **User / Group** | Admin users, finance department, all guests |
| **Location** | Named trusted IP range, specific country |
| **Device** | Platform (iOS/Android/Windows), compliance state |
| **Application** | Specific app being accessed (e.g., SharePoint vs. Azure portal) |
| **Sign-in Risk** | Low / Medium / High (from Entra ID Protection) |
| **User Risk** | Low / Medium / High (from Entra ID Protection) |

#### Access Decisions

| Decision | Description |
|---|---|
| **Allow access** | Grant without additional requirements |
| **Require MFA** | Force multi-factor authentication |
| **Require compliant device** | Only allow access from Intune-managed, compliant devices |
| **Require Entra joined device** | Only allow Entra-joined machines |
| **Block access** | Deny access entirely |
| **Require Terms of Use** | Force acceptance of Terms of Use |
| **Require password change** | Force password reset before proceeding |

### Common Conditional Access Policies

| Scenario | Policy |
|---|---|
| Require MFA for all administrators | IF user = admin role → Require MFA |
| Block legacy authentication | IF auth protocol = POP3/IMAP/SMTP → Block |
| Allow access only from compliant devices | IF device ≠ compliant → Block |
| Require MFA for high-risk sign-ins | IF sign-in risk = High → Require MFA |
| Block access from unknown countries | IF location = non-trusted country → Block |

### Licensing

> Conditional Access requires **Microsoft Entra ID P1** or **P2**. It is NOT included in the free Entra ID tier.

> ⚠️ **Block policies ALWAYS take precedence** over grant policies. If a user matches both a block and a grant policy, they are blocked.

📖 **References:**

- [What is Conditional Access?](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)
- [Conditional Access policy components](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-policies)
- [Common Conditional Access policies](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-policy-common)

---

## 8. Role-Based Access Control (RBAC)

RBAC manages who can do what to which resources. It implements the **principle of least privilege** — grant only the minimum permissions needed.

### Two Separate RBAC Systems

| | Azure RBAC | Microsoft Entra ID Roles |
|---|---|---|
| **Controls access to** | Azure *resources* (VMs, storage, networking) | Entra ID *features* (users, groups, licenses, apps) |
| **Assigned at** | Management group, subscription, resource group, or resource | Directory level |
| **Managed in** | Azure portal / Azure Resource Manager | Microsoft Entra admin center |
| **Examples** | Owner, Contributor, Reader | Global Administrator, User Administrator |

> ⚠️ **Critical:** These are **two entirely separate systems**. An Entra Global Administrator does **NOT** automatically have Azure subscription access. An Azure Owner does NOT automatically have Entra admin rights.

### Azure RBAC — Key Built-in Roles

| Role | Permissions |
|---|---|
| **Owner** | Full access to all resources; can assign roles to others |
| **Contributor** | Create and manage all resources; **cannot** assign roles |
| **Reader** | View resources only; cannot make any changes |
| **User Access Administrator** | Manage user access to Azure resources only |

### Microsoft Entra ID — Key Built-in Roles

| Role | Permissions |
|---|---|
| **Global Administrator** | Full access to all Entra ID features and settings |
| **Security Administrator** | Manage security features in Entra and Microsoft 365 Defender |
| **User Administrator** | Create/manage users and groups; reset passwords |
| **Billing Administrator** | Manage subscriptions, billing, and service requests |
| **Helpdesk Administrator** | Reset passwords for non-admin users |
| **Application Administrator** | Create/manage app registrations and enterprise apps |

### RBAC Scope Hierarchy (Azure)

```
Management Group
    └── Subscription
            └── Resource Group
                    └── Resource
```

Permissions assigned at a higher scope are **inherited** by all child scopes.

📖 **References:**

- [Azure RBAC overview](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview)
- [Microsoft Entra built-in roles](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)

---

## 9. Identity Governance

**Microsoft Entra ID Governance** helps organizations balance security and employee productivity by ensuring the right people have the right access to the right resources — and for the right amount of time.

### Access Reviews

**Access reviews** allow organizations to periodically certify that users still require access to specific resources. This ensures stale permissions are identified and removed.

| What Can Be Reviewed | Who Can Review |
|---|---|
| Group memberships | Group owners |
| Application access | Application owners |
| Entra ID role assignments | Privileged role administrators |
| Azure resource role assignments | Resource owners |

**Key features:**

- Reviews can be one-time or recurring (weekly, monthly, quarterly, annually)
- Reviewers can approve, deny, or let the system decide based on recommendations
- Automated removal of access when a reviewer doesn't respond ("apply results automatically")

📖 **Reference:** [What are access reviews?](https://learn.microsoft.com/en-us/entra/id-governance/access-reviews-overview)

---

## 10. Privileged Identity Management (PIM)

**Privileged Identity Management (PIM)** manages, controls, and monitors access to high-privilege roles in Entra ID and Azure. It enforces the **principle of least privilege** for administrative accounts.

### PIM Key Capabilities

| Capability | Description |
|---|---|
| **Just-in-Time (JIT) Access** | Eligible users can activate privileged roles only when needed, for a limited time |
| **Time-Bound Assignments** | Set start and end dates for role assignments to auto-expire |
| **Approval Workflows** | Require a designated approver before a role can be activated |
| **MFA on Activation** | Require MFA every time a privileged role is activated |
| **Audit History** | Full log of all role activations, approvals, and assignments |
| **Notifications** | Email alerts when privileged roles are activated or assigned |
| **Access Reviews (built-in)** | Periodic reviews of privileged role assignments |

### PIM Role States

| State | Description |
|---|---|
| **Eligible** | User can activate the role but does not have it continuously |
| **Active** | User currently has the role's permissions (permanently or time-limited) |
| **Expired** | Role assignment has passed its end date |

### Licensing

> ⚠️ PIM requires **Microsoft Entra ID P2** (not P1). This is a common exam trap.

📖 **Reference:** [What is Privileged Identity Management?](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure)

---

## 11. Microsoft Entra ID Protection

**Microsoft Entra ID Protection** uses machine learning and Microsoft threat intelligence to automatically detect, investigate, and remediate identity-based risks.

### Risk Types

| Risk | Definition | Examples |
|---|---|---|
| **User Risk** | Probability that a user identity has been compromised | Leaked credentials found on dark web, anomalous user behavior |
| **Sign-in Risk** | Probability that a specific sign-in attempt is not from the legitimate user | Impossible travel, anonymous IP, unfamiliar sign-in properties, password spray |

### Risk Levels

Each risk type is assigned a level: **Low**, **Medium**, or **High**.

### Integration with Conditional Access

ID Protection generates risk signals. Conditional Access **consumes** these signals to enforce policies:

| Condition | Example Policy |
|---|---|
| Sign-in risk ≥ Medium | Require MFA |
| Sign-in risk = High | Block access |
| User risk = High | Require password change |

### Licensing

> Microsoft Entra ID Protection requires **Microsoft Entra ID P2** licensing.

📖 **References:**

- [What is Microsoft Entra ID Protection?](https://learn.microsoft.com/en-us/entra/id-protection/overview-identity-protection)
- [Risk-based Conditional Access policies](https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies)

---

## 12. External Identities (B2B & B2C)

### Microsoft Entra B2B (Business-to-Business)

**B2B collaboration** allows organizations to invite external users (partners, vendors, contractors) to access internal applications and resources using their own credentials.

| Feature | Description |
|---|---|
| **Guest accounts** | External users are represented as guest accounts (UserType = Guest) in your tenant |
| **Authentication** | Guests authenticate with their home IdP (Microsoft account, Google, enterprise IdP) |
| **Access control** | Governed by Conditional Access, access reviews, and entitlement management |
| **No credential management** | You don't manage the guest's passwords |

### Microsoft Entra External ID for Customers (B2C)

**B2C** (Business-to-Customer) is a Customer Identity and Access Management (CIAM) solution for building customer-facing apps.

| Feature | Description |
|---|---|
| **Use case** | Allow customers to register/sign-in to your apps using social accounts (Google, Facebook, Apple) or local accounts |
| **Customization** | Fully branded sign-in/sign-up experience |
| **Scalability** | Supports millions of users |
| **Separate tenant** | B2C uses a separate Azure AD B2C tenant from your corporate Entra ID |

📖 **References:**

- [B2B collaboration overview](https://learn.microsoft.com/en-us/entra/external-id/what-is-b2b)
- [Microsoft Entra External ID overview](https://learn.microsoft.com/en-us/entra/external-id/overview)

---

## 13. Entitlement Management

**Entitlement Management** is an identity governance feature that automates access request workflows, assignments, reviews, and expiration for resources.

### Access Packages

An **access package** bundles resources (groups, apps, SharePoint sites) that a user can request access to in one step.

| Feature | Description |
|---|---|
| **Catalog** | Container for access packages and resources |
| **Policies** | Define who can request, who approves, and how long access lasts |
| **Automatic expiration** | Access is automatically removed after a set period |
| **Guest access** | External users can also request access packages |

📖 **Reference:** [What is entitlement management?](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-overview)

---

## 14. Exam Tips & Key Takeaways

### 🎯 Must-Know for the Exam

| Topic | What to Remember |
|---|---|
| **Entra ID vs Windows AD** | Cloud IAM vs. on-prem directory — completely different protocols and purposes |
| **MFA Categories** | Know / Have / Are — two from different categories = MFA |
| **FIDO2 vs Windows Hello** | FIDO2 = strongest, phishing-resistant; Hello = best for Windows devices |
| **SMS as MFA** | SMS is the **weakest** MFA method — susceptible to SIM swapping |
| **Conditional Access licensing** | Requires Entra ID **P1** (risk-based policies require **P2**) |
| **Block vs Grant policies** | Block ALWAYS wins over grant in Conditional Access |
| **Azure RBAC vs Entra Roles** | Two separate systems — Global Admin ≠ Azure Owner |
| **PIM licensing** | Requires Entra ID **P2** (not P1) |
| **ID Protection** | Generates User Risk and Sign-in Risk — consumed by Conditional Access |
| **System vs User-assigned MI** | System = tied to resource lifecycle; User = independent, shareable |
| **B2B vs B2C** | B2B = partners/employees of other orgs; B2C = external customers |
| **SSPR writeback** | On-premises password writeback requires Entra ID **P1 or P2** |

### 📊 Licensing Quick Reference

| Feature | Free | P1 | P2 |
|---|---|---|---|
| Basic MFA (Security Defaults) | ✅ | ✅ | ✅ |
| Conditional Access | ❌ | ✅ | ✅ |
| SSPR (cloud only) | ❌ | ✅ | ✅ |
| SSPR + on-prem writeback | ❌ | ✅ | ✅ |
| Identity Governance (Access Reviews) | ❌ | ❌ | ✅ |
| Privileged Identity Management | ❌ | ❌ | ✅ |
| ID Protection (risk policies) | ❌ | ❌ | ✅ |

### ⚡ Common Exam Traps

- PIM requires **P2**, not P1 — the most common licensing trap
- Conditional Access is the Zero Trust enforcement mechanism for Entra ID (not a firewall)
- Legacy authentication protocols (POP3, IMAP, SMTP) **bypass** MFA and must be blocked explicitly
- Access reviews are part of **ID Governance**, not just PIM
- Entitlement Management and Access Reviews both require **Entra ID P2**

---

## 📚 Official Microsoft Learn Resources

| Resource | Link |
|---|---|
| Learning Path: Describe capabilities of Microsoft Entra | [Open](https://learn.microsoft.com/en-us/training/paths/describe-capabilities-of-microsoft-entra/) |
| Module: Describe Microsoft Entra ID | [Open](https://learn.microsoft.com/en-us/training/modules/describe-microsoft-entra-id/) |
| Module: Describe authentication capabilities | [Open](https://learn.microsoft.com/en-us/training/modules/describe-authentication-capabilities/) |
| Module: Describe access management capabilities | [Open](https://learn.microsoft.com/en-us/training/modules/describe-access-management-capabilities/) |
| Module: Describe identity protection and governance | [Open](https://learn.microsoft.com/en-us/training/modules/describe-identity-protection-governance-capabilities/) |
| What is Microsoft Entra ID? (Docs) | [Open](https://learn.microsoft.com/en-us/entra/fundamentals/whatis) |
| Conditional Access documentation | [Open](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview) |
| PIM documentation | [Open](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure) |
| SC-900 Certification Page | [Open](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/) |
| Free Practice Assessment | [Open](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/practice/assessment?assessment-type=practice&assessmentId=11) |

---

*Last updated: May 2026 · Aligned with SC-900 exam objectives (November 2025 update)*
