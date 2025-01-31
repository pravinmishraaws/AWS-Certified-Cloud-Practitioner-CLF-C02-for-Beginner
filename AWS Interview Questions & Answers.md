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

## **Networking in AWS**
### 1️⃣ What is the difference between a public subnet and a private subnet?
### 2️⃣ How to connect a private subnet or server from public?
### 3️⃣ What is PrivateLink in S3?
### 4️⃣ VPC Endpoint Types?
### 5️⃣ What is VPC Peering and its steps?
### 6️⃣ VPC Transit Gateway Steps?
### 7️⃣ Have you ever configured a Transit Gateway?
### 8️⃣ What is the difference between a Security Group and NACL?
### 9️⃣ How to restrict the traffic between ALB and NLB?
### 🔟 Explain the use of a route table. If there is an entry in NACL and no entry in the route table, will it work?
### 11️⃣ If there is an application in one VPC and a jump host in another VPC, how can you access the application URL from the jump host? What additional configurations are required?

---

## **Storage**
### 1️⃣ Types of connection from EC2 to S3. Is it public or private?
### 2️⃣ How to achieve end-to-end encryption in S3?
### 3️⃣ Encryption in REST vs Transit?
### 4️⃣ How do you encrypt in S3 and the types?
### 5️⃣ Resolving File Management Challenges with Amazon S3 (Assignment 40).
### 6️⃣ Managing Storage Costs for EpicReads' Expanding Digital Assets (Assignment 41).
### 7️⃣ Addressing Rising Storage Costs Due to S3 Versioning (Assignment 42).
### 8️⃣ Can we reduce the volume size, and if not, how can we migrate data from one volume to another?

---

## **Security and Compliance**
### 1️⃣ How to secure the resources in AWS?
### 2️⃣ Encryption Types?
### 3️⃣ How do you monitor server patching?
### 4️⃣ Difference between CA and self-signed certificate?
### 5️⃣ There is an e-commerce website hosted by Russia, and they want to block all requests from Ukraine. How to do that?
### 6️⃣ If there is any vulnerability detected like Log4J, how will you provide a solution from the AWS side?
### 7️⃣ What are the best security measures implemented in your project?

---

## **Serverless & Compute**
### 1️⃣ How to optimize Lambda functions?
### 2️⃣ How to increase Lambda function performance?
### 3️⃣ Common issues you face in Lambda functions?
### 4️⃣ Explain the difference between ECS task and service.
### 5️⃣ How do you use Auto Scaling in your project?
### 6️⃣ What have you done in Terraform?

---

## **Infrastructure as Code (IaC)**
### 1️⃣ Terraform import - Explain with an example.
### 2️⃣ Terraform Module?
### 3️⃣ Terraform best practices?
### 4️⃣ What is a Statefile, and where do you keep it?
### 5️⃣ What was the idea behind choosing Terraform?
### 6️⃣ Explain Terraform Drift.
### 7️⃣ What is Sentinel Policy?
### 8️⃣ .git-ci.yaml file for Terraform steps?

---

## **Observability and Monitoring**
### 1️⃣ How to monitor VPC logs?
### 2️⃣ What observability tools do you use in projects?
### 3️⃣ What are all the metrics to monitor for an application?
### 4️⃣ How are you monitoring EC2 and ECS in your project?

## **DevOps Concepts and Practices**

### **General DevOps Concepts**
### 1️⃣ What is DevOps, and why is it important?
### 2️⃣ Explain the difference between DevOps and Agile.
### 3️⃣ What are the main components of a DevOps pipeline?
### 4️⃣ What is the role of CI/CD in DevOps?
### 5️⃣ How do you approach infrastructure as code (IaC)?
### 6️⃣ What are the best security measures implemented in your project?

---

### **CI/CD Pipelines**
### 1️⃣ What is a CI/CD pipeline?
### 2️⃣ How do you implement a CI/CD pipeline from scratch?
### 3️⃣ How do you handle rollbacks in CI/CD?
### 4️⃣ What is the purpose of artifact repositories in CI/CD?
### 5️⃣ How do you ensure that deployments are zero-downtime?

---

### **Containers & Kubernetes**
### 1️⃣ What is Docker, and how does it work?
### 2️⃣ What is Kubernetes, and why is it used?
### 3️⃣ Explain the concept of Docker Compose.
### 4️⃣ How do you deploy a Kubernetes cluster?
### 5️⃣ What are Kubernetes Pods, and how do they work?
### 6️⃣ How do you monitor and scale a Kubernetes cluster?
### 7️⃣ What are Kubernetes Ingress and Services?

---

### **Real-World Scenarios**
### 1️⃣ What are your day-to-day activities as a DevOps Engineer?
### 2️⃣ Explain some issues you have faced in production and how you resolved them.
### 3️⃣ Have you performed an RCA of any production issues?
### 4️⃣ Explain the complete architecture of your project.
### 5️⃣ Have you enabled any monitoring metrics in your project?

---

### **Miscellaneous**
### 1️⃣ What is GitLab Actions?
### 2️⃣ How do you maintain nodes in Jenkins?
### 3️⃣ Which language is used to write Jenkins pipelines?
### 4️⃣ Have you ever written a Dockerfile?
### 5️⃣ How do you access an EC2 instance if your .pem file is lost?
### 6️⃣ Difference between EBS and EFS?
### 7️⃣ How can you increase the size of an EBS volume?
### 8️⃣ Lifecycle of Auto Scaling EC2 instance.
### 9️⃣ ECS task strategies.
### 🔟 Use of behaviors in CloudFront.
### 11️⃣ Use case of AWS WAF.
### 12️⃣ How to give a meaningful URL to an Application Load Balancer DNS?


## 📌 **More AWS Interview Questions Coming Soon! Stay Tuned 🚀**
