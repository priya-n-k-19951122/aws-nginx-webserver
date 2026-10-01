# AWS EC2 Nginx Web Server Deployment

This repository provides an automated initialization script to deploy an Nginx web server on an AWS EC2 instance running a Red Hat Enterprise Linux (RHEL), CentOS, or Amazon Linux distribution.

## 🚀 Features
* Automated package updates via `yum` package manager.
* Silent, non-interactive installation of the Nginx web server.
* Persistent service configuration (`systemctl enable`) ensuring Nginx survives instance reboots.

## 📂 Project Structure
* `install_nginx.sh` - Core automation bash script used as User Data during EC2 instance provisioning.

## 🛠️ Deployment Steps

### 1. Launching the EC2 Instance
1. Open the **AWS Management Console** and navigate to EC2.
2. Click **Launch Instance** and select an Amazon Linux 2023 or RHEL AMI.
3. Configure your Instance Type (e.g., `t2.micro`).

### 2. Configure Network & Security Groups
Ensure your instance's security group allows inbound traffic on the following ports:
* **SSH (Port 22)**: For remote administration.
* **HTTP (Port 80)**: Crucial for serving the Nginx landing page.

### 3. Bootstrap via Advanced Details (User Data)
1. Scroll down to the **Advanced Details** section.
2. Paste the contents of `install_nginx.sh` directly into the **User Data** field.
3. Launch the instance.

## 🎯 Verification
Once the instance transitions to the `Running` state, copy its Public IPv4 address, paste it into a web browser, and verify you see the **"Welcome to nginx!"** landing page.
