# AWS-3-Tier-Architecture

# Step1. Let's first build the foundations
 I. Create a VPC
    We need to build a VPC, an Internet gateway, a NAT gateway, Route tables, Two Availability zones. 2 public subnets, and 4 private subnets.
    VPC is the framework and it is the essential feature that allows communication to the internet through an internet Gateway.

 II. Subnets
    As shown in the diagram. There are 3 Tiers. A web tier with two public subnets. Application tier with two private subnets and Database tier with two private            subnets. It is being deployed across two availability zones (AZ).


 III. Create an Internet Gateway
    An internet gateway enables resources in your public subnets (such as EC2 instances) to connect to the internet if the resource has a public IPv4 address. We can     create an internet gateway and attach it to our VPC.

 IV. Create NAT Gateway!
    NAT Gateway is a highly available AWS-managed service that makes it easy to connect to the Internet from instances within a private subnet in an Amazon Virtual       Private Cloud (Amazon VPC).

 V. Create Route Tables.
    A route table contains a set of rules, called routes, that determine where network traffic from your subnet or gateway is directed. We need one public route          table   (with 2 public subnets) and one private route table.

# Step 2. Create a Web-Tier

 I. Launch Template
    A launch template is similar to a launch configuration, in that it specifies instance configuration information. It includes the ID of the Amazon Machine …

 II. Web Tier Auto Scaling group
  An Auto Scaling group contains a collection of EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management. An Auto   Scaling group also lets you use Amazon EC2 Auto Scaling features such as health check replacements and scaling policies.

# Step 3. Create an Application — Tier

I. Launch Template > Create a new template name: 3TierTemplate2 > Template version: AppTierTemplate > Auto scaling guidance: check “Provide guidance” > Quick       Start > Amazon Linux 2AMI (Free tier eligible) > Instance Type t.2 micro (Free tier eligible) > KeyPair: ProjectKEYpair.
    
 II. Application Tier Auto Scaling Group
    Create a new ASG name: 3TierAutoScalingGroup2 > Lauch Template: 3TierTempalte2 > Next

# Step 4. Create a Database — Tier
   1. Use a free Tier MySql RDS Database.
   2. The Database Security Group should allow inbound traffic for MySQL from the Application Server Security Group.
   3. 2 private subnets.
   4. Associate with a private route table.
      Note: No need to use Multi-AZ but be sure to document how you would add it.
   5. Remember that when diagraming this tier you are only creating one RDS instance in one subnet even though you are creating two subnets. If you use multi-az or       a read replica then and only then should you have a second instance. Make sure to label accordingly.

# I have officially completed all tasks in the project and successfully built my own three-tier architecture!

![image](https://github.com/Deepchand123/AWS-3-Tier-Architecture/assets/108334863/b2755093-17b1-4a92-88e6-5245be438575)

















  
