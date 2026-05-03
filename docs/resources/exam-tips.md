# Exam Tips & Strategy

Practical advice for passing the SC-900 on your first attempt.

---

## About the Exam

| Detail | Info |
|---|---|
| **Questions** | 40–60 questions |
| **Duration** | 45 minutes |
| **Passing score** | 700 / 1000 |
| **Question types** | Multiple choice, multi-select, drag-and-drop, case studies |
| **Delivered by** | Pearson VUE (in-person or online proctored) |

> You don't need to score 100% — 700/1000 is roughly 70%. Don't panic if you're unsure about some questions.

---

## Domain Priority

Study in this order based on exam weight:

| Priority | Domain | Weight |
|---|---|---|
| 1st | Domain 3 — Microsoft Security Solutions | 35–40% |
| 2nd | Domain 2 — Microsoft Entra Capabilities | 25–30% |
| 3rd | Domain 4 — Microsoft Compliance Solutions | 20–25% |
| 4th | Domain 1 — Security, Compliance & Identity Concepts | 10–15% |

> **Domain 3 alone is worth up to 40% of the exam.** Know Sentinel, Defender XDR products, and Azure security services well.

---

## What the Exam Actually Tests

The SC-900 is a **conceptual** exam — it does not test you on how to click through portals. It tests:

- **What each product does** — and what problem it solves
- **Where each product fits** — which domain, which threat, which use case
- **Key terminology** — Zero Trust, SIEM, CSPM, DLP, eDiscovery, etc.
- **Differences between similar products** — e.g., Sentinel vs Defender for Cloud

---

## High-Value Topics to Master

### Domain 1
- Zero Trust three principles: Verify explicitly, Use least privilege, Assume breach
- Defense-in-depth 7 layers — know the order
- Authentication vs Authorization
- Encryption vs Hashing — encryption is reversible, hashing is not
- Shared responsibility model — customer always owns data and identity

### Domain 2
- Entra ID vs on-prem AD DS — key differences
- MFA factors: something you know / have / are
- Passwordless options: Windows Hello, Authenticator App, FIDO2
- Conditional Access signals and controls
- PIM = just-in-time access (requires P2)
- Entra ID Protection = ML risk detection (requires P2)
- SSPR = users reset their own passwords

### Domain 3
- **Map every Defender product to what it protects:**
  - Endpoint → devices
  - Office 365 → email, Teams, SharePoint
  - Identity → on-prem AD DS
  - Cloud Apps → SaaS / shadow IT
- Sentinel = SIEM + SOAR (not the same as Defender for Cloud)
- Defender for Cloud = CSPM + CWPP
- Secure Score = posture measurement in Defender for Cloud
- Azure Bastion = secure RDP/SSH without public IPs
- Azure Key Vault = secrets, keys, certificates
- WAF vs Azure Firewall — layer difference

### Domain 4
- Service Trust Portal = Microsoft's compliance (external audit reports)
- Compliance Manager = your organization's compliance score
- Sensitivity labels travel with content and enforce protection
- DLP = prevents sharing of sensitive data
- Retention policy = broad; Retention label = per item
- Audit Standard = 90 days; Audit Premium = up to 1 year
- Insider Risk Management = monitors internal user behavior

---

## Common Exam Traps

**1. Sentinel vs Defender for Cloud**
These are often confused. Remember:
- Sentinel = SIEM/SOAR — collects logs, detects threats, automates response
- Defender for Cloud = CSPM/CWPP — posture management and workload protection

**2. Entra ID P1 vs P2**
- P1 = Conditional Access
- P2 = PIM + Identity Protection

**3. Authentication vs Authorization**
- AuthN = who you are (identity verification)
- AuthZ = what you can do (permissions)

**4. Encryption vs Hashing**
- Encryption = reversible with a key
- Hashing = one-way, cannot be reversed

**5. Service Trust Portal vs Compliance Manager**
- STP = Microsoft proves its compliance to you
- Compliance Manager = you track your own compliance

**6. Retention Policy vs Retention Label**
- Policy = applied broadly to locations (mailboxes, sites)
- Label = applied to specific items, can declare records

---

## Exam Day Tips

- **Read every question twice** — SC-900 questions often hinge on one word (e.g., "which service *prevents*" vs "which service *detects*")
- **Eliminate wrong answers first** — narrow down to two, then decide
- **Flag and return** — if unsure, flag the question and come back
- **Don't overthink** — this is a fundamentals exam, answers are rarely tricky
- **Watch for absolutes** — words like "always", "never", "only" are often wrong
- **Time management** — 45 minutes for ~50 questions = ~54 seconds per question. Don't spend too long on any one question.

---

## Recommended Study Schedule

| Week | Focus |
|---|---|
| Week 1 | Domain 1 + Domain 2 study notes + Microsoft Learn paths |
| Week 2 | Domain 3 + Domain 4 study notes + Microsoft Learn paths |
| Week 3 | Labs 01 and 02, practice questions per domain |
| Week 4 | Full practice assessment, review weak areas, exam day |

> The Microsoft Learn free practice assessment is the closest thing to the real exam. Do it at the end of Week 3 and use your score to guide Week 4 review.

---

## On Exam Day

1. Get a good night's sleep
2. If taking online — test your webcam, mic, and internet connection beforehand
3. Have your ID ready (government-issued photo ID)
4. Clear your desk if taking online proctored
5. You can take notes on the provided whiteboard during the exam
6. If you fail — you can retake after 24 hours. Review the score report to identify weak domains.
