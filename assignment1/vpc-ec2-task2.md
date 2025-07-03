1. Create a Custom VPC
   - [ ] Go to VPC Dashboard → Create VPC
   - [ ] Name: MyCustomVPC
   - [ ] IPv4 CIDR block: 10.0.0.0/16

2. Create Subnets
   - [ ] Public Subnet (10.0.1.0/24)
   - [ ] Private Subnet (10.0.2.0/24)
   - [ ] Use different Availability Zones

3. Set Up Internet Gateway
   - [ ] Create Internet Gateway
   - [ ] Attach it to MyCustomVPC
   - [ ] Modify Public Route Table: route 0.0.0.0/0 to Internet Gateway

4. Configure Security Group
   - [ ] Allow SSH (port 22) from your IP
   - [ ] Allow HTTP (port 80) from 0.0.0.0/0

5. Launch EC2 Instance
   - [ ] Use Amazon Linux 2 AMI
   - [ ] Select MyCustomVPC and Public Subnet
   - [ ] Enable Auto-assign Public IP
   - [ ] Attach the Security Group

6. Install Web Server (SSH into EC2 and run):
   - [ ] `sudo yum update -y`
   - [ ] `sudo yum install -y httpd`
   - [ ] `sudo systemctl start httpd`
   - [ ] `sudo systemctl enable httpd`
   - [ ] `echo "Hello from your VPC!" > /var/www/html/index.html`

7. Verify Web Page
   - [ ] Open public IP in browser
   - [ ] Should display: Hello from your VPC!

🎯 Extras (Optional)
   - [ ] Configure NAT Gateway for private subnet internet access
   - [ ] Launch database server in private subnet
