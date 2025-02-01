# 🔐 IAM Policies in AWS

## 🎉 Introduction  
AWS Identity and Access Management (**IAM**) policies define **who** can access **what** AWS resources **under what conditions**.  
They are **JSON-based documents** that control **permissions** for AWS services.

✅ In this guide, you will learn:  
✔️ What **IAM Policies** are  
✔️ Different **types** of IAM Policies  
✔️ Key **components** of an IAM Policy  
✔️ **Examples** of IAM Policies  

---

## 📌 1️⃣ What Are IAM Policies?  
🔹 **IAM Policies** are **rules** that specify permissions for **users, groups, and roles** in AWS.  
🔹 They define **actions** that can be performed on **AWS resources**.

📜 **Example IAM Policy (JSON Format):**  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}

## 📌 2️⃣ Types of IAM Policies
AWS supports multiple types of IAM Policies:

### 🔹 1. Managed Policies  
- **AWS Managed Policies** → Predefined by AWS for common use cases.  
- **Customer Managed Policies** → Custom-created by users for specific needs.  

🔹 **Example:** `AmazonS3ReadOnlyAccess` (AWS-managed) grants **S3 read-only access**.

---

### 🔹 2. Inline Policies  
- Embedded **directly** into a **user, group, or role**.  
- Best for **one-time permissions** or **resource-specific access**.  

🔹 **Example:** A user with **inline policy** can access only **a specific EC2 instance**.

---

### 🔹 3. Service Control Policies (SCPs)  
- Applied at **AWS Organizations** level.  
- Used to enforce permissions across **multiple AWS accounts**.  

🔹 **Example:** Prevents any IAM user in an AWS Organization from **deleting S3 buckets**.

---

### 🔹 4. Permissions Boundaries  
- Restricts the **maximum permissions** a user or role can have.  
- Enforces **least privilege access**.  

🔹 **Example:** Even if a user has an **Admin policy**, a **Permissions Boundary** can **limit** their ability to create IAM users.

---

### 🔹 5. Session Policies  
- Temporary policies assigned to users via **AWS STS (Security Token Service)**.  
- Applied when users **assume a role**.  

🔹 **Example:** A user **assumes a role** with a **temporary policy** that allows access to an S3 bucket for **1 hour**.

---

## 📌 3️⃣ Key Components of an IAM Policy  
Every IAM Policy contains **three key components**:

1️⃣ **Effect** → `Allow` or `Deny`  
2️⃣ **Action** → Specifies AWS service actions (e.g., `s3:ListBucket`)  
3️⃣ **Resource** → Specifies **ARN** (Amazon Resource Name) of AWS resources  

📜 **Example IAM Policy with Conditions:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:StartInstances",
      "Resource": "arn:aws:ec2:us-east-1:123456789012:instance/i-1234567890abcdef0",
      "Condition": {
        "StringEquals": { "aws:RequestedRegion": "us-east-1" }
      }
    }
  ]
}

# 🔐 IAM Policy Best Practices & Common Examples

## 📌 4️⃣ IAM Policy Best Practices
✔️ **Follow the Principle of Least Privilege** – Grant only the required permissions.  
✔️ **Use AWS Managed Policies** whenever possible to reduce complexity.  
✔️ **Enable IAM Access Analyzer** to detect unintended access.  
✔️ **Regularly review IAM policies** to ensure compliance and security.  
✔️ **Use IAM Policy Simulator** to test permissions before applying.  

---

## 📌 5️⃣ Common IAM Policy Examples  

### 🔹 **Admin Access Policy** (Full Access to All AWS Services)  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*"
    }
  ]
}
