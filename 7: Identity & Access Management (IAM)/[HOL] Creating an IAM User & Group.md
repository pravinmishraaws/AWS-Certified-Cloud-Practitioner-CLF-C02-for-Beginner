# 🔐 [HOL] Create IAM Users & Groups

## 🎉 Introduction
In this hands-on lab, you will learn how to create **IAM Users and Groups** in AWS and assign permissions.  
By the end of this lab, you will be able to:

✅ Create IAM **Users**  
✅ Create IAM **Groups**  
✅ Assign IAM **Policies** to users and groups  

---

## 📌 1️⃣ Navigate to IAM Console
1. Log in to your **AWS Management Console**.
2. In the **Search bar**, type **IAM** and select **IAM** from the services list.
3. This will take you to the **IAM Dashboard**.

---

## 📌 2️⃣ Create IAM Users
### 🏗️ Step 1: Add Users
1. In the **IAM Dashboard**, click on **Users** from the left menu.
2. Click on **Add Users**.
3. Enter **Username**:  
   - **Ram** (Developer)  
   - **Shyam** (Administrator)  

### 🏗️ Step 2: Set AWS Access  
4. Select **AWS Management Console access**.
5. Choose **Auto-generated password**.
6. (Optional) **Uncheck** "Require password reset on first login".

### 🏗️ Step 3: Set Permissions  
7. Click **Next: Permissions**.  
8. Choose **No permissions for now** (we will assign them later).  
9. Click **Next: Tags**.  
10. Add a **Tag**: `Key: Department | Value: Finance`.  
11. Click **Next: Review** and then **Create User**.

### 🏗️ Step 4: Save User Credentials  
12. Click **Download CSV** to store user credentials securely.  
13. Click **Close**.

🚀 **Repeat the steps for user Shyam**.

---

## 📌 3️⃣ Create IAM Groups
### 🏗️ Step 1: Create "Developers" Group
1. Navigate to **User Groups** in IAM.
2. Click on **Create Group**.
3. Enter **Group Name**: `Developers`.
4. Add **User**: `Ram`.
5. Attach Policies:  
   - ✅ `AmazonEC2FullAccess`
   - ✅ `AmazonS3FullAccess`
6. Click **Create Group**.

### 🏗️ Step 2: Create "Administrators" Group
1. Click on **Create Group**.
2. Enter **Group Name**: `Administrators`.
3. **Skip adding users** for now.
4. Attach Policy:  
   - ✅ `AdministratorAccess`
5. Click **Create Group**.

---

## 📌 4️⃣ Assign User to Administrator Group
1. Go to **Users**.
2. Click on **Shyam**.
3. Select **Groups → Add User to Group**.
4. Select **Administrators** Group.
5. Click **Add to Group**.

Now, Shyam has **AdministratorAccess** inherited from the **Administrators** group.

---

## 🎯 Conclusion
✅ Created **IAM Users** (Ram & Shyam).  
✅ Created **IAM Groups** (Developers & Administrators).  
✅ Assigned appropriate **IAM Policies**.  
✅ Added **Users to Groups** for easy permission management.  

