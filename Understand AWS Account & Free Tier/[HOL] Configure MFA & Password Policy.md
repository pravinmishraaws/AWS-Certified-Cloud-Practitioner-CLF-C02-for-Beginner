
# 🔒 [HOL] Configure MFA & Password Policy in AWS

## 🎉 Introduction
Securing your AWS account is **crucial** to prevent unauthorized access.  
This **Hands-On Lab (HOL)** will guide you through:

✅ **Enabling Multi-Factor Authentication (MFA)** for your Root & IAM users.  
✅ **Configuring a Strong Password Policy** for IAM users.  

---

## 📌 1️⃣ Enable Multi-Factor Authentication (MFA)
### 🔹 Why is MFA Important?
- Protects your **AWS Root & IAM accounts** from unauthorized access.
- Adds an **extra security layer** beyond a password.

### ✅ **Steps to Enable MFA for Root User**
1. **Log in** to AWS **as Root User**.
2. Open the **IAM (Identity & Access Management) Console**.
3. Click on **Users** and select your **Root Account**.
4. Under **Security credentials**, click **Enable MFA**.
5. Select **Virtual MFA Device** and click **Continue**.
6. Open an **MFA App** (Google Authenticator, Microsoft Authenticator).
7. **Scan the QR Code** with the app.
8. Enter the **two MFA codes** shown in the app.
9. Click **Enable MFA**.

📌 **Result:** Root account now requires an MFA code on login.

---

### ✅ **Steps to Enable MFA for IAM Users**
1. Navigate to **IAM Console → Users**.
2. Select the **IAM User** who needs MFA.
3. Under **Security credentials**, click **Manage MFA**.
4. Choose **Virtual MFA Device** and scan the **QR Code**.
5. Enter the **two MFA codes** shown in the app.
6. Click **Enable MFA**.

📌 **Best Practice:**  
✔️ **Enforce MFA** for all IAM users via an **IAM Policy**.

---

## 📌 2️⃣ Configure a Strong Password Policy
### 🔹 Why Set a Password Policy?
- Ensures users use **strong, hard-to-guess passwords**.
- **Reduces security risks** like brute-force attacks.

### ✅ **Steps to Configure Password Policy**
1. Open the **IAM Console**.
2. Navigate to **Account Settings**.
3. Under **Password Policy**, click **Edit**.
4. **Enable the following settings**:
   ✅ Require **minimum 12-character password**.  
   ✅ Require **uppercase & lowercase letters**.  
   ✅ Require **numbers & symbols**.  
   ✅ Enable **password expiration** (e.g., **90 days**).  
   ✅ Prevent **password reuse** (e.g., last 3 passwords).  
5. Click **Save Changes**.

📌 **Result:** IAM users must follow this policy for all new passwords.

---

## 🎯 Conclusion
✅ **MFA is enabled** for Root & IAM users, adding extra security.  
✅ **Password policy ensures strong passwords** to prevent breaches.  
✅ **IAM security best practices** help protect AWS accounts.  

