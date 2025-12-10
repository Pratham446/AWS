A simple, secure, and scalable static website hosted on an AWS EC2 instance using the NGINX web server, with SSH and TCP/IP–based security configurations
🚀 Project Overview

This project demonstrates how to host a static HTML/CSS/JS website on an AWS EC2 Linux instance using NGINX as the web server. The setup includes:

EC2 Instance (Ubuntu/Amazon Linux)

NGINX Web Server

Static Website Deployment

Secure access using SSH

Network configuration with TCP/IP, HTTP, and Security Groups

🛠️ Tech Stack

AWS EC2 – Compute hosting

NGINX – Web server for serving static content

HTML/CSS/JS – Frontend static website

SSH – Secure shell for remote access

TCP/IP – Network communication

HTTP/HTTPS – Web protocols

📁 Project Structure
/project-root
│── index.html
│── styles/
│── scripts/
└── README.md

🧩 Steps to Host Static Website on AWS EC2 Using NGINX
1️⃣ Launch EC2 Instance

Choose Ubuntu or Amazon Linux

Create/Download Key Pair (.pem)

Configure Security Group

Allow SSH (port 22)

Allow HTTP (port 80)

(Optional) Allow HTTPS (port 443)

2️⃣ Connect to EC2 Using SSH
ssh -i "your-key.pem" ubuntu@your-public-ip

3️⃣ Install & Start NGINX
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx


Verify:

http://your-public-ip

4️⃣ Deploy Static Website

Remove default NGINX page:

sudo rm -f /var/www/html/index.nginx-debian.html


Copy your website files:

sudo cp -r * /var/www/html/


Restart NGINX:

sudo systemctl restart nginx

🔐 Security Protocols Used
✔ SSH (Secure Shell)

Used for secure remote login to the EC2 instance using a key pair instead of passwords.

✔ TCP/IP

Handles the network communication between the client (browser) and the AWS server.

✔ HTTP

Default protocol used to serve the website on port 80.

✔ Security Groups

Firewall rules to allow:

SSH (22)

HTTP (80)

(Optional) HTTPS (443)

🌍 Access Your Website

Open this in browser:

http://<your-public-ip>
