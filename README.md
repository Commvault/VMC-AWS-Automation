# VMC on AWS Automation

This Automation POC script offers ability to onboard Tenants to an MSP(Managed Service Provider) environment seeking VMC Backup Solution.


## Prerequisites:

The CommServer and the VMC SDDC should have direct connection between each other.
Minimum SP(Service Pack) level - SP19

## Steps to Follow:

1) Download all the files from the above repository.
2) Download the <a href="https://commvaultapplicanceova.s3-us-west-2.amazonaws.com/commvaultappliance.ova" onclick="return ! window.open(this.href);">ova file</a> and copy it to the VSA Proxy machine which would be used for deployment of Tenant Proxy+MA on the SDDC.
3) Install vmware ovf tools from the below location on the same deployer proxy machine where the .ova file is placed.    	
	OVF Installer location - https://code.vmware.com/web/tool/4.4.0/ovf (For Windows use the following path as installation folder - C:\Program Files\VMware\VMware OVF Tool)
4) Import the following workflows and deploy in the same order as below.	
	### Workflows:
	1) DeployVM
	2) CreateVirtualizationClient
	3) CreateCLoudLibrary
	4) CreatePlan
	5) OnBoardSDDC
	
	To Import workflow follow -> http://documentation.commvault.com/commvault/v11/article?p=49632_1.htm  
	To Deploy workflow follow -> http://documentation.commvault.com/commvault/v11/article?p=49597_1.htm
	
5) Import the postman collection file and create a dummy environment for runtime storage of variables.
	Right click the collection and click Edit -> Pre-request Scripts tab, change the variable values according to the environment.
	Run the APIs in the below order to Onboard a Tenant.
	1) POST Login 
	2) Create customer in CommServer
	3) Generate AuthCode
	4) Create SDDC
	

