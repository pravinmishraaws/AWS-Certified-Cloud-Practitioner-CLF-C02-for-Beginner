# 🔐 IAM Policy Examples

## 🎉 Introduction  
IAM policies control **who** can access **what** AWS resources.  
In this guide, we will cover **common IAM policy examples** for different AWS services.

---

## 📌 1️⃣ Full Administrator Access  
✅ Grants **full access** to all AWS services and resources.  
❗ **Use with caution!** This policy allows unrestricted access.

📜 **Example: Full Admin Access**
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
```
---

## 📌 2️⃣ Read-Only Access to AWS Services  
✅ Allows **read-only access** to all AWS services.  
🔹 Users can **view** but **not modify** AWS resources.

📜 **Example: Read-Only Access**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "aws:RequestedRegion": "us-east-1"
        }
      }
    }
  ]
}
```
---

## 📌 3️⃣ Read-Only Access to Amazon S3  
✅ Allows **read-only access** to a specific S3 bucket.  
🔹 Users can **list and get objects** but **cannot upload or delete**.

📜 **Example: S3 Read-Only Access**
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
      "Resource": [
        "arn:aws:s3:::example-bucket",
        "arn:aws:s3:::example-bucket/*"
      ]
    }
  ]
}
```
---

## 📌 4️⃣ Restrict EC2 Access to Specific Instances  
✅ Allows users to **start and stop** only **one EC2 instance**.  

📜 **Example: EC2 Restricted Access**
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
      "Resource": "arn:aws:ec2:us-east-1:123456789012:instance/i-1234567890abcdef0"
    }
  ]
}
```
---

## 📌 5️⃣ Deny S3 Bucket Deletion (Explicit Deny Policy)  
✅ Explicitly **denies** S3 bucket deletion.  
❗ **Deny policies always override Allow policies**.

📜 **Example: Deny S3 Deletion**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "s3:DeleteBucket",
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}
```
---

## 📌 6️⃣ Allow Lambda Execution Only  
✅ Allows users to **invoke** a Lambda function but **not modify it**.

📜 **Example: Lambda Invoke Only**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "lambda:InvokeFunction",
      "Resource": "arn:aws:lambda:us-east-1:123456789012:function:my-lambda-function"
    }
  ]
}
```
---

## 📌 7️⃣ Allow RDS Database Access  
✅ Grants **read and write** access to **one RDS database**.

📜 **Example: RDS Access Policy**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "rds:DescribeDBInstances",
        "rds:ModifyDBInstance",
        "rds:RebootDBInstance"
      ],
      "Resource": "arn:aws:rds:us-east-1:123456789012:db:mydbinstance"
    }
  ]
}
```
---

## 📌 8️⃣ Grant IAM User Password Change  
✅ Allows IAM users to **change their own password**.  

📜 **Example: IAM Change Password**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "iam:ChangePassword",
      "Resource": "arn:aws:iam::123456789012:user/${aws:username}"
    }
  ]
}
```
---

## 📌 9️⃣ Restrict Access to AWS Based on IP Address  
✅ Allows access to AWS **only from a specific IP range**.  
❗ **Useful for security policies!**

📜 **Example: Restrict AWS Access by IP**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "NotIpAddress": {
          "aws:SourceIp": "192.168.1.0/24"
        }
      }
    }
  ]
}
```
---

## 📌 🔟 Summary  

### ✅ Key Takeaways:  
✔️ **IAM Policies** define **who can access what AWS resources**.  
✔️ **Use the principle of least privilege** – Grant only the necessary permissions.  
✔️ **Explicit Deny policies override Allow policies**.  
✔️ **Test IAM policies using IAM Policy Simulator** before applying them.  

