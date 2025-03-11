# 🧹 Cleaning Up AWS Resources

I have completed the **Introduction to Cost Management** section.  
To **avoid unnecessary charges**, I will now clean up all the resources I created.

> **Note:**  
> If I used an **AWS-provisioned account for an event**, cleanup is not required.  
> If I completed this workshop **in my own AWS account**, I must **follow these steps** to delete resources.

---

## 🚀 **Step-by-Step: Cleaning Up Resources**

---

## **1️⃣ Remove Cost Monitor and Email Subscription**
- Navigate to **[AWS Cost Anomaly Detection](https://console.aws.amazon.com/cost-management/home?#/anomaly-detection)**.
- Click on the **Cost Monitors** tab.
- Select **CostOpMonitor**.
- Click **Delete** and confirm the prompt.



2️⃣ Remove Sample Budget from AWS Budgets
Open the AWS Budgets Console.
Click on Budgets in the left menu.
Select the Zero-Spend Budget checkbox.
Click Actions → Delete.
Confirm by clicking Confirm.



3️⃣ Deactivate Billing Alarms & Tags
Navigate to AWS Billing Console.
Select Cost Allocation Tags.
Under AWS-Generated Cost Allocation Tags:
Select aws:createdBy.
Click Deactivate → Confirm.
 If I activated a User-Defined Cost Allocation Tag, repeat the steps above.

Navigate to CloudWatch Billing Alarms.
Select CW_Billing_Alarm.
Click Actions → Delete → Confirm.

4️⃣ Terminate EC2 Instance, Security Group, and Delete Key Pair
Open the AWS EC2 Console.
Click Instances in the left-hand menu.
Select CostOpInstance.
Click Instance State → Terminate → Confirm.

Click on the Key Pair Name: CostOpKey.
Select CostOpKey, then Actions → Delete → Type "Delete" → Confirm.

Navigate back to the Instance Details Page → Security Tab.
Click on the Security Group linked to the instance.
Select Actions → Delete Security Group → Confirm.

5️⃣ Remove Organization from AWS Organizations
Important:
If this AWS account was created within an Organization, I must remove it before deletion.

Open the AWS Organizations Console.
Select the CostOpDemo Organization checkbox.
Click Actions → Remove from Organization.
Click Remove Account.

6️⃣ Remove IAM Users and Groups
Open the AWS IAM Console.
Click Users in the left-hand menu.
Select CostOp_Admin and any other CostOp users.
Click Delete → Type "delete" → Confirm.

Click User Groups in the left-hand menu.
Select CostOp Groups.
Click Delete → Confirm.

✅ Cleanup Complete!
I have successfully removed all unnecessary resources and avoided future AWS charges.
