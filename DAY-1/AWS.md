DAY 1

- What is cloud ?
- What is private cloud and public cloud ?
- Why public cloud is more popular ?
- Why AWS popular among all cloud provider
- Trends of people going back to private cloud



Around 10–15 years ago, when you bought a personal computer, you needed separate components like a CPU, UPS, keyboard, mouse, and so on. Now imagine a company with a huge workload. In such cases, companies used to purchase servers and all the required equipment from service providers like IBM, bring them to their data centers, and configure everything for use.

The problem was that servers were very costly, and managing and configuring them was difficult. For example, let’s say XYZ company purchased 15 servers, each with 100 CPUs and 100 GB of RAM. On top of one server, they deployed a single application that only required 10 CPUs and 10 GB of RAM. That meant the remaining 90 CPUs and 90 GB of RAM went unused until required. In short, resources were not properly utilized, and the company was wasting money. If, in the future, they needed to deploy another application, they would end up buying a new server—even though their existing servers still had plenty of unused resources.

To solve this problem, **virtualization** came into the picture. Virtualization helps avoid resource wastage. For example, if you have one physical server with 100 CPUs and 100 GB of RAM, you can create multiple **virtual servers (VMs)** on top of it according to your needs. This way, you can deploy multiple applications on the same physical server, ensuring proper resource utilization.

Later, this concept evolved further: with virtualization, we can create VMs in any part of the world and share them anywhere. For example, suppose a company has its headquarters in India and a branch in the USA. If a developer in the USA requests 5 virtual servers, the system administrator can configure and provide them remotely. The developer doesn’t need to know the exact physical location of the servers but can still use the resources.

This concept is what we now call the **Cloud**.

#### In technical language What is cloud ??
Cloud is a technology that allows you to access computing resources like servers, storage, databases, and applications over the internet instead of owning and managing physical hardware. You just use what you need, pay for what you use, and scale anytime.

BUT as you see all Virtual that share with in the same organization so we called it as private cloud .

##### what is private cloud
A **private cloud** is a cloud computing environment that is used exclusively by a single organization.  in a private cloud all the resources—servers, storage, and networking—are dedicated to one organization, providing more **control, security, and customization**.


And here Companies like **Amazon, Microsoft, and Google** saw a big opportunity in cloud computing.

For example, imagine you are starting a company or running a medium-scale business. In the beginning, you might need only 10 servers. But as your business grows, you may require 50 or more servers. Managing all these servers is difficult—you would need a dedicated IT team with proper knowledge to handle configuration, setup, and maintenance.

This is where **cloud providers** stepped in. They said:

> “Don’t worry about buying, setting up, or managing physical servers. We will provide you with **Virtual Machine instances** directly over the internet.”

With **public cloud**, you don’t need to know where the actual servers are located or how they are configured. You simply request the resources—like servers, databases, or storage—and the provider gives them to you instantly from anywhere in the world. You can even choose the region where you want your resources to be deployed.

This idea of delivering IT resources **on-demand over the internet** without the burden of infrastructure management is called the **Public Cloud** concept.

##### What is  Public Cloud ??
A **public cloud** is a cloud computing environment where resources like servers, storage, and networking are owned and operated by a third-party provider (like AWS, Azure, or GCP) and shared across multiple customers over the internet. You pay only for what you use, without worrying about managing the infrastructure.

##### why public cloud is more popular ?
Public cloud is more popular because it’s **cost-effective, scalable, easy to use, and accessible from anywhere**. Companies don’t need to invest in costly servers or hire large teams to manage infrastructure—the cloud provider takes care of everything.

##### why AWS popular among all cloud provider ?
AWS is the most popular cloud provider because it was the first major player to enter the market back in 2006, giving it a huge early-mover advantage. Over the years, it has built the widest range of cloud services, covering compute, storage, databases, AI/ML, IoT, and DevOps tools, which makes it suitable for almost any business need. AWS also has the largest global infrastructure with data centers spread across many regions and availability zones, ensuring low latency, scalability, and high availability for applications worldwide. 
Another reason for its popularity is the flexibility it offers through different pricing models like on-demand, reserved, and spot instances, which helps companies optimize their costs. On top of that, AWS is highly reliable, secure, and compliant with international standards, making it trusted by startups, enterprises, and even governments. Big companies like Netflix, Airbnb, and NASA use AWS because it allows them to innovate faster, scale globally, and avoid the hassle of managing physical infrastructure. All these factors together make AWS the most widely adopted and popular cloud provider.


### Account creation on AWS Cloud 

Go to browser and Search for   [AWS sing in ](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Faws.amazon.com%2Fmarketplace%2Fmanagement%2Fsignin%3Fref_%3Dfooter_nav_management_portal%26state%3DhashArgs%2523%26isauthcode%3Dtrue&client_id=arn%3Aaws%3Aiam%3A%3A015428540659%3Auser%2Faws-mp-seller-management-portal&forceMobileApp=0&code_challenge=yJO5i9fuH-nS3z9H78jV6VNaJFaEiPAMLpyVhHESgdM&code_challenge_method=SHA-256) 
![[Pasted image 20250911120803.png]] 


as you are sing in first time  click on New to AWS ? sing up

1. **Enter Account Information**    
    - Provide your **email address**, **password**, and choose an **AWS account name**.
    - This email will be your **root user account** (use a personal email, not temporary).        
2. **Provide Contact Information**    
    - Select **Personal** or **Business** account type.        
    - Fill in your name, phone number, country/region, and address.        
3. **Payment Information**    
    - Enter a valid **credit/debit card** (required for verification, even for Free Tier).        
    - AWS may make a temporary small charge (₹2 or $1) to validate your card.        
4. **Identity Verification**    
    - Verify your phone number via **OTP or automated call**.        
5. **Choose a Support Plan**    
    - Select **Basic (Free)** plan (others like Developer or Business are paid).        
6. **Login to AWS Console**    
    - Once setup is complete, sign in as the **root user** with your email and password.        
    - You now have full access to the **AWS Management Console**.        
7. **Set Up Security (Best Practice)**    
    - Enable **MFA (Multi-Factor Authentication)** for your root account.        
    - Create an **IAM Admin User** and use it for daily tasks (avoid using root directly).