VPCs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

AWS Virtual Private Cloud (VPC) is an isolated virtual network in AWS. This virtual network
enables MeBeFake to manage the resources allocation inside the established VPCs including
implementing a secure access between MeBeFake and AWS data centres.

MeBeFake’s strategy on VPC is to utilise the Multi-VPC approach. This approach enables MeBeFake to 
set isolated boundaries based on core services being provided. This effectively establishes VPC as a
foundational platform in the MeBeFake SRE-Managed AWS platform of which workloads will be placed
into.

The VPC structure is outlined as follows:

+---------------+----------------------------------------------------+---------------+
|VPC Name       |Description                                         |TransitGateway |
+               +                                                    +Interconnect   +
|               |                                                    |               |
+===============+====================================================+===============+
|Production     |A VPC containing the Visy production and UAT        |Yes            |
+**(PRD)**      +environments                                        +               +
+---------------+----------------------------------------------------+---------------+
|Development    |A VPC containing MeBeFake's development and test    |Yes            |
+               +                                                    +               +
|(DEV)          |environments                                        |               |
+---------------+----------------------------------------------------+---------------+
|Shared Services|A VPC containing MeBeFake’s SRE shared services     |Yes            |
+               +                                                    +               +
|(SHARE)        |that hosts MeBeFake’s CI/CD framework and other     |               |
+               +                                                    +               +
|               |services such as ActiveDirectory                    |               |
+---------------+----------------------------------------------------+---------------+
|Security       |A VPC that is used for SRE Management and Audit     |No             |
+               +                                                    +               +
|Operations     |Operational Services. This VPC also provides        |               |
+               +                                                    +               +
|(SecOps)       |centralised management services.                    |               |
+---------------+----------------------------------------------------+---------------+


An AWS Virtual Private Cloud (VPC) allows an isolated virtual network created in AWS. The
address range is allocated per RFC1918 with the largest address range for a VPC being a /16
subnet. Inside a VPC, subnets are deployed in multiple availability zones (AZs) to provide support
for a highly available applications architecture. Multiple subnets are required to separate public,
private and protected subnets.

The following table highlights the network allocation for each VPC in-scope for the MeBeFake SRE-
Managed AWS Platform.

+-------------+-------------+-------------+-------------+-------------+
|Region       |VPC          |Network      |CIDR Mask    |Usable IP's  |
+=============+=============+=============+=============+=============+
|**Sydney**   |PRD          |10.92.0.0    |/18          |16378        |
|             +-------------+-------------+-------------+-------------+
|             |DEV          |10.92.64.0   |/18          |16378        |
|             +-------------+-------------+-------------+-------------+
|             |SHARE        |10.92.128.0  |/18          |16378        |
|             +-------------+-------------+-------------+-------------+
|             |SecOps       |10.92.192.0  |/18          |16378        |
+-------------+-------------+-------------+-------------+-------------+