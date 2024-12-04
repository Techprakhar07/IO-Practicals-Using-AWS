# Automating AWS Infrastructure with CloudFormation

### Steps to Complete the Practical

1. **Prepare CloudFormation Template**  
   - Open a code editor and create a YAML file to define AWS resources.
   - Include the following in your YAML file:
     - VPC
     - Public and Private Subnets
     - EC2 Instances
     - SNS Topic for notifications

2. **Write a Sample YAML Template**  
   - Example:
     ```yaml
     AWSTemplateFormatVersion: '2010-09-09'
     Description: CloudFormation template to create a VPC and deploy resources.
     Resources:
       MyVPC:
         Type: AWS::EC2::VPC
         Properties:
           CidrBlock: 10.0.0.0/16
           EnableDnsSupport: true
           EnableDnsHostnames: true
     ```

3. **Deploy the CloudFormation Template**  
   - Log in to the AWS Management Console.
   - Go to the CloudFormation service.
   - Click **Create Stack** > **Upload a Template File**.
   - Upload the YAML file and click **Next**.

4. **Configure Stack Details**  
   - Enter a name for your stack.
   - Configure parameters (e.g., key pair, instance types).

5. **Monitor Deployment**  
   - Navigate to the **Events** tab in CloudFormation to monitor resource creation.
   - Wait until the stack status changes to `CREATE_COMPLETE`.

6. **Verify Resources**  
   - Go to the EC2, VPC, and SNS services to confirm that resources have been created successfully.
