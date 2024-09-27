AWS Session 1 - 26 Sep 2024 (2PM to 6PM)

On Prem / Cloud

Private, Public, Hybrid, Corporate


https://aws.amazon.com/about-aws/global-infrastructure/regions_az/

https://aws.amazon.com/compliance/data-center/data-centers/


Regions -> Avalability Zones (az) -> Data centers
Logical Units


Data Centers are protected. AWS does not disclose how many data centers are available in Avalibality Zones(does not disclose location for AZ)

az are always tried available.
Each az is atleast 60km apart


### EC2 - Elastic Web Scale Computing
virtual server
scalable computing capacity, pay for what you use

Instances - virtual server
AMI - Amazon Machine Images 
  - Details of OS, softwares installed on it.
  - AWS has pre-built AMIs, we can create own AMI
Instance Types - https://aws.amazon.com/ec2/instance-types/
  - generate purpose like m5.large, m5.xlarge etc
  - compute optimised for batch processing, video transcoding, etc (c8a...)
  - memory optimised - process large data set in memory (r5a....)
  - Accelerated Computing - Has GPUs, etc (p5...)
  - AWS Compute Optimiser - helps identify over provisioning/under provisioning

EC2 Key Pair - when aws allots a machine, aws will have a public key and share the **private key**. Prove your identity.

Instance Store - Temporary storage option. 

Elastic Block Store - Permanant storage option.

Security Group - combination of inbound rule and outbound rule. 
 - Inbound Rule - what can come in
 - Outbound Rule - what can go out

Public IP - default 1 Public IP addrtess is allocated, reachable over internet.

Private IP - default 1 is allowed, 

Elastic IP - It is Public IP. Why we need it? Public Ips are got from AWS Pool IPs. When you stop/restart instance, Public IP is deallocated. And when started gain new Public IP IP is allocated. Static IP - or mapping between a static IP(unchnaged IP) and public IP. 

Tags -  metadata, Helps with IAM?

VPC - Virtual Private Cloud, Virtual Networks. Logically Isolated Networks from AWS Cloud. 



Advantages - 
 - Complete Control.
 - ...


### LAB 1
- use us-east-1 region
- Select AMI
  - Microsoft Windows Server 2022, Free
  - ami id is diff in diff region
- t2.medium - 2 vCPUs and 4 GB Mem
- Key Pair  - Create new key Pair, .pem (windows), .ppk (linux with putty)
- Netwoking settings - do nothing for now
- configure storage - 30 GiB gp2 root volume
- number of instances 1
- Launch instance
- Will take  1-2 min

- - Security Group - Add rule, allow HTTP, Custom, 0.0.0.0/0

- Actions > Security > Get Window Password > Upload .pem file > Decrypt password > password -  iBO0K0fKZH9I3Ge1EA%V.pyXAa*-%b!X
- Select instance > connect > RDP Client (port 3389) > download remote desktop file ..... put password .... 

- Server Manager > Select Server roles > IIS > next ... > 

The above process is manual.
- EC2 User Data.
- Execute your script  powershell script


https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connecting_to_windows_instance.html
------


https://www.putty.org/

- launch new instance with linux - use ppk new 
- port 22
- ec2-user
- yum install httpd -y #(apache web server)

