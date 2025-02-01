# 💰 [HOL] Set Up AWS Budget & Cost Alerts

## 🎉 Introduction
Managing AWS costs effectively is crucial to **avoid unexpected charges**.  
This **Hands-On Lab (HOL)** will guide you through:
✅ **Creating a Budget in AWS**  
✅ **Setting Up Cost Alerts** for budget thresholds  
✅ **Monitoring & Optimizing AWS Spending**  

---

## 📌 1️⃣ Create an AWS Budget
### 🔹 Why Set a Budget?
- **Prevents unexpected charges** by tracking AWS costs.
- Sends **alerts** when spending **exceeds a set limit**.
- Helps **optimize AWS usage**.

### ✅ **Steps to Create an AWS Budget**
1. **Log in** to the **AWS Management Console**.
2. Open the **AWS Billing Dashboard**.
3. Click **Budgets** in the left panel.
4. Click **Create Budget**.
5. Choose **Cost Budget** and click **Next**.
6. Enter:
   - **Budget Name** (e.g., `Monthly Budget`)
   - **Period**: Monthly (Recommended)
   - **Budget Amount**: Enter your limit (e.g., `$50`)
   - **Include all AWS Services** (or select specific services).
7. Click **Next**.

📌 **Result:** A budget is now created for monitoring AWS costs.

---

## 📌 2️⃣ Set Up Budget Alerts
### 🔹 Why Use Budget Alerts?
- **Sends email notifications** when AWS costs exceed limits.
- Helps **take action before unexpected charges** occur.

### ✅ **Steps to Set Up Alerts**
1. In the **Create Budget** wizard, go to the **Notifications** section.
2. Click **Add a Notification**.
3. Set the **Threshold** (e.g., `80% of Budget`).
4. Choose **Email Alerts** and **enter your email address**.
5. Click **Add Another Notification** (Optional):
   - **100% of Budget** (for full alert).
6. Click **Next** and then **Create Budget**.

📌 **Result:** AWS **will notify you** via email if spending exceeds thresholds.

---

## 📌 3️⃣ Monitor & Optimize Costs
### 🔹 How to Monitor AWS Spending?
✅ Use **AWS Cost Explorer** to analyze spending trends.  
✅ Check **AWS Budgets Dashboard** for real-time tracking.  
✅ **Review past invoices** to identify cost-heavy services.  

📌 **Best Practice:**  
✔️ **Set multiple budget thresholds** (e.g., 50%, 80%, 100%) for proactive alerts.  
✔️ **Regularly review** AWS **spending reports** and optimize resource usage.  

---

## 🎯 Conclusion
✅ **AWS Budget is created** to monitor cloud costs.  
✅ **Cost Alerts are configured** to prevent overspending.  
✅ **Spending is tracked effectively**, ensuring cost optimization.  

🚀 **Next Steps:**  
👉 **[HOL] Enable AWS Cost Explorer for Usage Analysis**  
👉 **[HOL] Set Up AWS Trusted Advisor for Cost Optimization**  
