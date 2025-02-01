# 🔎 AWS IAM Access Analyzer

## 🎯 Introduction  
AWS **IAM Access Analyzer** helps identify and **analyze resource access policies** to detect **unintended public access** or **cross-account sharing** of AWS resources.

✅ **In this guide, you will learn:**  
✔️ What **IAM Access Analyzer** is  
✔️ How it **works**  
✔️ **How to enable and use it**  
✔️ **Best practices** for securing AWS resources  

---

## 📌 1️⃣ What is IAM Access Analyzer?  
IAM Access Analyzer is an **AWS security tool** that continuously **monitors and analyzes IAM policies** to detect unintended access.

✔️ **Identifies public access risks**  
✔️ **Finds cross-account access issues**  
✔️ **Works with AWS Organizations** to manage security at scale  
✔️ **Supports multiple AWS resources**  

---

## 📌 2️⃣ How Does IAM Access Analyzer Work?  
1️⃣ **Creates an Analyzer** to scan AWS policies  
2️⃣ **Evaluates IAM roles, S3 buckets, KMS keys, Lambda functions, and SQS queues**  
3️⃣ **Generates findings** if resources are publicly accessible or shared  
4️⃣ **Provides actionable recommendations** to secure access  

📜 **Example: IAM Access Analyzer Detecting Public S3 Bucket**
```json
{
  "analyzedAt": "2025-01-30T12:34:56Z",
  "findingType": "Public",
  "resource": "arn:aws:s3:::my-public-bucket",
  "status": "Active",
  "createdAt": "2025-01-30T12:30:00Z"
}
```
✅ **This finding indicates that `my-public-bucket` is publicly accessible.**

---

## 📌 3️⃣ AWS Resources Analyzed by IAM Access Analyzer  
IAM Access Analyzer scans the following AWS services:

🔹 **IAM Roles** – Detects roles shared with external AWS accounts  
🔹 **S3 Buckets** – Identifies publicly accessible storage  
🔹 **KMS Keys** – Analyzes encryption key sharing  
🔹 **Lambda Functions** – Checks execution permissions  
🔹 **SQS Queues** – Detects unauthorized queue access  

---

## 📌 4️⃣ How to Enable IAM Access Analyzer  

### **✔️ Using AWS Management Console**  
1️⃣ Open **AWS IAM Console**  
2️⃣ Navigate to **Access Analyzer**  
3️⃣ Click **Create Analyzer**  
4️⃣ Select **Type: Account or Organization**  
5️⃣ Click **Create**  

✅ IAM Access Analyzer is now **enabled** and will start monitoring resources.

---

### **✔️ Using AWS CLI**  
Run the following command to create an IAM Access Analyzer:  
```sh
aws accessanalyzer create-analyzer --analyzer-name my-access-analyzer --type ACCOUNT
```
✅ **This enables IAM Access Analyzer for your AWS account.**

---

## 📌 5️⃣ Viewing Findings from IAM Access Analyzer  

### **✔️ Using AWS Console**  
1️⃣ Go to **AWS IAM Console** → **Access Analyzer**  
2️⃣ Click **Findings**  
3️⃣ View **publicly exposed resources**  

### **✔️ Using AWS CLI**  
Run the following command to list IAM Access Analyzer findings:  
```sh
aws accessanalyzer list-findings --analyzer-name my-access-analyzer
```
✅ **Findings show potential security risks in AWS policies.**

---

## 📌 6️⃣ Responding to IAM Access Analyzer Findings  

### **✔️ Reviewing Findings**
- Findings can be **Public, Cross-Account, or External Access**  
- Identify the **affected AWS resource**  
- Check the **policy statement granting access**  

### **✔️ Resolving Public Access Issues**
If a resource is **publicly accessible**, modify its policy:

📜 **Example: Block Public Access to an S3 Bucket**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "s3:*",
      "Principal": "*",
      "Resource": [
        "arn:aws:s3:::my-public-bucket",
        "arn:aws:s3:::my-public-bucket/*"
      ]
    }
  ]
}
```
✅ **This policy denies public access to `my-public-bucket`.**

---

## 📌 7️⃣ Best Practices for Using IAM Access Analyzer  

✔️ **Enable IAM Access Analyzer for all AWS accounts**  
✔️ **Regularly review and resolve findings**  
✔️ **Use AWS Organizations for centralized security**  
✔️ **Restrict public access to S3 buckets, IAM roles, and KMS keys**  
✔️ **Use IAM Conditions to limit access**  

---

## 📌 8️⃣ Summary  

🔹 **IAM Access Analyzer** detects unintended **public access or cross-account sharing**  
🔹 Supports AWS services like **IAM Roles, S3 Buckets, Lambda, and KMS Keys**  
🔹 Findings help identify **security misconfigurations**  
🔹 Use **AWS CLI or AWS Console** to view and fix security risks  
🔹 **Enforce best practices** to **secure AWS environments**  
