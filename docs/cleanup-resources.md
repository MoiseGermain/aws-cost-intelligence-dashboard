# 🧹 Cleaning Up AWS Cost Intelligence Dashboards

## **Introduction**
Now that I’ve completed the **Cloud Intelligence Dashboards** section, it's time to clean up AWS resources to **prevent any unnecessary costs**.

🔹 **Who Needs to Do This?**
- **If I used an AWS Event-provisioned account**, no cleanup is necessary.
- **If I used my own AWS account**, I need to follow these steps to ensure that no resources are left running.

---

## **1️⃣ QuickSight Cleanup**
Since QuickSight **incurs costs** for storing SPICE data, I will remove all dashboards and **terminate QuickSight** if I no longer need it.

### **Delete QuickSight Dashboards**
1. Navigate to **[Amazon QuickSight](https://quicksight.aws.amazon.com/)**
2. Click on **Dashboards** from the left menu.
3. **Select each dashboard** and **delete** it.

Release SPICE Capacity
Click on the Person Icon at the top-right.
Select Manage QuickSight.
Choose SPICE capacity on the left menu.
Click Release unused purchased capacity.
Select Release all and confirm.

Terminate QuickSight (Optional)
Click on Account settings in the left menu.
Under Account termination, click Manage.
Follow the prompt to terminate the QuickSight account.
Click Go to AWS Console to exit.

2️⃣ CloudShell Cleanup
Since CloudShell stores uploaded files, I need to delete any temporary files from this workshop.

Navigate to AWS CloudShell
Once the shell loads, run the following commands:
cd /home/cloudshell-user
rm -rf STAMCostOpsSOW
rm -rf STAMCostOpsSOW.zip

3️⃣ AWS Glue Cleanup
AWS Glue stores metadata about the datasets used in the dashboards. I will delete Glue databases and crawlers.

Delete Glue Database
Navigate to AWS Glue
Click on Databases from the left menu.
Select customer_cur_data and click Delete.

Delete Glue Crawler
Go to Crawlers in AWS Glue.
Select Crawler-Demo.
Click Actions → Delete crawler.
Confirm deletion.
This will also clean up the Athena views I created earlier.

4️⃣ Cost & Usage Reports (CURS) Cleanup
If I set up Cost & Usage Reports (CURS), I need to delete them to avoid ongoing cost tracking.

Navigate to AWS Billing
Click on Cost and Usage Reports from the left menu.
Select CostReportDemo.
Click Actions → Delete.
Confirm deletion.

5️⃣ S3 Cleanup
AWS S3 stores the cost report data. I will delete the buckets created for this workshop.

Empty S3 Buckets
Navigate to Amazon S3
Identify the three buckets created:
demo-curs-[Account-ID]
demo-costso-[Account-ID]
aws-athena-query-results-us-east-1-[Account-ID]
Select each bucket, click Empty, and confirm by typing permanently delete.

Delete S3 Buckets
After emptying all buckets, select each bucket.
Click Delete.
Confirm deletion by typing the bucket name.

✅ Cleanup Complete!
✔️ I have successfully removed all AWS Cost Intelligence Dashboard resources.
✔️ My AWS account is now free of unnecessary cost-related services.



