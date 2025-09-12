

Before understanding concept of IAM first understand what is  **Authentication** and **Authorization**.
let assume example about your office 1
In an office, each employee has an ID card to enter. Each time, you have to scan that ID card, and if it has access, then only you can enter the office. So, the system verifies your identity, and this process is called **Authentication** in technical language.

Now, assume with that same ID card you try to access the Data Center or Server Room, which is a critical part of the office. It won’t be possible unless you have special access. The process of granting or verifying that a user is authorized for that area is called **Authorization**.

## Why AWS came up with IAM service

Now consider: You are a DevOps Engineer in **XYZ company**. As part of your job, you create one AWS account that stores all information related to databases, EC2 instances, servers, and other resources.

One day, a junior engineer joins your team and accidentally deletes the database which had no backup. Technically, your client data is lost completely.

To solve such issues, and to manage **Authentication and Authorization**, AWS introduced the **IAM service**.

With IAM, a DevOps admin never shares the **root account** credentials. Instead, they create new users and grant them only the required permissions according to their role and responsibilities.

---
## Main Components of IAM

There are four main sub-services in IAM:

1. **Users**    
2. **Groups**    
3. **Policies**    
4. **Roles**    

---
### 1. User

- The root user can create IAM users.    
- A user is an **authenticated person** for that particular account.    
- But, even if a user is created, they **cannot perform any action** unless a **policy** is attached.    

---
### 2. Policies
- Policies define the **permissions** for a user, i.e., what actions they can perform.    
- There are many predefined AWS-managed policies. Some examples:    

1. **AmazonS3FullAccess** → Full access to all S3 buckets    
2. **AmazonEC2FullAccess** → Full access to manage EC2 instances    
3. **AmazonRDSFullAccess** → Full access to manage RDS databases    
4. **AmazonVPCFullAccess** → Manage networking (VPC, subnets, security groups)    
5. **IAMReadOnlyAccess** → Can only _view_ IAM resources, not modify    
6. **AdministratorAccess** → Full access to all AWS services and resources    
7. **CloudWatchFullAccess** → Manage monitoring and logging in CloudWatch    
8. **AmazonDynamoDBFullAccess** → Manage DynamoDB tables and operations    
9. **AmazonS3ReadOnlyAccess** → Can only view/download objects from S3    
10. **AWSLambdaExecute** → Allows execution of AWS Lambda functions
---

### 3. Groups

Now, a question may come: _If a user has policies attached, why do we need groups?_
👉 Example:  
In your company, people are joining and resigning daily. Each employee belongs to different teams — for example: **DEV team, QA team, DB Admin team, Others**.
It would be very time-consuming to create each user individually and attach separate policies.
To solve this, IAM provides **Groups**.
- You create groups according to team responsibilities.    
- Attach the required policies to the group.    
- Then, simply add a new employee to the desired group.    
- That employee automatically inherits the permissions.
---
### 4. Roles

👉 Example:  If someone comes to your office for an interview or as a visitor, you do not give them a permanent employee ID card. Instead, you generate a **visitor pass** that is temporary and only allows access to certain areas.

Similarly, in AWS:

- A **Role** is an identity that has a set of permissions, but it is **not associated with a specific user**.   
- Roles are **temporary** and can be assumed by **users, applications, or services**.    

👉 Example in AWS:  
Suppose you are a developer and you have a DB server in a private AWS cloud. If a client requests access to the DB server, instead of creating a new user, you create a **Role** with the required permissions. The developer/application assumes the role to access the DB server securely.

**Definition:**  
In AWS IAM, a **Role** is like a user but without permanent credentials. Roles are designed to be **assumed temporarily** for accessing specific AWS resources.

---

## ✅ Steps to Create an IAM User

1. **Login to AWS Console** → Open the IAM service.    
2. **Navigate to Users** → Click _Add User_.    
3. **Set User Details** → Enter username and choose access type:    
    - _AWS Management Console access_ (username/password login)        
    - _Programmatic access_ (Access Key + Secret Key for CLI/SDK)        
4. **Set Permissions** →    
    - Attach user to an existing group, OR        
    - Attach policies directly, OR        
    - Copy permissions from another user        
5. **Review & Create** → Download credentials (.csv file with access keys).    

---
## ✅ Steps to Create an IAM Group

1. **Open IAM service** → Go to _User groups_.    
2. **Create Group** → Provide a name (e.g., _DevOpsTeam_, _Admins_).    
3. **Attach Policies** → Assign permissions (e.g., `AmazonS3FullAccess`, `EC2ReadOnlyAccess`).    
4. **Add Users to Group** → Select users to join the group.    
5. **Create Group** → All users in this group inherit the same permissions.