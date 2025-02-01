
# 🔐 IAM Policies in AWS

## 🎉 Introduction  
In the last session, we covered **IAM users, groups, and roles**.  
We briefly discussed **IAM policies** to grant permissions, but **understanding policies in-depth is crucial** for effectively managing IAM.

In this lesson, we will dive deeper into IAM policies, their **types, structure, and use cases**.

---

## 📌 1️⃣ What Are IAM Policies?  
IAM policies are **permissions rules** that control **who** can perform **what actions** on **which AWS resources**.  

🔹 **Definition**: IAM policy is an entity that, when attached to an **identity or resource**, defines **its permissions**.  
🔹 **Permissions** determine whether a request is **allowed or denied**.  
🔹 **IAM Policies** are written in **JSON format**.

---

## 📌 2️⃣ Understanding IAM Policies with an Example  

Imagine you have a **team** of two developers (**Ram & Shyam**) and two administrators (**Sita & Gita**).  

You create two IAM **groups**:  
- **Developers** → Can **list, start, and stop EC2 instances**.  
- **Administrators** → Can **create and delete EC2 instances**.  

You create two **policies**:  
1️⃣ **Developer Policy** – Allows `List`, `Start`, `Stop` EC2.  
2️⃣ **Administrator Policy** – Allows `Create`, `Delete` EC2.  

📜 By **attaching policies to IAM groups**, all members of the group inherit the permissions:  
✅ **Ram & Shyam** (Developers) → Can only **List, Start, Stop EC2**.  
✅ **Sita & Gita** (Administrators) → Can **Create & Delete EC2**.

This shows **how IAM policies control access at the group level**.

---

## 📌 3️⃣ Types of IAM Policies  

IAM policies can be attached to:  
✅ **Identities** (Users, Groups, Roles) → **Identity-Based Policies**  
✅ **AWS Resources** (EC2, S3, Lambda, etc.) → **Resource-Based Policies**  

### **1️⃣ Identity-Based Policies**  
Identity-based policies define **what actions an IAM identity (user, group, or role) can perform on AWS resources**.  
They are user-specific and only allow access to AWS resources **within the same AWS account**.

📜 **Example: Identity-Based Policy for EC2**  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:RunInstances",
      "Resource": "*"
    }
  ]
}
```
✅ This policy allows **Ram** to **launch EC2 instances**.  
✅ Can also **define permissions for S3, Lambda, etc.**  

---

### **2️⃣ Resource-Based Policies**  
Resource-based policies define **who can access an AWS resource and what actions they can perform**.  
These policies **attach directly to AWS resources** like **S3 buckets, EC2 instances, etc.**  

📜 **Example: Resource-Based Policy for S3**  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::123456789012:user/Ram"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}
```
✅ This allows **Ram** to **read objects from S3 bucket `my-bucket`**.

---

## 📌 4️⃣ Types of Identity-Based Policies  

### 🔹 **Managed Policies**  
AWS provides two types of managed policies:  
1️⃣ **AWS Managed Policies** – Predefined by AWS (ReadOnlyAccess, AdministratorAccess).  
2️⃣ **Customer Managed Policies** – Created and managed by AWS customers.  

✅ **AWS Managed Policies**: Cannot be modified by customers.  
✅ **Customer Managed Policies**: Fully customizable, easier to reuse across multiple IAM entities.  

📜 **Example: AWS-Managed Policy – AmazonS3ReadOnlyAccess**  
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
      "Resource": "*"
    }
  ]
}
```
✅ This AWS **predefined policy** grants **read-only access** to all S3 buckets.  

---

### 🔹 **Inline Policies**  
- **Embedded directly** into a **user, group, or role**.  
- **Strictly 1:1** relationship (policy exists only for that entity).  
- **Deleted when the user/group/role is deleted**.  
- **Useful for temporary access needs**.  

📜 **Example: Inline Policy for EC2 Start/Stop**  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:StartInstances",
        "ec2:StopInstances"
      ],
      "Resource": "arn:aws:ec2:us-east-1:123456789012:instance/*"
    }
  ]
}
```
✅ This **inline policy** allows **only Start/Stop EC2** for **one IAM user**.

---

## 📌 5️⃣ Key Differences Between IAM Policies  

| Policy Type          | Applied To | Use Case |
|----------------------|-----------|----------|
| **Identity-Based**  | IAM Users, Groups, Roles | Controls what an IAM entity can do |
| **Resource-Based**  | AWS Resources (S3, EC2) | Controls who can access the resource |
| **AWS Managed**     | Predefined by AWS | Simplifies policy management |
| **Customer Managed** | Created by users | Allows full customization |
| **Inline**          | Single entity only | Best for temporary access |

---

## 📌 6️⃣ Summary  

🔹 **IAM Policies define permissions** in AWS.  
🔹 **Two main types**: **Identity-Based Policies** (for IAM users/groups) and **Resource-Based Policies** (for AWS resources).  
🔹 **IAM Policies** control **who can perform what actions** on **which AWS resources**.  
🔹 **Managed Policies (AWS & Customer)** allow **policy reuse**.  
🔹 **Inline Policies** apply to **one specific entity** and are deleted when the entity is deleted.  
