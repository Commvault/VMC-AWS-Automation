# VMC on AWS Automation

This Automation POC script offers ability to onboard Tenants to an MSP(Managed Service Provider) environment seeking VMC Backup Solution.


## Prerequisites:

	1)Workflow engine needs to be installed on the same node as deployer machine.
	2)Set additional setting ValidateSSL under WFEngine to 0 on workflow engine machine(deployer).
Minimum SP(Service Pack) level - SP22

## Steps to Follow:
1) Download all the files from the above repository.
2) Download the <a href="https://commvaultappliance.s3-us-west-2.amazonaws.com/commvaultappliance.ova" onclick="return ! window.open(this.href);">ova file</a> and upload to content library, have it subscribed to the on-boarding SDDC on VMC.
3) Import the following workflows and deploy in the same order as below.	
	### Workflows:
	1) DeployVM
	2) CreateVirtualizationClient
	3) CreateCLoudLibrary
	4) CreatePlan
	5) OnBoardSDDC
	
	To Import workflow follow -> http://documentation.commvault.com/commvault/v11/article?p=49632_1.htm  
	To Deploy workflow follow -> http://documentation.commvault.com/commvault/v11/article?p=49597_1.htm
	
4) Import the postman collection file and create a dummy environment for runtime storage of variables.
	Right click the collection and click Edit -> Pre-request Scripts tab, change the variable values according to the environment.
	Run the APIs in the below order to Onboard a Tenant.
	1) POST Login 
	2) Create customer in CommServer
	3) Generate AuthCode
	4) Create SDDC
	

