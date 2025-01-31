# 🏆 AWS Interview Questions & Answers

## **AWS Fundamentals**

### **1. What is AWS, and why is it preferred for cloud computing?**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  AWS (Amazon Web Services) is a **comprehensive and widely adopted cloud computing platform** offered by Amazon, providing on-demand cloud services such as computing power, storage, and databases. It is preferred because:
  - **Scalability**: Supports auto-scaling and on-demand resources.
  - **Cost-Effective**: Pay-as-you-go pricing model.
  - **Security**: Robust security features with IAM, encryption, and compliance.
  - **Global Presence**: Availability across multiple **Regions** and **Availability Zones**.
  - **Managed Services**: Offers fully managed solutions for databases, analytics, AI/ML, and more.
</details>

---

### **2. What is AWS Landing Zone?**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  AWS Landing Zone is a **pre-configured environment** that enables organizations to quickly set up a **secure, multi-account AWS environment** using best practices. It helps with:
  - **Automated account provisioning**
  - **Centralized identity and access management**
  - **Security baseline configurations**
  - **Logging and monitoring setup**
  - **Networking configurations** for a scalable AWS setup
</details>

---

### **3. What is AWS Organizations?**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  AWS Organizations is a service that **helps manage multiple AWS accounts** centrally. It allows:
  - **Consolidated billing** for cost management.
  - **Account grouping** under Organizational Units (OUs).
  - **Service control policies (SCPs)** to enforce security across accounts.
  - **Cross-account permissions** and centralized access management.
</details>

---

### **4. What is the Shared Responsibility Model in AWS?**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  The AWS Shared Responsibility Model defines the **division of security responsibilities** between AWS and the customer:
  - **AWS is responsible for**: Securing the underlying infrastructure (hardware, networking, regions, availability zones, and data centers).
  - **Customer is responsible for**: Securing applications, data, identity access management (IAM), encryption, and network configurations.
  This model ensures security and compliance while providing flexibility to customers.
</details>

---

### **5. Explain the difference between EC2 and Lambda.**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  | Feature            | AWS EC2 🖥️ | AWS Lambda ⚡ |
  |-------------------|------------|-------------|
  | **Type**         | Virtual machines (IaaS) | Serverless compute (FaaS) |
  | **Provisioning** | Manual setup required | No provisioning needed |
  | **Scalability**  | Auto Scaling enabled | Automatic scaling |
  | **Billing**      | Pay for instance uptime | Pay per request & execution time |
  | **Use Case**     | Long-running applications | Event-driven, short-lived functions |
</details>

---

### **6. What is an S3 bucket lifecycle policy?**
<details style="font-size: 14px; cursor: pointer; outline: none;">
  <summary>See the Answer</summary>
  An **S3 lifecycle policy** is a set of rules that **automate data management** within an Amazon S3 bucket by transitioning or deleting objects based on defined criteria. It allows:
  - **Moving objects between storage classes** (e.g., S3 Standard → S3 Glacier for cost savings).
  - **Deleting objects automatically** after a certain period to free up storage.
  - **Defining lifecycle rules** for versioning, expiration, and cleanup of incomplete multipart uploads.

  Example policy:
  ```json
  {
    "Rules": [
      {
        "ID": "MoveToGlacier",
        "Status": "Enabled",
        "Prefix": "logs/",
        "Transitions": [
          {
            "Days": 30,
            "StorageClass": "GLACIER"
          }
        ],
        "Expiration": {
          "Days": 365
        }
      }
    ]
  }
  ```
</details>
