## Deploy a Real Web Server on the Cloud

#### Step 1: Launch EC2 Instance
#### Step 2: Connect instance via ssh
##### command: ssh -i "batch10.pem" ubuntu@ec2-35-93-207-92.us-west-2.compute.amazonaws.com
#### Step 3: Install Nginx
##### command: sudo apt update | sudo apt install nginx -y
#### Step 4: Enable nginx
##### command: sudo systemctl start nginx | sudo systemctl enable nginx
#### Step 5: In security groups access for port 80.
#### Step 6: Check Nginx logs
##### command: journalctl -u nginx -n 20
#### Step 7: Save logs to file
##### command: scp -i "batch10.pem" ubuntu@ec2-35-93-207-92.us-west-2.compute.amazonaws.com:/var/log/nginx/access.log .
#### Install Docker
##### command: sudo apt update | sudo apt isntall docker.io

### Challenges Faced   
##### custom HTML page was not loading on the webpage.
##### I reloaded the Nginx service. After reloading, my aboutme.html page was accessible.

### What I learned
#### Connect to an AWS cloud instance using SSH.
#### How to check the logs.
#### How to manage the security groups.
#### How to install Service
