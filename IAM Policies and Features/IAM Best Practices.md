# 🔐 AWS IAM Best Practices

## 🎯 Introduction  
AWS Identity and Access Management (**IAM**) is **critical** for securing AWS resources.  
Following **best practices** helps prevent **unauthorized access, security risks, and compliance issues**.

✅ **In this guide, you will learn:**  
✔️ Key **IAM security best practices**  
✔️ How to implement **least privilege access**  
✔️ Common **security misconfigurations to avoid**  

---

## 📌 1️⃣ Enable Multi-Factor Authentication (MFA)  
✔️ **MFA adds an extra layer of security** by requiring a second authentication factor.  
✔️ **Enable MFA for root users and IAM users** with console access.  
✔️ Use **MFA device** (Google Authenticator, AWS MFA) for additional protection.  

📜 **Example: Enforce MFA for IAM users**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "BoolIfExists": {
          "aws:MultiFactorAuthPresent": "false"
        }
      }
    }
  ]
}
```
✅ **This policy denies all actions unless MFA is enabled.**

---

## 📌 2️⃣ Follow the Principle of Least Privilege  
✔️ **Grant only the permissions required for a task** – no excessive access.  
✔️ Use **IAM roles** instead of long-term access keys.  
✔️ **Review IAM permissions regularly** to ensure minimal access.  

📜 **Example: Restrict S3 Access to Read-Only**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::example-bucket/*"
    }
  ]
}
```
✅ **This ensures users can read objects but not delete them.**

---

## 📌 3️⃣ Use IAM Roles for Applications and Services  
✔️ **Avoid using long-term access keys for AWS applications.**  
✔️ **Assign IAM roles to EC2, Lambda, and ECS tasks** to manage permissions securely.  

📜 **Example: Allow EC2 to Access S3**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}
```
✅ **IAM roles eliminate the need for hardcoded credentials.**

---

## 📌 4️⃣ Secure IAM Access Keys  
✔️ **Avoid using IAM user access keys unless necessary.**  
✔️ **Use AWS CLI and SDKs with IAM roles instead.**  
✔️ **Rotate access keys regularly** and use AWS Secrets Manager for key storage.  

📜 **How to Detect and Rotate Exposed Keys:**  
- **Use AWS IAM Access Analyzer** to detect **publicly exposed credentials**.  
- **Use AWS Security Hub** to identify **at-risk IAM credentials**.  
- **Rotate keys using AWS CLI**:  
  ```sh
  aws iam update-access-key --access-key-id <key-id> --status Inactive
  aws iam create-access-key --user-name <user-name>
  ```

✅ **Regular rotation and monitoring reduce the risk of key leakage.**

---

## 📌 5️⃣ Enforce Strong Password Policies  
✔️ Require **complex passwords** (uppercase, lowercase, numbers, special characters).  
✔️ Enforce **password expiration and rotation** every 90 days.  
✔️ **Prevent password reuse** to enhance security.  

📜 **Example: Enforce Strong Password Policy**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "iam:UpdateAccountPasswordPolicy",
      "Resource": "*"
    }
  ]
}
```
✅ **This ensures IAM users follow strong password rules.**

---

## 📌 6️⃣ Use IAM Policies Instead of Inline Policies  
✔️ **Prefer Managed Policies** to improve security and reduce complexity.  
✔️ **Inline policies are attached directly** to users and **are difficult to track**.  
✔️ **Use IAM Access Analyzer** to identify excessive permissions.  

✅ **AWS Managed Policies** offer pre-built, best-practice security controls.  

---

## 📌 7️⃣ Enable AWS IAM Access Analyzer  
✔️ Detects **publicly accessible resources**.  
✔️ Identifies **unintended access from external AWS accounts**.  
✔️ Monitors IAM policies **for excessive permissions**.  

📜 **How to Enable IAM Access Analyzer via CLI**
```sh
aws accessanalyzer create-analyzer --analyzer-name my-access-analyzer --type ACCOUNT
```
✅ **IAM Access Analyzer helps prevent security misconfigurations.**

---

## 📌 8️⃣ Regularly Audit IAM Users and Permissions  
✔️ Use **AWS IAM Credential Report** to review user activity.  
✔️ **Delete unused IAM users and roles** regularly.  
✔️ Implement **AWS CloudTrail** for monitoring user activity.  

📜 **Generate IAM Credential Report (CLI)**
```sh
aws iam generate-credential-report
aws iam get-credential-report
```
✅ **Regular audits ensure IAM security and compliance.**

---

## 📌 9️⃣ Restrict Root Account Usage  
✔️ **Do not use the root account for daily tasks.**  
✔️ **Create IAM administrators** instead of using the root user.  
✔️ **Enable MFA on the root user account.**  

📜 **Example: Deny Root User from Performing Actions**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "aws:PrincipalArn": "arn:aws:iam::123456789012:root"
        }
      }
    }
  ]
}
```
✅ **This prevents accidental changes using the root account.**

---

## 📌 🔟 Summary  
✔️ **Enable MFA** for root and IAM users.  
✔️ **Follow Least Privilege Access** – grant only necessary permissions.  
✔️ **Use IAM roles instead of access keys** for applications.  
✔️ **Regularly audit IAM users and permissions.**  
✔️ **Enforce strong password policies and avoid inline policies.**  
✔️ **Enable AWS IAM Access Analyzer for security insights.**  
