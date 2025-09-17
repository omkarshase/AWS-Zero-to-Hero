# Why use CloudFormation (CFT) instead of CLI?

Infrastructure as Code (IaC) allows us to **define infrastructure in code** instead of manually creating resources. IaC tools act as a **middleman between the user and the cloud provider**.

When a user submits a **template** (in YAML or JSON), the IaC tool (here, CloudFormation) reads the input and translates it into **AWS API calls** to create or update infrastructure. Since CloudFormation is an AWS-native IaC tool, it supports **only AWS services** and therefore makes only AWS API calls.

---

## Declarative and Versioned Templates

- **Declarative:** A CloudFormation template describes _what the final infrastructure should look like_, not _how to build it_. In one line:  
    **Declarative means “what you see is what you get”** — by reading the template, you can understand what resources will exist after execution.
    
- **Versioned:** Templates can be stored in **Git repositories or S3 buckets**. This allows you to track changes, roll back to previous versions, and compare what the infrastructure looked like 5 or 10 days ago.
    

---

## When to use CFT vs CLI

- **CLI (Command Line Interface):**  
    Best for **quick, ad-hoc actions** such as listing S3 buckets, starting/stopping instances, or debugging issues.
    
- **CFT (CloudFormation):**  
    Best when you need to **create or manage multiple resources** together in a consistent, automated, and repeatable way.
    

---

## Why YAML is preferred

CloudFormation supports both **YAML and JSON** formats. However, YAML is widely used in DevOps because:

- It is more **readable and human-friendly**.
    
- It supports **comments** (unlike JSON).
    
- It is less verbose and easier to maintain.
    

---

## Drift Detection

CloudFormation supports **drift detection**.

- Example: You create an S3 bucket with versioning enabled via CloudFormation. Later, another user disables versioning from the AWS Console.
    
- Drift detection helps identify such **manual changes** by comparing the actual AWS resources with the CloudFormation stack definition.
    

---

## How templates are submitted to CloudFormation

1. Write a template in YAML/JSON.
    
2. Go to the **AWS CloudFormation service** in the Console.
    
3. Create a **Stack** (a logical container for resources).
    
4. Upload the template file or provide the S3/Git location.
    
5. CloudFormation then provisions the resources defined in the template.
    

---

## Structure of a CloudFormation Template

1. **AWSTemplateFormatVersion** – template format version.
    
2. **Description** – brief explanation of the stack.
    
3. **Metadata** – additional information about the template.
    
4. **Parameters** – input values you can pass when creating the stack.
    
5. **Rules** – validation rules for parameters.
    
6. **Mappings** – key-value mappings (e.g., region-to-AMI).
    
7. **Conditions** – conditional logic (e.g., create resource only in prod).
    
8. **Resources** _(mandatory)_ – actual AWS resources to create.
    
9. **Outputs** – values returned after stack creation (e.g., S3 bucket name, EC2 instance IP).