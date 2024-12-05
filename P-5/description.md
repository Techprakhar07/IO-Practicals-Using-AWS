# Enabling EC2 Instance Access to S3 Buckets

### Steps to Complete the Practical

1. **Create an S3 Bucket**  
   - Go to the S3 service and click **Create Bucket**.
   - Enter a bucket name and click **Create**.

2. **Launch an EC2 Instance**  
   - Launch an Ubuntu instance.
   - Allow HTTP and SSH traffic in the security group.

3. **Create an IAM Role**  
   - Go to the IAM service and create a role.
   - Attach the **AmazonS3FullAccess** policy to the role.

4. **Attach the IAM Role to the Instance**  
   - Go to the EC2 dashboard.
   - Select the instance and attach the IAM role.

5. **Access S3 from the Instance**  
   - Connect to the instance via SSH.
   - Install AWS CLI:  
     `sudo apt install awscli`
   - Configure AWS CLI using the instance role.  
     `aws s3 ls`
