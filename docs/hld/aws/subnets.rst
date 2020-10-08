Subnets
----------------------------------------------------------------

The following section defines the overall subnets placement for MeBeFake’s SRE Managed AWS cloud
platform. Subnets design is key to MeBeFake AWS implementation as it sets a foundation for MeBeFake’s
infrastructure on the AWS platform. Hence any modification should be minimised where possible to
prevent additional costs to migrate workloads.

Further to this, MeBeFake is establishing a pattern for each VPC to simplify overall network architecture,
ensure consistency and aid repeatability. Three logical tiers are proposed: public, private and
protected as follows:

+---------------+-------------------------------------------------------------------------------+
|Tier           |Description                                                                    |
+===============+===============================================================================+
|Public tier    |The Public tier will include Public subnets. This subnet type is targeted for  |
+               +                                                                               +
|               |instances that support inbound connections from the internet through an AWS    |
+               +                                                                               +
|               |Internet Gateway (for example, Web Application Firewall (WAF) servers).        | 
+               +                                                                               +
|               |Public subnets have been provisioned in anticipation that internet facing      |
+               +                                                                               +
|               |workloads will be deployed to these subnets in the future                      |
+---------------+-------------------------------------------------------------------------------+
|Private tier   |The Private tier will include Private subnets. This subnet type is targeted for|
+               +                                                                               +
|               |internal web servers and application servers that have private IP addresses.   |
+               +                                                                               +
|               |Instances in a Private subnet will not support inbound internet connections.   |
+---------------+-------------------------------------------------------------------------------+
|Protected tier |Instances in a Private subnet are accessible to MeBeFake on-premise networks.  |
+               +                                                                               +
|               |The Protected tier will include Protected subnets. This subnet type is         | 
+               +                                                                               +
|               |designated for EC2 instances with database(s) and can only be accessed by      |
+               +                                                                               +
|               |servers in the Private tier.                                                   |
+---------------+-------------------------------------------------------------------------------+

**For detailed Network Subnet definitions please refer to the Network Subnets tab in the *ne1MBF*
Data spreadsheet.**
