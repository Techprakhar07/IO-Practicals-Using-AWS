# Scaling Applications with EC2 and Load Balancer Integration

### Steps to Complete the Practical

1. **Launch EC2 Instances**  
   - Go to the EC2 service and launch 4 instances with the following configuration:
     - AMI: Ubuntu 24.04
     - Instance Type: t2.micro
     - Security Group: Allow HTTP and SSH traffic.
   - Name the instances as WebServer1, WebServer2, WebServer3, and WebServer4.

2. **Install Web Server**  
   - Connect to each instance via SSH.
   - Install Apache:  
     `sudo apt install apache2`
   - Create a basic HTML file in `/var/www/html/` for each instance to differentiate them.

3. **Configure Security Group**  
   - Edit the security group to allow HTTP traffic (port 80) from any IP address.

4. **Set Up a Target Group**  
   - Go to the Target Groups section in the AWS EC2 dashboard.
   - Create a new target group:
     - Target Type: Instance
     - Protocol: HTTP
     - Health Check: Enable HTTP health checks.
   - Add all 4 instances to the target group.

5. **Create an Application Load Balancer (ALB)**  
   - Go to the Load Balancer section in the AWS EC2 dashboard.
   - Create a new ALB:
     - Listener Protocol: HTTP
     - Security Group: Allow HTTP traffic.
     - Associate the ALB with the previously created target group.

6. **Test the Load Balancer**  
   - Copy the DNS name of the ALB and paste it into your browser.
   - Refresh the browser multiple times to verify traffic distribution among instances.

7. **Clean Up Resources**  
   - Terminate the instances and delete the ALB to avoid charges.
