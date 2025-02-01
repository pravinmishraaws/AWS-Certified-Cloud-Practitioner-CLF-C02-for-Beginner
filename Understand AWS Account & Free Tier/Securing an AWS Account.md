# 🔒 Securing Your AWS Account: MFA, Access Keys & Password Policy

## 🎉 Introduction
Before creating AWS resources, it's **critical** to secure your AWS account.  
This guide covers:

✅ **Multi-Factor Authentication (MFA)**  
✅ **Access & Secret Keys** (Programmatic Access)  
✅ **AWS Password Policy**  

These measures help prevent **unauthorized access, data breaches, and security risks**.

---

## 📌 1️⃣ Enable Multi-Factor Authentication (MFA)
### 🔹 What is MFA?
MFA adds an **extra layer of security** beyond a password by requiring a second factor, such as:
✅ **Authenticator App** (Google/Microsoft Authenticator)  
✅ **SMS/Email OTP**  
✅ **Security Token Devices**  

### 🔹 Why is MFA Important?
- Even if someone steals your password, they **cannot** log in without the MFA code.  
- **Prevents unauthorized access** and protects **critical resources**.  

### ✅ **Steps to Enable MFA for Root & IAM Users**
1. **Sign in** to AWS **as Root User**.
2. Navigate to **IAM (Identity & Access Management)**.
3. Go to **Users → Your Root User → Enable MFA**.
4. Select **Virtual MFA Device** (Authenticator App).
5. Scan the **QR Code** and enter the **verification codes**.
6. Click **Enable MFA**.

📌 **Best Practice:** Enforce **MFA for all IAM users** using an IAM policy.

---

## 📌 2️⃣ Secure AWS Access & Secret Keys
### 🔹 What Are Access & Secret Keys?
AWS **Access Keys** allow **programmatic access** to AWS services via:
- **AWS CLI (Command Line Interface)**
- **AWS SDKs (Software Development Kits)**
- **Automation Scripts**

### 🔹 Why Are Access Keys a Security Risk?
- **Keys are equivalent to passwords**—exposing them can lead to **unauthorized access**.
- Attackers can use stolen keys to **create resources, delete data, and incur huge AWS bills**.

### ✅ **Best Practices for Protecting Access Keys**
✅ **Do NOT use Root Account keys** – Always use IAM roles.  
✅ **Rotate keys regularly** – Reduce the risk of compromised keys.  
✅ **Never hardcode keys** – Use **AWS Secrets Manager** or environment variables.  
✅ **Scan repositories for exposed keys** – Use tools like **AWS IAM Access Analyzer**.  

📌 **Example of a Security Breach:**  
Many users **accidentally commit AWS keys** to GitHub.  
AWS **automatically scans** public repositories and **revokes compromised keys**.

---

## 📌 3️⃣ Implement a Strong Password Policy
### 🔹 Why Do You Need a Password Policy?
A **strong password policy** prevents weak passwords that can be easily guessed or cracked.

### ✅ **Best Practices for Password Policy**
🔹 **Set a minimum password length** (e.g., 12 characters).  
🔹 **Require uppercase, lowercase, numbers, and symbols**.  
🔹 **Enable password expiration** (e.g., every 90 days).  
🔹 **Prevent password reuse** (e.g., last 3 passwords).  
🔹 **Allow only Admins to reset passwords** for better control.  

### 🔹 How Quickly Can a Password Be Cracked?
| Password Type | Cracking Time |
|--------------|--------------|
| 6-digit numbers only | **Instantly** |
| 6 characters (lowercase) | **2 minutes** |
| 8 characters (mixed case) | **8 months** |
| 12 characters (symbols + mixed case) | **38 million years** 🚀 |

📌 **Best Practice:** Enforce strong password policies via **IAM settings**.

---

## 🎯 Conclusion
🔹 **Enforce MFA** for all users to prevent unauthorized access.  
🔹 **Use IAM roles instead of access keys** to reduce security risks.  
🔹 **Implement a strong password policy** to prevent brute-force attacks.  
🔹 **Regularly audit AWS accounts** for security best practices.  

🚀 **Next Steps:**  
👉 **[HOL] Configure MFA & IAM Best Practices**  
👉 **[HOL] Set Up AWS Budgets for Cost Monitoring**
