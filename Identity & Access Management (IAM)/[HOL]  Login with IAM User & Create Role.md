# 🔐 [HOL] Login as IAM User & Create IAM Role

## 🎉 Introduction
In this hands-on lab, you will learn how to:

✅ Login to **AWS Console** using an IAM User  
✅ Create an **IAM Role** for AWS services (EC2)  
✅ Understand **IAM Role Trust Policies**  

---

## 📌 1️⃣ Login as IAM User

### 🏗️ Step 1: Open AWS IAM Login Page  
1. Locate the **CSV file** downloaded while creating user **Shyam**.
2. Copy the **AWS Console Login Link** from the CSV file.
3. Open the link in a **web browser**.
4. Enter **IAM Username** (`Shyam`) and **Password**.

✅ **Note:** Since we did not enable **programmatic access**, the **Access Key ID & Secret Key** fields in the CSV will be empty.

---

## 📌 2️⃣ Navigate to IAM Console  
1. After logging in, navigate to **IAM** using the AWS **Search Bar**.
2. Click on **Roles** from the left navigation menu.
3. Click on **Create Role**.

---

## 📌 3️⃣ Create an IAM Role  

### 🏗️ Step 1: Select Trusted Entity  
AWS IAM Roles allow **AWS Services or users** to assume permissions.  
1. Under **Trusted Entity Type**, choose **AWS Service**.
2. Select **EC2** as the service that will use this role.
3. Click **Next**.

### 🏗️ Step 2: Attach Policies  
1. Choose a policy to define **role permissions**.  
2. Select ✅ **AmazonS3FullAccess** to grant full access to **Amazon S3**.
3. Click **Next**.

### 🏗️ Step 3: Configure Role Settings  
1. Enter a **Role Name** (e.g., `EC2-S3-FullAccess`).
2. Review the **default trust policy** that allows EC2 to assume this role.
3. Click **Create Role**.

🎉 **Success!** The role is now created and available under **IAM → Roles**.

---

## 📌 4️⃣ Understanding IAM Role Trust Policies  
IAM **Roles** are different from **Users** because:
- **Users have permanent credentials** (passwords, access keys).
- **Roles are assumed temporarily** by AWS services (like EC2, Lambda).

### **Trusted Entities**
- **AWS Service** → Used by AWS services like EC2, Lambda.
- **AWS Account** → Cross-account access.
- **Web Identity** → Sign-in using Google, Facebook.
- **SAML Federation** → Enterprise identity providers (Active Directory).
- **Custom Trust Policy** → Define **custom JSON-based access rules**.

---

## 📌 5️⃣ Best Practices for IAM Users & Roles  
✅ **Use IAM Users instead of Root User** for daily operations.  
✅ **Enable MFA (Multi-Factor Authentication)** for IAM users.  
✅ **Use IAM Roles for EC2** instead of hardcoding credentials.  
✅ **Delete Root User’s Access & Secret Key** for security.  
✅ **Rotate IAM User credentials regularly** to prevent unauthorized access.  

---

## 🎯 Conclusion  
✅ **Logged in as IAM User (Shyam).**  
✅ **Created IAM Role for EC2.**  
✅ **Understood Trusted Entities & Role Policies.**  
✅ **Learned IAM Security Best Practices.**  

