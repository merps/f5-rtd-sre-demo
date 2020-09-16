Solution Description
------------------------------------------------------------------

MeBeFake has currently has hosted infrastructure and application stacks in CoLo Data Centres at IBM
Cumberland and FujiXerox Macquarie Park that is approaching capacity.  SRE Observability of the 
current infrastructure and the expansion to Amazon Web Services will address the immediate resource 
constraints.

Overview
=================================================================

The solution is a Self-Managed platform currently established On-premises using a mix of physical 
and virtualised infrastructure and the expansion to Amazon Web Services (AWS) Public Cloud will 
allow the flexibility to extend MeBeFake company security, continuity and scalability ethos. 

MeBeFake SRE team develops, deploys and maintains the current On-premises *ne1MBF* application Stacks,
this allows MeBeFake to have full control of the application stack providing best flexibility for 
the solution.

The SRE Managed On-premsise and AWS Platform provides infrastructure in a customisable multi-cloud 
environment using:


On-premise Environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    * VMware vRealize Operations Cloud
    * VMware vSphere 6.7 
    * NetApp FAS Storage Arrays
    * F5 & Ubiquiti network appliances 


AWS CSP Environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^    
    * Amazon Virtual Private Cloud (VPC) for virtual networks
    * Amazon Elastic Cloud Compute (EC2) for virtual machines
    * Amazon Elastic Block Storage (EBS) for block storage
    * Amazon Simple Storage Service (S3) for object storage
    * F5 BIGIP & NGINX for ADC & Security services.


F5aaS CloudServices (SaaS)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    * Beacon
    * Essentials App Protect (EAP)
    * DNS Services (DNS)
    * DNS LoadBalancers (DNSLB)


The Platform will extend current on-premises environments to AWS and will consist of 4 VPCs for 
Production, Development, Shared Services and Security Operations Services. Each of these VPCs 
have high speed dedicated network connections to the AWS DirectConnect (DX) from both IBM Cumberland 
and FujiXerox Macquarie Park DC's. 

The Platform subsequently has connectivity with the MeBeFake on-premise CoLo environments levering 
both PIPE networks and GlobalSwitch.  Each of the VPCs span across three AWS Availability Zones 
(Data Centres) in the Sydney Region for high availability.

The solution includes a fully managed service consisting of:
    
    * Incident Management
    * Configuration Management
    * Patch Management
    * Anti-Virus Management
    * Monitoring
    * Auditing and Logging
    * Management of AWS Security Groups
    * Backup as a Service
    * Customer Help Desk