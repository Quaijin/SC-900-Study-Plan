# Lab 01 — Explore Microsoft Entra ID

**Domain:** 2 — Microsoft Entra Capabilities  
**Estimated Time:** 30–45 minutes  
**Difficulty:** Beginner

---

## Objective

In this lab you will:

- Navigate the Microsoft Entra admin center
- Create a user account
- Create a security group and add members
- Review sign-in logs
- Configure Self-Service Password Reset (SSPR)
- Review MFA registration options

---

## Prerequisites

- A Microsoft 365 Developer Program sandbox tenant (free)
- Global Administrator access to the tenant
- A browser — Microsoft Edge recommended

> **Free tenant:** Sign up at [developer.microsoft.com/microsoft-365/dev-program](https://developer.microsoft.com/microsoft-365/dev-program). This gives you a free 90-day M365 E5 sandbox with Entra ID P2 included — renewable as long as you use it actively.

---

## Steps

### Part 1 — Access the Entra Admin Center

1. Open a browser and go to [entra.microsoft.com](https://entra.microsoft.com)
2. Sign in with your Global Administrator account
3. On the left navigation, explore the main sections:
   - **Identity** — Users, Groups, External Identities
   - **Protection** — Conditional Access, Identity Protection, MFA
   - **Governance** — Entitlement Management, Access Reviews, PIM

---

### Part 2 — Create a New User

1. Go to **Identity → Users → All users**
2. Click **+ New user → Create new user**
3. Fill in:
   - **User principal name:** `testuser01@yourdomain.onmicrosoft.com`
   - **Display name:** `Test User 01`
   - **Password:** Auto-generate or set manually
4. Under **Assignments**, leave role as User for now
5. Click **Review + create**, then **Create**
6. Verify the user appears in the All users list

---

### Part 3 — Create a Security Group

1. Go to **Identity → Groups → All groups**
2. Click **+ New group**
3. Fill in:
   - **Group type:** Security
   - **Group name:** `SC-900-Lab-Group`
   - **Membership type:** Assigned
4. Under **Members**, add `Test User 01`
5. Click **Create**
6. Open the group and verify the member was added

---

### Part 4 — Review Sign-in Logs

1. Go to **Identity → Monitoring & health → Sign-in logs**
2. Browse recent sign-in events
3. Click on any sign-in entry and inspect:
   - **Basic info** — User, application, date/time, IP address
   - **Location** — Country, city
   - **Device info** — OS, browser, compliant status
   - **Authentication details** — Methods used, MFA result
   - **Conditional Access** — Which policies applied and their result

> **Note:** Sign-in logs are critical for investigating suspicious access. This data is heavily referenced in Domain 2 exam questions.

---

### Part 5 — Configure Self-Service Password Reset (SSPR)

1. Go to **Protection → Password reset**
2. Under **Properties**, set SSPR to **Selected** and choose `SC-900-Lab-Group`
3. Go to **Authentication methods**:
   - Set **Number of methods required to reset:** 1
   - Enable **Email** and **Mobile phone**
4. Go to **Registration** and enable **Require users to register when signing in**
5. Click **Save**

---

### Part 6 — Review MFA Settings

1. Go to **Protection → Multifactor authentication**
2. Explore **Getting started** — review Fraud Alert and One-time bypass options
3. Review available verification methods:
   - Microsoft Authenticator app
   - SMS / Voice call
   - OATH tokens

> **Note:** Per-user MFA settings here are considered legacy. The modern approach is enforcing MFA through Conditional Access policies — covered in Lab 02.

---

## What I Observed

> ✏️ *Add your own notes, screenshots, and observations here as you complete the lab.*

---

## Key Takeaways for the Exam

- The Entra admin center is the primary tool for managing identity in Microsoft 365
- Sign-in logs capture: location, device, IP, authentication method, and CA policy results
- SSPR requires users to pre-register at least one verification method
- Security groups vs Microsoft 365 groups — know the difference
- MFA enforcement via Conditional Access is preferred over per-user MFA settings

---

## Next Lab

➡️ [Lab 02 — Conditional Access Policies](lab-02.md)
