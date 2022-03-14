# Summary

- Geography - usually a country and has at least 2 regions
- Azure Region - area within a geographical boundary; regions are hundreds of miles apart
- Datacenter - physical building within a region with its own power, cooling supply, water supply, generators and network
- Latency Boundary - round-trip latency between two regions no greater than 2ms
- Ensuring High Availability - deploy Azure resources to multiple regions
- Availability Zones - allow resources to be deployed into separate datacenters in a region; at least 3 availability zones in each region
- Resource Groups - separate Azure resources in a logical way and tag resources for easier management
- Azure Subscription - required to create Azure resources; additional subscriptions can be created under the same account; helps with reporting on resources easily
	- Have limits
- Management Groups (permissions) - assign policies and access control to Azure resources
	- Can only contain management groups or subscriptions
- Azure Resource Manager (ARM) - used by Azure management tools to create and manage Azure resources
	- Uses resource providers to create and manage resources
- ARM Template - ensure consistency of large Azure deployments
- Azure Virtual Machines (IaaS) - manage the operating system and configuration
- Availability Sets - protects VMs with fault and update domains
	- Fault Domains - protect VMs from hardware failure in a hardware rack
	- Update Domains - protect from VM reboots
- Scale Sets - auto-scale rules to scale horizontally (scaling out) when needed
- Azure App Service (PaaS) - makes hosting web apps in the cloud because it's PaaS and removes management burden from user
- App Service Plan - used to run App Service apps and specifies # of VMs and their configurations
- Containers - create an image of an application and everything needed to run it
- Azure Container Instances (ACI) - run containers cheaply
- Azure Kubernetes Service (AKS) - manage service that makes it easier to host Kubernetes clusters in the cloud
- Windows Virtual Desktop (WVD) - remote access to applications and OSes to multiple users from almost any device
- Azure Virtual Network (VNet) - allows Azure services to communicate with each other and the internet
- Public IP Address for VNets - used for inbound internet connectivity to allow other people to access it
- Azure Load Balancer - distribute traffic across multiple VMs in the VNet
- ExpressRoute - allows high-bandwidth connection to Azure of up to 10 Gbps by connecting to the Microsoft Enterprise Edge (MSEE) router
	- This traffic doesn't travel over the internet
- Azure Blob Storage - good storage option for unstructured data like binary files
	- Storage Tiers
		- Hot 
		- Cool
		- Archive
- Azure Data Box - moves large amount of data to Azure Blob Storage
	- Hard drives shipped to you from Microsoft
- Azure Disk Storage - virtual disk storage for Azure VMs
	- removes management burden of disks
- Azure Files - disk space in cloud that is mapped to an on-premises drive
- Azure Cosmos DB - NoSQL database in the cloud for unstructured data
- Azure SQL Database - relational database system in the cloud completely managed by Microsoft
- Azure Database for MySQL - based on Community Edition of the open-source MySQL database system
	- removes management burden from the user
- Azure Database for PostgreSQL - managed service for hosting PostgreSQL database
- Azure Marketplace - source of templates for creating Azure resources provided by Microsoft and 3rd-party providers

## Charts

| DTU Model | vCore Model |
| --------- | ----------- |
| (1) Don't need high degree of flexibility (2) Fixed pricing | High level of visibility and control of db resources (CPU, memory) |
| Pre-configured limits for transactions against DB, storage, CPU and memory configurations | Flexibility in CPU power, memory, storage, etc. |
| Basic, Standard & Premium Tiers | General Purpose Business Critical |
| Backup storage and long-term retention of data costs additional | Backup storage and long-term retention of data costs additional |

## Resources

- Changes in Azure
- Azure Status Page
- Moving Resources Between Groups
- Azure Subscription Limits
- ARM Template Docs
- Custom Images
- Docker
- Windows Virtual Desktop
- Azure Files
- Purchasing Models