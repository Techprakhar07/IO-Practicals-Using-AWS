# Hosting Multiple Websites on One Web Server

### Steps to Complete the Practical

1. **Launch an EC2 Instance**  
   - Go to the EC2 service on AWS.
   - Launch a new instance with the following configuration:
     - AMI: Ubuntu 24.04 (Free Tier Eligible)
     - Instance Type: t2.micro
     - Security Group: Allow SSH and HTTP traffic.

2. **Install Apache Web Server**  
   - Connect to your instance using SSH.
   - Update the package list:  
     `sudo apt update`
   - Install Apache:  
     `sudo apt install apache2`

3. **Create Directories for Websites**  
   - Navigate to the Apache web root directory:  
     `cd /var/www/html`
   - Create three directories:  
     `mkdir web1 web2 web3`

4. **Upload Website Templates**  
   - Download website templates from any open-source resource.
   - Unzip the files and move them to the respective directories (web1, web2, web3).  
     Example commands:  
     `sudo cp -r website1/* /var/www/html/web1/`

5. **Configure Apache Virtual Hosts**  
   - Edit the Apache configuration file:  
     `sudo nano /etc/apache2/sites-available/000-default.conf`
   - Add the following configurations for each website:
     ```plaintext
     <VirtualHost *:80>
         ServerAdmin webmaster@localhost
         DocumentRoot /var/www/html/web1
         ServerName web1.example.com
     </VirtualHost>
     ```
   - Repeat for `web2` and `web3`.

6. **Enable Virtual Hosts and Restart Apache**  
   - Enable the site configurations:  
     `sudo a2ensite web1.conf web2.conf web3.conf`
   - Restart the Apache server:  
     `sudo systemctl restart apache2`

7. **Test the Setup**  
   - Access the websites via the public IP address of the instance:
     - `http://<Public_IP>/web1/`
     - `http://<Public_IP>/web2/`
     - `http://<Public_IP>/web3/`
