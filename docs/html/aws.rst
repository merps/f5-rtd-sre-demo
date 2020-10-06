AWS CSP Environment
------------------------------------------------------------------


Network Overview
==================================================================

The MeBeFake SRE AWS Platform consists of four AWS VPCs (Virtual Private Clouds) for
Production, Development, Shared Services and Security Operations Services each VPC has layer 3 
interconnects (using AWS TransitGateway) to IBM Cumberland and FujiXerox Macquarie Park DC's. 


VPCs
==================================================================

AWS Virtual Private Cloud (VPC) is an isolated virtual network in AWS. This virtual network
enables MeBeFake to manage the resources allocation inside the established VPCs including
implementing a secure access between MeBeFake and AWS data centres.

MeBeFake’s strategy on VPC is to utilise the Multi-VPC approach. This approach enables MeBeFake to set
isolated boundaries based on core services being provided. This effectively establishes VPC as a
foundational platform in the MeBeFake SRE-Managed AWS platform of which workloads will be placed
into.

The VPC structure is outlined as follows:

(table) 


An AWS Virtual Private Cloud (VPC) allows an isolated virtual network created in AWS. The
address range is allocated per RFC1918 with the largest address range for a VPC being a /16
subnet. Inside a VPC, subnets are deployed in multiple availability zones (AZs) to provide support
for a highly available applications architecture. Multiple subnets are required to separate public,
private and protected subnets.

The following table highlights the network allocation for each VPC in-scope for the MeBeFake SRE-
Managed AWS Platform.


Subnets
==================================================================

The following section defines the overall subnets placement for MeBeFake’s SRE Managed AWS cloud
platform. Subnets design is key to MeBeFake AWS implementation as it sets a foundation for MeBeFake’s
infrastructure on the AWS platform. Hence any modification should be minimised where possible to
prevent additional costs to migrate workloads.

Further to this, MeBeFake is establishing a pattern for each VPC to simplify overall network architecture,
ensure consistency and aid repeatability. Three logical tiers are proposed: public, private and
protected as follows:

-------------   --------------------------------------------------
Tier            Description
=============   ==================================================
Public tier     The Public tier will include Public subnets. This subnet type is targeted for
                instances that support inbound connections from the internet through an AWS
                Internet Gateway (for example, Web Application Firewall (WAF) servers). For MeBeFake, 
                Public subnets have been provisioned in anticipation that internet facing workloads 
                will be deployed to these subnets in the future

Private tier    The Private tier will include Private subnets. This subnet type is targeted for
                internal web servers and application servers that have private IP addresses.  
                Instances in a Private subnet will not support inbound internet connections.

Protected tier  Instances in a Private subnet are accessible to MeBeFake on-premise networks.  
                The Protected tier will include Protected subnets. This subnet type is designated 
                for EC2 instances with database(s) and can only be accessed by servers in the 
                Private tier.
=============   ==================================================


ACL's
==================================================================

Network access control lists (ACL), are an optional layer of security within the VPC layer. They are
stateless (return traffic must be allowed by rules) firewalls for controlling traffic entering and 
leaving the subnets. Security Groups provide much better security controls at a more granular level with
better debug capabilities than Network ACLs and therefore ACLs will not be used beyond the
default allow settings.


SecurityGroups
==================================================================

Security groups are a stateful firewall used to control traffic entering or leaving an instance or
groups of instances. Outbound traffic for all EC2 instances will be allowed out without filtering,
however for Inbound traffic connections will be restricted to improve instance security

MeBeFake Security Group Standards

    * Instances will generally belong to the following security groups:

        - Default security group (per tier) or a workload specific security group
        - Management security group – allows incoming traffic for management/shared services

    * Default security groups are as follows:

        - Private Default security group – allows/filters incoming traffic from the Public
        - Default security group, allows/filters incoming traffic from on-premise networks
        - Protected Default security group – allows/filters incoming traffic from the Private 
        security group
        - Within a default security group instances allow incoming traffic from all other
        instances in the same security group

Through SRE Service Requests custom security groups can be created and updates to existing
security groups can be made.

For detailed Network Security Groups definitions please refer to the Security Groups tab in
the ne1MBF Data spreadsheet.
