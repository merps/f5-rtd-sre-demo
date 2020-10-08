Security Groups
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Security groups are a stateful firewall used to control traffic entering or leaving an instance or
groups of instances. Outbound traffic for all EC2 instances will be allowed out without filtering,
however for Inbound traffic connections will be restricted to improve instance security

**MeBeFake Security Group Standards:**

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

**For detailed Network Security Groups definitions please refer to the Security Groups tab in
the *ne1MBF* Data spreadsheet.**