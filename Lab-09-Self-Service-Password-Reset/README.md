# Lab 09 – Self-Service Password Reset (SSPR)

## Overview

Configured and tested **Self-Service Password Reset (SSPR)** in Microsoft Entra ID using a security group for a controlled rollout.

**Skills:** Entra ID • SSPR • MFA • Microsoft Authenticator • Security Groups • IAM

---

## 1. Created SSPR Test Group

Created the **SSPRTesters** security group and assigned three test users.

![SSPR Group Configuration](images/01-SSPRTesters-Group-Configuration.png)

![SSPR Group Members](images/02-SSPRTesters-Group-Members.png)

---

## 2. Enabled SSPR

Enabled SSPR specifically for the **SSPRTesters** group instead of the entire organization.

![SSPR Enabled](images/03-SSPR-Enabled-Selected-Group.png)

---

## 3. Verified Authentication Methods

The current Entra UI manages authentication methods through the **Authentication Methods Policy**. I verified that **Microsoft Authenticator** was enabled and used it for SSPR verification.

![Authentication Methods](images/04-SSPR-Authentication-Methods.png)

The test user already had Microsoft Authenticator registered, so I verified the existing method instead of performing duplicate enrollment.

![User Authentication Method](images/05-SSPR-Test-User-Authentication-Method.png)

---

## 4. Tested SSPR

Initiated **Forgot my password** as an SSPR-enabled user.

![SSPR Initiated](images/06-SSPR-Password-Reset-Initiated.png)

Completed identity verification and reached the password-reset stage.

![Identity Verified](images/07-SSPR-Identity-Verified-New-Password.png)

Successfully completed the password reset.

![Password Reset Successful](images/08-SSPR-Password-Reset-Success.png)

---

## 5. Tested Access Control

Tested SSPR with a user **outside the SSPRTesters group**. Microsoft correctly denied self-service password reset.

![SSPR Access Denied](images/09-SSPR-NonMember-Access-Denied.png)

---

## Key Takeaways

* Deployed SSPR to a controlled security group.
* Used Microsoft Authenticator for identity verification.
* Adapted the lab to Microsoft's current Entra UI.
* Verified both **successful and denied** SSPR scenarios.
* Demonstrated how SSPR can reduce help-desk password-reset workload while maintaining access controls.

---

## Status

**Lab Completed ✅**
