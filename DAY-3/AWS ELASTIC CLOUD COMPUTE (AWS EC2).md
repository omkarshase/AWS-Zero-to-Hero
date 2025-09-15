
# WHY EC2 Instance

Assume you join as a DevOps Engineer and you are the only one in the company. The company wants to build 15 new applications, so they buy 1 new physical server and ask you to create 15 virtual servers on top of that physical server. For you, it’s easy to create that—simply write a script.

But what if problems arise such as timely updates, security checks, or applying new configurations to servers? You would have to do the same task on all servers, which is very time-consuming.

Now, assume that as per requirements you have to scale up or scale down servers. With physical servers, this is very complex and costly.

To solve this problem, if you use a public cloud, you don’t need to worry about all these things, and it is also more cost-efficient compared to physical servers. That’s why most people use **EC2 service**.

---

# WHAT IS EC2

EC2 stands for **Elastic Compute Cloud**, where _compute_ is a combination of CPU, RAM, and disk—in short, a **virtual server**.

**Technical definition:**  
EC2 is a **core AWS service** that provides **resizable virtual servers in the cloud**. Think of it as renting a computer (server) from AWS, where you can run applications just like you would on a physical machine, but without worrying about buying or maintaining hardware.

---

### **Key Features of EC2**

1. **Elastic** – You can scale up (more CPU/RAM) or scale down as per demand.    
2. **On-Demand** – Pay only for what you use (per second/minute/hour depending on instance type).    
3. **Variety of Instances** – Optimized for compute, memory, storage, or GPU.    
4. **Customizable** – Choose OS (Linux, Windows, etc.), storage, networking.    
5. **Secure** – Integrated with **IAM, Security Groups, VPCs** for access control.    
6. **Different Pricing Models** – On-Demand, Reserved, Spot, Savings Plans.   

---

### **Types of EC2 Instances**

1. General Purpose    
2. Compute Optimized    
3. Memory Optimized    
4. Storage Optimized    
5. Accelerated Computing   

---

## **Steps to Launch an EC2 Instance**

1. **Login to AWS Console** → Go to the **EC2 service**.    
2. **Click “Launch Instance”** → Start the instance creation wizard.    
3. **Name & Tags** → Give your instance a meaningful name (e.g., _MyWebServer_).
    
4. **Choose AMI (Amazon Machine Image)** → Select an OS (e.g., Ubuntu, Amazon Linux, Windows).    
5. **Choose Instance Type** → Select hardware config (e.g., `t2.micro` for free tier).    
6. **Key Pair (SSH login)** →    
    - Create a new key pair or use an existing one.        
    - Download the `.pem` file to access your server securely.        
7. **Configure Network Settings** →    
    - Choose **VPC** and **Subnet**.        
    - Assign a **public IP** if you need internet access.        
    - Set **Security Group rules** (e.g., allow SSH `22`, HTTP `80`, HTTPS `443`).        
8. **Configure Storage** →    
    - Choose root volume size (default ~8 GB).        
    - Add more EBS volumes if needed.        
9. **Review & Launch** → Confirm all settings and click **Launch Instance**.    

---

### **Connect to Instance**

You can use tools like **MobaXterm, PuTTY, or VS Code**.
- Copy the **Public IP/DNS** of your instance.    
- Open terminal and run:
    `ssh -i my-key.pem ubuntu@<Public-IP>`
    
- Make sure you are in the folder where the `.pem` key is present, or provide the correct path to the `.pem` key.    

If you face an error like:  
`Permissions 0644 for 'my-key.pem' are too open`  
Run the following command to fix it:
`chmod 600 my-key.pem <file name where pem key is present>`

# **How to Access EC2 Instance from MobaXterm**

1. **Download & Install MobaXterm**
    
    - Go to the official site and download **MobaXterm (Home Edition)**.        
    - Choose the **Installer Edition**.        
    - Extract the ZIP file and install MobaXterm.        
    - Accept all conditions → Finish installation.
        
2. **Open MobaXterm & Start New Session**    
    - Launch **MobaXterm**.        
    - Click **Session → SSH**.        
3. **Enter EC2 Instance Details**    
    - **Remote Host (IP):** Enter the **Public IP** of your EC2 instance.        
    - **Username:**        
        - For Ubuntu AMI → use `ubuntu`.            
        - For Amazon Linux → use `ec2-user`.            
        - For Windows AMI → use Administrator (with RDP, not SSH).            
4. **Set Private Key for Authentication**    
    - Click on **Advanced SSH Settings**.        
    - Browse and select your **private key (.pem)** file.        
5. **Connect to EC2**    
    - Click **OK** → **Accept security prompt**.        
    - You are now **inside your EC2 instance**.