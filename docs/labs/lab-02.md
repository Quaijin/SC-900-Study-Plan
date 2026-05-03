# Lab 02 — Conditional Access Policies

**Domain:** 2 — Microsoft Entra Capabilities  
**Estimated Time:** 30–45 minutes  
**Difficulty:** Beginner–Intermediate

---

## Objective

In this lab you will:

- Create a Conditional Access policy that requires MFA for all users
- Create a policy that blocks sign-ins from specific countries
- Use Report-only mode to safely test policies
- Review policy evaluation results in sign-in logs
- Explore Named Locations

---

## Prerequisites

- Microsoft 365 Developer Program sandbox tenant
- Global Administrator or Security Administrator role
- Test user account created in Lab 01
- Entra ID P1 or P2 license (included in M365 E5 developer sandbox)

---

## Steps

### Part 1 — Access Conditional Access

1. Go to [entra.microsoft.com](https://entra.microsoft.com)
2. In the left nav, go to **Protection → Conditional Access**
3. Review the **Overview** page — note any existing policies
4. Click **Policies** to see the full list

---

### Part 2 — Create a Policy: Require MFA for All Users

1. Click **+ New policy**
2. Name: `Require MFA - All Users`
3. Under **Users:**
   - Select **All users**
   - Under **Exclude**, add your Global Admin account
   
   > ⚠️ Always exclude your admin account. A misconfigured policy can lock everyone out of the tenant.

4. Under **Target resources:** select **All cloud apps**
5. Under **Conditions:** leave defaults for now
6. Under **Grant:**
   - Select **Grant access**
   - Check **Require multifactor authentication**
   - Click **Select**
7. Under **Enable policy:** set to **Report-only**
8. Click **Create**

> **Why Report-only?** Always test CA policies in Report-only mode first. It logs what would happen without actually enforcing anything — this is the safe and professional way to validate policies.

---

### Part 3 — Review Report-Only Results in Sign-in Logs

1. Sign in as your test user from Lab 01 at [office.com](https://office.com)
2. Go back to the Entra admin center → **Monitoring → Sign-in logs**
3. Find the test user sign-in and open it
4. Go to the **Conditional Access** tab
5. Find your `Require MFA - All Users` policy
6. The result should show **Report-only: Would have required MFA**

---

### Part 4 — Create a Policy: Block Sign-ins from Specific Countries

1. Go to **Conditional Access → Policies → + New policy**
2. Name: `Block - High Risk Countries`
3. Under **Users:** select **All users**
4. Under **Target resources:** select **All cloud apps**
5. Under **Conditions → Locations:**
   - Toggle **Configure** to **Yes**
   - Under **Include**, select **Selected locations**
   - Click **+ New location** → create a Countries location
   - Select the location you created
6. Under **Grant:** select **Block access**
7. Set policy to **Report-only**
8. Click **Create**

---

### Part 5 — Explore Named Locations

1. In Conditional Access, go to **Named locations**
2. Review the two types:
   - **Countries location** — define by country/region
   - **IP ranges location** — define trusted corporate IP ranges
3. Note that IP ranges marked as **trusted** are treated differently — users from trusted locations may bypass certain policy conditions

> **Exam tip:** Named locations serve two purposes — trusting known office IPs to reduce friction, and blocking high-risk countries to reduce attack surface.

---

### Part 6 — Enable the MFA Policy (Optional)

If you want to experience full enforcement:

1. Open `Require MFA - All Users`
2. Change **Enable policy** from **Report-only** to **On**
3. Click **Save**
4. Open a private browser window and sign in as the test user
5. You will be prompted to register for MFA and then verify

> ⚠️ Make sure your Global Admin account is excluded before enabling. If you get locked out, you'll need a break-glass account or Microsoft support.

---

## What I Observed

> ✏️ *Add your own notes, screenshots, and observations here as you complete the lab.*

---

## Key Takeaways for the Exam

- Conditional Access = Zero Trust policy engine: **If [signals] Then [grant/block]**
- Always use **Report-only** mode before enabling a policy
- Signals include: user, group, location, device, application, sign-in risk
- Named locations = trusted IPs or blocked countries
- Conditional Access requires **Entra ID P1** minimum
- Always exclude break-glass admin accounts from blocking policies
- Block policies take precedence over grant policies
