# Skill 1.3: Describe the differences between public, private, and hybrid cloud models

- Cloud computing
	- Definition
		- Common - infrastructure and applications accessible over the internet.
		- Better - many computing resources all connected by a network. 
			- Systems that are scalable, agile and so forth.
			- Distributed computing resources accessible on a network
- Public cloud - traditional cloud model available over the public internet.
	- AKA multi-tenant environment
	- Shared infrastructure available on a public network
	- Network, storage, VMs used by your app are provided by a cloud provider and shared between all consumers of a public cloud
	- Public clouds - Microsoft Azure, Amazon Web Services (AWS) and Google Cloud Platform
	- Access usually requires authentication
	- Advantages
		- Easy and fast to move to the public cloud because provider already has the infrastructure in place
		- Scale quickly and efficiently because provider has resources provisioned and ready for your use when needed
		- Control costs
		- Flexibility and convenience
	- Disadvantages
		- Must give up some control of infrastructure when using the public cloud
		- Security concerns with operating in the public cloud
			- Must have security measures in place and the ones provided by the cloud provider may not be up to your standards or requirements.
		- Locked into a specific configuration defined by the cloud provider
- Private cloud - infrastructure dedicated to a business, organization or group.
	- AKA single-tenant environment
	- Scalable and elastic
	- Private environment dedicated to a single company
		- On-premises environment (business owns infrastructure) or third-party environment (provider owns infrastructure)
			- Can be on-premises or in cloud
	- Advantages
		- Privacy of infrastructure and data
		- Regulatory concerns (i.g. banks, hospitals, cruise ship industries)
	- Disadvantages
		- On-premises infrastructure costs money
		- Lose control of security of data when using a 3-rd party environment
			- Can't guarantee all of your data will be secure
- Hybrid cloud - mixture of public and private cloud models.
	- Examples
		- App running within public cloud but data stored on-premises in a private cloud
		- Application on private cloud but services and infrastructure located in a public cloud
		- Keep expensive to move legacy systems private while building out public cloud presence
	- Technologies to connect private and public clouds
		- Virtual Networks
		- Hybrid Connections
		- Service Bus
	- Disadvantages
		- Compatibility - Must ensure data shared between public and private clouds are compatible
		- Networking complexities - can be difficult to troubleshoot
		- May cause application slowdowns due to geographical distance
	- Services
		- Azure Stack - run Azure services on-premises (sold as a package)
- Community cloud - similar to private clouds but resources are dedicated to a community of companies instead of one company.
	- e.g. hospitals, financial institutions, etc.
	- This will NOT be on the AZ-900 exam


Additional Info

- Cloud Design Patterns