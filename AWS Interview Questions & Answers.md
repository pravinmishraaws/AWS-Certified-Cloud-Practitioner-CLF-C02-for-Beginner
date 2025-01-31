# 🏆 AWS Interview Questions & Answers

## **AWS Fundamentals**

### 1️⃣ What is AWS, and why is it preferred for cloud computing?
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <p>
  AWS (Amazon Web Services) is a **comprehensive cloud computing platform** offered by Amazon, providing on-demand cloud services such as computing power, storage, and databases. It is preferred because:
  </p>
  <ul>
    <li><strong>Scalability</strong>: Supports auto-scaling and on-demand resources.</li>
    <li><strong>Cost-Effective</strong>: Pay-as-you-go pricing model.</li>
    <li><strong>Security</strong>: Robust security features with IAM, encryption, and compliance.</li>
    <li><strong>Global Presence</strong>: Availability across multiple <strong>Regions</strong> and <strong>Availability Zones</strong>.</li>
    <li><strong>Managed Services</strong>: Offers fully managed solutions for databases, analytics, AI/ML, and more.</li>
  </ul>
</details>

---

### 2️⃣ What is AWS Landing Zone?
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <p>
  AWS Landing Zone is a **pre-configured environment** that enables organizations to quickly set up a **secure, multi-account AWS environment** using best practices. It helps with:
  </p>
  <ul>
    <li><strong>Automated account provisioning</strong></li>
    <li><strong>Centralized identity and access management</strong></li>
    <li><strong>Security baseline configurations</strong></li>
    <li><strong>Logging and monitoring setup</strong></li>
    <li><strong>Networking configurations</strong> for a scalable AWS setup</li>
  </ul>
</details>

---

### 3️⃣ What is AWS Organizations?
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <p>
  AWS Organizations is a service that **helps manage multiple AWS accounts** centrally. It allows:
  </p>
  <ul>
    <li><strong>Consolidated billing</strong> for cost management.</li>
    <li><strong>Account grouping</strong> under Organizational Units (OUs).</li>
    <li><strong>Service control policies (SCPs)</strong> to enforce security across accounts.</li>
    <li><strong>Cross-account permissions</strong> and centralized access management.</li>
  </ul>
</details>

---

### 4️⃣ What is the Shared Responsibility Model in AWS?
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <p>
  The AWS Shared Responsibility Model defines the **division of security responsibilities** between AWS and the customer:
  </p>
  <ul>
    <li><strong>AWS is responsible for</strong>: Securing the underlying infrastructure (hardware, networking, regions, availability zones, and data centers).</li>
    <li><strong>Customer is responsible for</strong>: Securing applications, data, identity access management (IAM), encryption, and network configurations.</li>
  </ul>
  <p>This model ensures security and compliance while providing flexibility to customers.</p>
</details>

---

### 5️⃣ Explain the difference between EC2 and Lambda.
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>AWS EC2 🖥️</th>
        <th>AWS Lambda ⚡</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Type</strong></td>
        <td>Virtual machines (IaaS)</td>
        <td>Serverless compute (FaaS)</td>
      </tr>
      <tr>
        <td><strong>Provisioning</strong></td>
        <td>Manual setup required</td>
        <td>No provisioning needed</td>
      </tr>
      <tr>
        <td><strong>Scalability</strong></td>
        <td>Auto Scaling enabled</td>
        <td>Automatic scaling</td>
      </tr>
      <tr>
        <td><strong>Billing</strong></td>
        <td>Pay for instance uptime</td>
        <td>Pay per request & execution time</td>
      </tr>
      <tr>
        <td><strong>Use Case</strong></td>
        <td>Long-running applications</td>
        <td>Event-driven, short-lived functions</td>
      </tr>
    </tbody>
  </table>
</details>

---

### 6️⃣ What is an S3 bucket lifecycle policy?
<details>
  <summary><strong>See the Answer ⬇️</strong></summary>
  <p>
  An **S3 lifecycle policy** is a set of rules that **automate data management** within an Amazon S3 bucket by transitioning or deleting objects based on defined criteria. It allows:
  </p>
  <ul>
    <li><strong>Moving objects between storage classes</strong> (e.g., S3 Standard → S3 Glacier for cost savings).</li>
    <li><strong>Deleting objects automatically</strong> after a certain period to free up storage.</li>
    <li><strong>Defining lifecycle rules</strong> for versioning, expiration, and cleanup of incomplete multipart uploads.</li>
  </ul>
  <p><strong>Example policy:</strong></p>
  <pre><code>
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
  </code></pre>
</details>

---

## **Identity and Access Management (IAM)**

### 1️⃣ IAM User vs Role?

### 2️⃣ IAM Assume Role?

### 3️⃣ What is a condition in an IAM Policy?

### 4️⃣ Explain IAM Policy and all steps in that.

### 5️⃣ How to create a role and its purpose?

### 6️⃣ What is the purpose of assigning a role to a resource?

### 7️⃣ What is the use of the external ID option while creating a role?

### 8️⃣ Difference between assume role and normal role?

## 📌 **More AWS Interview Questions Coming Soon! Stay Tuned 🚀**
