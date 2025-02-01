# 📦 Amazon S3 (Simple Storage Service) Overview

## 🎯 Introduction  
Amazon **Simple Storage Service (S3)** is a **highly scalable** and **secure** object storage service that allows users to **store, retrieve, and manage data** over the internet.

✅ **In this guide, you will learn:**  
✔️ What **S3** is and how it works  
✔️ **Buckets, Folders, and Objects**  
✔️ Key **characteristics** of S3  
✔️ **Storage classes and versioning**  

---

## 📌 1️⃣ What is Amazon S3?  
✔️ **S3 stands for Simple Storage Service**  
✔️ Provides **secure, durable, and highly available** cloud storage  
✔️ Can be accessed via **AWS Console, CLI, or SDKs**  
✔️ Ideal for storing **large-scale data, backups, media files, logs, and big data**  

---

## 📌 2️⃣ Understanding S3 Buckets, Folders, and Objects  

### 🔹 **S3 Buckets**
- **A bucket is a logical container** in which data is stored inside S3.  
- Buckets must have **globally unique names** across all AWS accounts and regions.  
- Example: If a bucket is named `my-bucket`, no other AWS account can create `my-bucket`.  

### 🔹 **S3 Folders**
- **Used for organizing objects** inside a bucket.  
- Unlike traditional filesystems, S3 **does not use a hierarchical structure**.  
- The **AWS Console represents folders visually**, but internally, they are part of the object's key.  

### 🔹 **S3 Objects**
- **Objects = Files + Metadata**  
- Examples: Documents, images, videos, backups, logs, etc.  
- **When you upload a file to S3, it becomes an "Object".**  
- **Buckets store objects, similar to a file directory in a traditional filesystem.**  

---

## 📌 3️⃣ Key Characteristics of S3 Objects  

### 🔹 **Object Size Limits**
✔️ The maximum **single object** size: **5 TB**  
✔️ **Objects larger than 5 GB** require **multipart upload**  
✔️ **Multipart upload** allows large files to be uploaded in parts  

### 🔹 **Object Versioning**
✔️ **Maintains multiple versions** of an object.  
✔️ Helps in **accidental deletions or overwrites**.  
✔️ **Versioning can be enabled per bucket**.  

### 🔹 **Storage Classes**
✔️ S3 provides **multiple storage classes** based on **cost and access frequency**.  
✔️ **Common Storage Classes:**
  - **S3 Standard** – Frequently accessed data.  
  - **S3 Intelligent-Tiering** – Automatically moves data between tiers.  
  - **S3 Standard-IA** (Infrequent Access) – Lower cost for less frequent access.  
  - **S3 Glacier & Glacier Deep Archive** – Low-cost storage for long-term backups.  

### 🔹 **Permissions & Access Control**
✔️ **Bucket policies and IAM policies** control access to S3 resources.  
✔️ **S3 Block Public Access** prevents unauthorized public access.  
✔️ Objects and buckets can have **fine-grained permissions**.  

---

## 📌 4️⃣ Summary  

🔹 **Amazon S3** is an object storage service used for **scalable** and **durable** storage.  
🔹 Data is stored in **buckets** and organized using **folders**.  
🔹 Objects have a **maximum size of 5TB**, and large objects require **multipart uploads**.  
🔹 **Versioning helps retain object history** and prevents accidental deletions.  
🔹 **Storage classes help optimize cost** based on access frequency.  
🔹 **Permissions and policies ensure security** and controlled access.  


