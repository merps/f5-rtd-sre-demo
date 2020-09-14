Site Reliability Engineering (SRE) Demo (WIP)
==================================================================

This document describes the use of F5 Networks SaaS service, Beacon, along with other products from
the F5 portfolio and OpenSource tools are used in conjuction to provide insights for Holistic IT 
Governance.

This document was created as part demonstration platform design and build.  The contents of the 
document consists of architecture references and detailed instructions on how to replicate.

Site Reliability Engineering (SRE) platform consists of multiple Cloud Service Provide (CSP)
deployments alongside a replication of a privately hosted Data Center (DC) environment.

The demonstration spans across mutliple regions and availablity zones of CSP's and a singular DC 
environment to imiate an Application's - Customer Portal (WordPress) - journey from OnPremises to 
PublicHybrid deployment model.

This is a holding page for code here:
https://github.com/merps/f5devops/tree/f5-sre-demo/terraform/f5-sre-demo


.. toctree::
   :maxdepth: 4
   :glob:

   html/about.rst
   html/cusomer.rst
   onprem/*
   aws/*
   images/* 
   examples/*