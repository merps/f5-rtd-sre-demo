Customer MeBeFake 
==================================================================

Customer Profile
------------------------------------------------------------------
A random name for a random organisation and ABC Co. is **truly** overused, this example customer 
operates in the Large SMB market that has an Public Internet precense for online training and marketting.

It is estatimated that MeBeFake has over 500 staff and are looking to begin their multi-cloud journey
with a three (3) year plan of to have sixty (60) percent of workloads bursting to CSP environments.


Customer Objectives
------------------------------------------------------------------
In a galaxy far, far, away someone had a *terrible* idea of creating a php application called
Customer Application Portal (CAP - *yes, I am a sadist*).   Customer MeBeFake (MBF) currently hosts
**'ne1MBF, CAP'**, Customer Portal Application, on-premises an the primary objects of this solution is 
to:

1) Provision Infrastucture as Code (IaC) for CSP's
2) Provide Integration of a Cloud Agnostic SaaS SRE solution
3) Reduce *'tool-sprawl'*, Infrastucture and management overheads through manual processes.


Scope of Services
------------------------------------------------------------------
MeBeFake has nominated the on-premises application *'ne1MBF'* as the Lighthouse application for the 
operational theoretical exercise as per previously listed objectives.

As such this document/site will be divided into two (2) distinct sections;

1) On-premises 
    a) Production Workload Discovery 
    b) Production Automation (IaC & CI/CD flows) of Lighthouse Application Stack
    c) SRE Solution Integration of On-premises

2) AWS Deployment (CSP)
    a) Production environment for hosting public facing workloads
    b) Shared Services for hosting/deploying applications
    c) NonProduction environments for Development/Testing
    d) Management & Audit (SecOps) environment
    e) Production Automation extension from on-premises to CSP
    f) SRE Solution integration extension.


Scope of Exclusion
------------------------------------------------------------------

The following items are out-of-scope for SRE Observibility deployment:

1) Coffee, *there just isn't enough to go around*
2) Implimentation of CAP and supporting SSO/2FA integration
3) Implimentation of, yeah, something for later I guess.


Assuptions
------------------------------------------------------------------

The following assuptions have been made during the implimentation of the Lighthouse Application 
- *'ne1MBF'* - for this SRE Observibility project:

* the reader, yes - you, has an understanding of the following:
    a) Linux - SysOp experience
    b) Automation;
        1) Terraform
        2) AWS CLi
        3) GitLab/GitHub (CI/CD)
        4) Scripting languages
        5) Docker
    c) Network, specificlly F5/NGINX
    d) Monitoring;
        1) syslog-ng
        2) telegraf & influxdb
        3) telemetry streaming 
    e) *ability to rtfm*