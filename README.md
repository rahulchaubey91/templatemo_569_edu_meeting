✅ Project Documentation
Hosting Static Website on Ubuntu NGINX via GitHub (Azure VM)

🔹 Objective:

To deploy a static HTML5 template website from a GitHub repository 
to an Ubuntu 24.04 Azure Virtual Machine (VM) using NGINX.

🔸 Prerequisites:

- Azure Ubuntu 24.04 LTS Virtual Machine
- GitHub repository with website files
- .pem or .ppk key (or Azure username/password for login)
- NGINX installed on the Ubuntu VM
- Inbound ports 22 (SSH) and 80 (HTTP) opened in Azure NSG

🔸 Step-by-Step Deployment Process

🟢 Step 1: Create Ubuntu VM on Azure

- Go to Azure Portal
- Create a new Ubuntu 24.04 LTS VM
- In Networking tab:
   • Allow Port 22 (SSH)
   • Allow Port 80 (HTTP)
- Download the SSH private key if using key-based login

🟢 Step 2: SSH into Azure VM using MobaXterm

Use MobaXterm:

<img width="998" height="667" alt="image" src="https://github.com/user-attachments/assets/936d3a02-2410-46c5-9f2c-c5a57c727ea4" />


🟢 Step 3: Update Ubuntu & Install NGINX

Commands:
sudo su
apt update -y
apt install nginx -y
systemctl enable nginx
systemctl start nginx

🔎 Visit http://13.201.20.161 → You should see the NGINX Welcome page.

<img width="1908" height="1078" alt="image" src="https://github.com/user-attachments/assets/acbea535-73e3-4f4e-ae7c-86b15eef3100" />


🟢 Step 4: Git Clone from GitHub Repository

Command:
git clone https://github.com/rahulchaubey91/templatemo_569_edu_meeting.git

<img width="1917" height="1072" alt="image" src="https://github.com/user-attachments/assets/856d32b8-a2ed-44c2-8dc5-d6ffaf22a44f" />



🟢 Step 5: Deploy Website to NGINX Directory

Commands:
rm -rf /var/www/html/*
cp -r /home/ubuntu/templatemo_569_edu_meeting/* /var/www/html/
ls /var/www/html

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/20862381-dab7-43f4-9857-b4cc2d5519c4" />


🟢 Step 6: Restart NGINX

Command:
systemctl restart nginx

✅ Final Output

Open in browser:
http://13.201.20.161

You should see:
TemplateMo Educational HTML CSS template deployed successfully.

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/e478fe61-414a-43f2-b67b-83bad9c1e418" />



