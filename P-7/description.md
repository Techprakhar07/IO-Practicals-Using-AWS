# Managing S3 Object Lifecycle with Policies

### Steps to Complete the Practical

1. **Create an S3 Bucket**  
   - Go to the S3 service and click **Create Bucket**.
   - Upload files to the bucket.

2. **Define Lifecycle Rules**  
   - In the bucket settings, go to the **Management** tab.
   - Click **Create Lifecycle Rule** and configure actions like:
     - Transition to Glacier after 30 days.
     - Delete after 365 days.

3. **Save and Verify**  
   - Save the rule and monitor object transitions.
