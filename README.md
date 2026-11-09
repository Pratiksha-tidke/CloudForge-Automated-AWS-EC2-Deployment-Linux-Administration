# CloudForge-Automated-AWS-EC2-Deployment-Linux-Administration


<p align="center">
  <img src="https://img.shields.io/badge/AWS-Amazon%20Linux%202023-orange?style=for-the-badge&logo=amazonaws" />
  <img src="https://img.shields.io/badge/Compute-t3.micro-blue?style=for-the-badge&logo=amazon-ec2" />
  <img src="https://img.shields.io/badge/Web%20Server-Apache%20(httpd)-red?style=for-the-badge&logo=apache" />
  <img src="https://img.shields.io/badge/Automation-Bash%20%2F%20Cloud--init-green?style=for-the-badge&logo=gnu-bash" />
</p>

---

## 📑 Table of Contents

* [1. Introduction](#1-introduction)
* [2. Project Overview](#2-project-overview)
* [3. Project Objectives](#3-project-objectives)
* [4. Tools and Technologies](#4-tools-and-technologies)
* [5. AWS EC2 Deployment Architecture](#5-aws-ec2-deployment-architecture)
* [6. Implementation Methodology](#6-implementation-methodology)
    * [6.1 AWS Console Login & Security Verification](#61-aws-console-login--security-verification)
    * [6.2 Service Search & Navigation](#62-service-search--navigation)
    * [6.3 EC2 Instance Provisioning & AMI Selection](#63-ec2-instance-provisioning--ami-selection)
    * [6.4 Instance Type, Key Pair & Network Configuration](#64-instance-type-key-pair--network-configuration)
    * [6.5 Inbound Security Group Rules](#65-inbound-security-group-rules)
    * [6.6 User Data Bootstrap Script Automation](#66-user-data-bootstrap-script-automation)
    * [6.7 Instance Launch & Operational Verification](#67-instance-launch--operational-verification)
    * [6.8 Web Server Deployment Validation](#68-web-server-deployment-validation)
    * [6.9 Remote SSH Terminal Administration via PuTTY](#69-remote-ssh-terminal-administration-via-putty)
    * [6.10 Resource Lifecycle Management (Stop & Termination)](#610-resource-lifecycle-management-stop--termination)
* [7. Key Learnings & Practical Skills Gained](#7-key-learnings--practical-skills-gained)
* [8. Future Enhancements](#8-future-enhancements)
* [9. Disclaimer](#9-disclaimer)

---

## 1. Introduction

Cloud computing has transformed the way organizations deploy, manage, and maintain their IT infrastructure. Amazon Elastic Compute Cloud (Amazon EC2) is an AWS service that provides scalable virtual computing resources without requiring organizations to maintain physical servers. 

**CloudForge** is a hands-on cloud infrastructure project focused on deploying and managing a Linux-based web server using Amazon EC2. This project demonstrates automated server provisioning through EC2 User Data (`cloud-init`), Apache HTTP Server installation, SSH-based remote administration, and comprehensive cloud resource lifecycle management.

---

## 2. Project Overview

The main purpose of CloudForge is to understand how cloud-based virtual servers are provisioned, configured, accessed, and managed. In this project, an Amazon Linux 2023 EC2 instance was deployed using the `t3.micro` instance type. A Bash script was configured through EC2 User Data to automate:
* System package updates.
* Apache HTTP Server installation.
* Apache service startup and enablement.
* Custom HTML webpage creation.

After deployment, the web server was accessed through a browser using its public IPv4 address. Remote administration was performed through PuTTY using SSH key-based authentication (`Linux-pratu`). Finally, the EC2 instance was stopped and permanently terminated to ensure proper resource clean-up and cost optimization.

---

## 3. Project Objectives

1. Understand AWS cloud computing and EC2 fundamentals.
2. Provision and configure a Linux-based EC2 instance.
3. Understand Amazon Machine Images (AMIs) and instance types.
4. Configure SSH key-based authentication.
5. Implement network access control using Security Groups.
6. Automate server configuration using Bash and `cloud-init`.
7. Install and manage the Apache web server.
8. Perform remote Linux administration using SSH.
9. Validate HTTP connectivity through a web browser.
10. Understand cloud resource lifecycle management and cost optimization.

---

## 4. Tools and Technologies

| Technology | Purpose |
| :--- | :--- |
| **Amazon Web Services (AWS)** | Cloud platform infrastructure |
| **Amazon EC2** | Virtual server provisioning and hosting |
| **Amazon Linux 2023** | Server operating system distribution |
| **Bash** | Automation scripting language |
| **Cloud-init** | Automated instance initialization |
| **Apache HTTP Server (`httpd`)** | Web server software |
| **Security Groups

###  1. Introduction

Cloud computing has transformed the way organizations deploy, manage, and maintain their IT infrastructure.
Amazon Elastic Compute Cloud (Amazon EC2) is an AWS service that provides scalable virtual computing resources without requiring organizations to maintain physical servers.
CloudForge is a hands-on cloud infrastructure project focused on deploying and managing a Linux-based web server using Amazon EC2.
This project demonstrates automated server provisioning through EC2 User Data (cloud-init), Apache HTTP Server installation, SSH-based remote administration, and basic cloud resource management.

###  2. Project Overview

The main purpose of CloudForge is to understand how cloud-based virtual servers are provisioned, configured, accessed, and managed.
In this project, an Amazon Linux 2023 EC2 instance was deployed using the t3.micro instance type.
A Bash script was configured through EC2 User Data to automate:
- System package updates.
- Apache HTTP Server installation.
- Apache service startup and enablement.
- Custom HTML webpage creation.
After deployment, the web server was accessed through a browser using its public IPv4 address.
Remote administration was performed through PuTTY using SSH key-based authentication.
Finally, the EC2 instance was stopped and terminated after testing.

###  3. Project Objectives

The primary objectives of this project are:
1. Understand AWS cloud computing and EC2 fundamentals.
2. Provision and configure a Linux-based EC2 instance.
3. Understand Amazon Machine Images (AMIs) and instance types.
4. Configure SSH key-based authentication.
5. Implement network access control using Security Groups.
6. Automate server configuration using Bash and cloud-init.
7. Install and manage the Apache web server.
8. Perform remote Linux administration using SSH.
9. Validate HTTP connectivity through a web browser.
10. Understand cloud resource lifecycle management and cost optimization.

###  4. Tools and Technologies
| Technology | Purpose |
| :--- | :--- |
| Amazon Web Services | Cloud platform |
| Amazon EC2 | Virtual server provisioning |
| Amazon Linux 2023 | Server operating system |
| Bash | Automation scripting |
| Cloud-init | Automated instance initialization |
| Apache HTTP Server | Web server |
| Security Groups | Network traffic control |
| PuTTY | SSH client |
| RSA Key Pair | Key-based authentication |
| Linux | Server administration |

## AWS EC2 Deployment Architecture

```text
                         Internet Users
                               |
                               | HTTP - Port 80
                               |
                               v
                       AWS Security Group
                               |
                               v
                          Amazon EC2
                       Amazon Linux 2023
                               |
                               v
                    Cloud-init / User Data
                               |
                        Bash Automation
                               |
                  +------------+------------+
                  |                         |
                  v                         v
             Install Apache          Create HTML Page
                  |                         |
                  +------------+------------+
                               |
                               v
                       Apache HTTP Server
                               |
                               v
                          Web Browser


                    Administrator Desktop
                               |
                            SSH - 22
                               |
                               v
                          Amazon EC2
                               |
                               v
                         PuTTY Terminal
                               |
                               v
                      Linux Administration
```

**Architecture Description:**

This architecture demonstrates automated deployment of an Apache web server on an AWS EC2 instance running Amazon Linux 2023.

- **HTTP (Port 80):** Allows internet users to access the hosted website.
- **AWS Security Group:** Controls incoming traffic to the EC2 instance.
- **Amazon EC2:** Provides the virtual Linux server.
- **Cloud-init / User Data:** Executes startup configuration automatically.
- **Bash Automation:** Automates Apache installation and HTML page creation.
- **Apache HTTP Server:** Hosts and serves the website.
- **SSH (Port 22):** Allows the administrator to securely connect to the EC2 instance using PuTTY.
- **Linux Administration:** Allows the administrator to manage and configure the server.

###  7. Implementation Methodology


###  AWS Console Login & Access
Opened the AWS Management Console,Viewed the dashboard and recently visited services.

<img width="1345" height="590" alt="Screenshot 2026-10-14 191643" src="https://github.com/user-attachments/assets/d9f2fa0d-f234-4922-ae07-d4b9d73d10b6" />

### AWS Account Sign-In
- Selected Root or IAM user.
- Entered the registered email address.
- Proceeded to AWS account login.
<img width="1332" height="624" alt="Screenshot 2026-10-14 191723" src="https://github.com/user-attachments/assets/ded6ee3d-8006-418a-9b86-d0ce12778aff" />

###  Password Verification
The Root User sign-in page prompts the account owner to enter their account password to verify authentication and gain full access to the AWS console.
<img width="1366" height="610" alt="Screenshot 2026-10-14 191755" src="https://github.com/user-attachments/assets/bcc7a6fa-4018-463d-8cf3-7ea55bddf709" />


###  Identity Verification (MFA)
The Multi-Factor Authentication (MFA) page requires the user to submit a time-based verification code from an authenticator app (such as Google Authenticator) to complete login access to the console.
<img width="1366" height="619" alt="Screenshot 2026-10-14 192020" src="https://github.com/user-attachments/assets/405034f8-88b0-4d8a-ba8b-f9ec76ce681c" />

###  Password Recovery Verification
The Password Recovery page verifies account ownership by requiring the user to complete a CAPTCHA security challenge before sending password reset instructions to the registered email address.
<img width="1347" height="623" alt="Screenshot 2026-10-14 192225" src="https://github.com/user-attachments/assets/f6fcb1fc-52aa-4657-8f04-78940dec0460" />

###  IAM User Authentication
The IAM user sign-in page allows non-root users to log in by providing their AWS Account ID (or alias), individual IAM username, and password to gain access according to their assigned permissions.
<img width="1339" height="517" alt="Screenshot 2026-10-14 192744" src="https://github.com/user-attachments/assets/72cf7558-f8b3-434e-8c55-babb5b022769" />

###  Console Home Dashboard
The AWS Console Home dashboard provides a customizable workspace showing recently visited services (such as IAM), global AWS Health status, region selection (Europe Stockholm), and direct search access to all cloud services[cite: 7].
<img width="1347" height="592" alt="Screenshot 2026-10-14 192840" src="https://github.com/user-attachments/assets/b224cfbf-bdf1-41ab-821d-0b7077977160" />

###  Bot Prevention & Security Verification
The Security Verification modal displays a CAPTCHA challenge during sign-in to verify human interaction and prevent automated bot access before allowing login authorization to proceed.
<img width="1366" height="632" alt="Screenshot 2026-10-14 193144" src="https://github.com/user-attachments/assets/8bc6ec35-8649-4617-b417-8af16701079e" />

###  Central Service Navigation
The Console Home dashboard displays the active deployment region (**United States Oregon**), key management widgets, account health monitoring, and quick navigation links to recently accessed services including **IAM**, **EC2**, and **Billing and Cost Management**.
<img width="1349" height="598" alt="Screenshot 2026-10-14 193357" src="https://github.com/user-attachments/assets/ef07caba-f76d-42ce-a72c-c6ea76c35d99" />

###  Service Search & Selection
The AWS Console global search bar allows administrators to locate and navigate directly to core cloud services, featuring quick links to **EC2 (Virtual Servers in the Cloud)**, **Instances**, **Launch templates**, and related compute tools.
<img width="1366" height="601" alt="Screenshot 2026-10-14 195227" src="https://github.com/user-attachments/assets/8399602c-a074-4870-9846-3b221f0210f0" />

###  Compute Service Navigation & Provisioning Initiator
The Amazon Elastic Compute Cloud (EC2) service page provides the entry point to create, manage, and monitor virtual servers in the cloud, featuring the primary **Launch instance** button to initiate virtual machine deployment.
<img width="1349" height="593" alt="Screenshot 2026-10-14 195307" src="https://github.com/user-attachments/assets/8293989a-5124-461a-a83a-f0019c2c9574" />

###  EC2 Instances Dashboard
The EC2 Instances dashboard serves as the central control panel for monitoring active virtual servers, displaying instance status checks, health metrics, and the primary **Launch instances** button to provision new virtual machines.
<img width="1366" height="602" alt="Screenshot 2026-10-14 195323" src="https://github.com/user-attachments/assets/d254a902-82fc-45d0-81f6-4b7ff0084531" />

###  Instance Configuration & AMI Selection
The "Launch an instance" page initiates virtual machine deployment, allowing administrators to specify instance names, select OS images (such as Amazon Linux 2023 AMI), configure hardware instance types (t3.micro), set firewall rules, and allocate storage volume.
<img width="1366" height="600" alt="Screenshot 2026-10-14 195402" src="https://github.com/user-attachments/assets/d9e9a829-f03e-48a9-8e2b-0b767af990c3" />

### AMI Operating System Selection
The Application and OS Images section defines the base operating system for the instance, selecting **Amazon Linux 2023 kernel-6.18 AMI** (Free tier eligible) to provide the baseline runtime environment for deployment[cite: 14].
<img width="1366" height="575" alt="Screenshot 2026-10-14 195424" src="https://github.com/user-attachments/assets/d2588260-8fc5-4da2-a5f4-12c1828ba28b" />

###  Instance Type & Key Pair Configuration
The Instance type and Key pair section configures the hardware profile by selecting **t3.micro** (2 vCPU, 1 GiB Memory, Free tier eligible) and sets up administrative access by attaching or generating an SSH key pair for secure terminal connections.
<img width="1366" height="602" alt="Screenshot 2026-10-14 195451" src="https://github.com/user-attachments/assets/b577933d-9696-4deb-91a1-fe91ff9edaec" />

####  Network & Key Pair Configuration
The Key pair and Network settings section assigns an SSH key pair for authentication and configures VPC networking parameters, including default subnet placement, enabling Auto-assign public IP, and setting up firewall rules via security groups.
<img width="1366" height="602" alt="Screenshot 2026-10-14 195534" src="https://github.com/user-attachments/assets/bedb6a81-99ea-454e-ba0b-e3d79fcc2379" />

#### Key Pair Creation & File Format Selection
The Create key pair modal allows administrators to generate a new cryptographic key pair by assigning a custom name, selecting the key algorithm (**RSA** or ED25519), and choosing the private key format (**`.pem`** for OpenSSH or `.ppk` for PuTTY) for secure instance access.
<img width="1366" height="599" alt="Screenshot 2026-10-14 195558" src="https://github.com/user-attachments/assets/e3ee9705-c3c7-49bc-a503-11d17fffaec8" />

#### Key Pair Selection Applied
The key pair dropdown displays the selected cryptographic identity **(`Linux-pratu`)** assigned to the instance, working alongside VPC network settings **(`vpc-07587356409da0db4`)**, default subnet placement, and enabled public IP assignment to establish secure connectivity channels.
<img width="1366" height="692" alt="Screenshot 2026-10-14 195652" src="https://github.com/user-attachments/assets/2e7e70e0-8da1-41b7-a628-a4b0b8404a55" />

#### Inbound Security Group Rules
Firewall & Network Traffic Configuration
The Inbound Security Group Rules section configures virtual firewall policies, setting up **SSH (TCP Port 22)** access for administrative terminal control and **HTTP (TCP Port 80)** access for web server traffic from **anywhere (0.0.0.0/0).**
<img width="1366" height="691" alt="Screenshot 2026-10-14 195809" src="https://github.com/user-attachments/assets/93f2bba4-2a69-4698-b3c0-19a1fb1661ee" />

#### Additional Security Group Rules (HTTPS & Custom UDP)
-  Advanced Firewall & Network Rule Configuration
The inbound security group configuration includes **HTTPS (TCP Port 443)** for secure web traffic and a **Custom UDP (Port 22)** rule, allowing flexible network traffic policies across the security group summary pane.
<img width="1366" height="599" alt="Screenshot 2026-10-14 200057" src="https://github.com/user-attachments/assets/b0dfdd40-939d-48ac-b2b3-4ba2d6ab7305" />

###  User Data Bootstrap Script
-  Post-Provisioning Automated Web Server Configuration
The optional User Data section allows inputting a shell script to automate package management and web server installation upon instance bootup, executing updates, configuring Apache **(`httpd`),** and provisioning a custom landing page **(`index.html`).**
<img width="1366" height="597" alt="Screenshot 2026-10-14 200736" src="https://github.com/user-attachments/assets/8e7f7a7b-b93e-416d-b35d-4f1e82c9c439" />

| Command | Description |
| :--- | :--- |
| `#!/bin/bash` | Defines the Bash shell interpreter. |
| `dnf update -y` | Updates all installed system packages to the latest versions without manual confirmation. |
| `dnf install -y httpd` | Installs the Apache HTTP Web Server package automatically. |
| `systemctl start httpd` | Starts the Apache HTTP Web Server service. |
| `systemctl enable httpd` | Configures the Apache service to automatically launch upon system boot. |
| `echo "..." > /var/www/html/index.html` | Creates and writes the default HTML index webpage. |

#### EC2 Instance Launch Success
1. Successfully launched the EC2 instance.
2. Verified the launch confirmation.
3. Viewed post-launch configuration options.
<img width="1366" height="603" alt="Screenshot 2026-10-14 200853" src="https://github.com/user-attachments/assets/48e38e4e-ff7d-4dc4-89db-cb939f0633fc" />

#### Post-Launch Management Options
1. Enable CloudWatch monitoring.
2. Configure load balancing.
3. Set AWS budget alerts.
4. Create CloudWatch alarms.
<img width="1351" height="597" alt="Screenshot 2026-10-14 200921" src="https://github.com/user-attachments/assets/e8f6d587-c77a-40aa-9bec-d2e3dd21fbbb" />

#### EC2 Instance Status Verification
1. Checked the **EC2 instance ID.**
2. Verified the **instance was Running.**
3. Confirmed the instance type **(t3.micro).**
4. Checked the instance status.
5. Viewed the Availability Zone **(us-west-2b).**
<img width="1366" height="341" alt="Screenshot 2026-10-14 200956" src="https://github.com/user-attachments/assets/ba7fcdd5-be54-429e-b65b-4f03817ac918" />

####  Instance Inspection & Network Addressing
* **Instance ID:** `i-0c1556c9a5297e8b0`.
* **Instance State:** **Running**
* **Instance Type:** `t3.micro`.
* **Auto-assigned IP Address:** `52.39.101.116 [Public IP]`.
* **Public DNS:** `ec2-52-39-101-116.us-west-2.compute.amazonaws.com`.
* **VPC ID:** `vpc-07587356409da0db4`.
  <img width="1366" height="605" alt="Screenshot 2026-10-14 201135" src="https://github.com/user-attachments/assets/6f2144b7-6f0e-4a9f-99d7-56f9a07197a5" />

#### Instance Stopping State
Instance Lifecycle Management & Shutdown
* **Notification:** Successfully initiated stopping of instance `i-0c1556c9a5297e8b0`.
* **Instance State:** **Stopping**.
* **Availability Zone:** `us-west-2b`.
* **Public IPv4 Address:** `52.39.101.116`.
* **Private IPv4 Address:** `172.31.31.91`.
<img width="1366" height="595" alt="Screenshot 2026-10-14 201458" src="https://github.com/user-attachments/assets/b9f488ef-b818-4ce6-885e-07f0d0da2b73" />


#### Web Server Deployment Verification
 Verification & Live Output Testing
 **Rendered Landing Page:** Successfully loaded the Apache web server HTML index page displaying **"Welcome to My AWS Webserver"** via the instance's public IP address.
 <img width="1356" height="472" alt="Screenshot 2026-10-14 202343" src="https://github.com/user-attachments/assets/68bb51ea-5f14-4901-96e2-2eff30747427" />

 ###  PuTTY Configuration - SSH Session Setup
 Remote Terminal Connection & Access
* **Host Name (or IP Address):** `54.244.57.147`.
* **Port:** `22`.
* **Connection Type:** **SSH**.
  <img width="451" height="435" alt="Screenshot 2026-10-14 202556" src="https://github.com/user-attachments/assets/c6b207cc-bdfd-4675-ba60-c08eb5a79d62" />

 #### SSH Terminal - Directory Navigation & Web Root Verification
 Phase: Remote Terminal Verification & Directory Inspection
 The terminal session successfully authenticates via public key **(Linux-pratu)** into Amazon Linux 2023, navigating through the file system 
 **(/var/www/html)** to verify the presence of the deployed **index.html file.**   
<img width="1366" height="768" alt="Screenshot 2026-10-14 203447" src="https://github.com/user-attachments/assets/bf72f006-af33-49c4-814f-f846d788c559" />

####  EC2 Instance State Management
1. Opened the Instance State menu.
2. Viewed Stop, Reboot, and Terminate options.

   <img width="1366" height="600" alt="Screenshot 2026-10-14 203742" src="https://github.com/user-attachments/assets/acd459bd-4b27-4e57-bf9e-038b1c46e51e" />


#### EC2 Instance Stop Confirmation
The confirmation window asks the administrator to confirm stopping the EC2 instance. It also explains that some charges, such as EBS storage and Elastic IP addresses, may continue even after the instance is stopped.

<img width="1366" height="596" alt="Screenshot 2026-10-14 203759" src="https://github.com/user-attachments/assets/98f65b22-18f2-4ae8-8bbc-f089c87fb4b6" />

####  Instance Termination
Resource Cleanup & Instance Deletion
*Selected Action:* Terminate (delete) instance selected from the Instance state dropdown menu for instance i-0c1556c9a5297e8b0 to permanently remove the virtual server and avoid ongoing resource charges.




Phase: EC2 Instance Termination
The confirmation window asks the administrator to permanently terminate the EC2 instance. It warns that the root EBS volume and local storage may be permanently deleted. Click Terminate (delete) to complete the cleanup.

<img width="1366" height="603" alt="Screenshot 2026-10-14 203925" src="https://github.com/user-attachments/assets/f08f38b3-a96a-4a2a-a07d-983f26a92f57" />


#### Key Learnings & Practical Skills Gained
Through this project, I gained hands-on experience with AWS EC2 deployment, Linux server administration, and cloud infrastructure management.
I learned how to configure EC2 instances, select Amazon Linux 2023, and manage security groups.
I also learned to automate Apache installation using Bash scripts and EC2 User Data, deploy a custom webpage, and access the server remotely using PuTTY.
Additionally, I understood EC2 instance lifecycle management, resource cleanup, and AWS cost optimization.

#### Future Enhancements
1. **HTTPS Configuration:** Secure the website using SSL/TLS certificates.
2. **Domain Integration:** Connect a custom domain name to the EC2 web server.
3. **Load Balancing:** Use an Application Load Balancer to distribute incoming traffic.
4. **Auto Scaling:** Automatically increase or decrease EC2 instances based on demand.
5. **CloudWatch Monitoring:** Monitor server performance, CPU utilization, and system health.
6. **Advanced Security:** Implement IAM roles, least-privilege permissions, and improved network security.
7. **Infrastructure Automation:** Use AWS CloudFormation or Terraform to automate infrastructure deployment.
These improvements can make the project more scalable, secure, reliable, and suitable for real-world cloud environments.

#### Disclaimer
This project was developed in a personal AWS environment for educational purposes and hands-on cloud infrastructure learning.
The implementation focuses on EC2 provisioning, Linux administration, Bash automation, Apache deployment, and basic network security.
All screenshots and documentation are intended to demonstrate the practical learning process.
No passwords, MFA codes, private keys, AWS credentials, or other sensitive information should be published.
This project is a learning exercise and does not represent a fully production-ready cloud infrastructure deployment.
