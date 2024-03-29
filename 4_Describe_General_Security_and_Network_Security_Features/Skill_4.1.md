# Skill 4.1: Describe Azure Security Features

- Azure Security Center
	- Provides confidence that security best practices are being met
	- Provides steps to keep resources configured in a way that makes them more secure
	- Can also secure on-premises resources
	- Service Tiers
		- Free Tier - general assessment and recommendations for securing your Azure resources 
			- Services Covered
				- Azure VMs
				- Azure App Service
		- Standard Tier
			- Services Covered
				- Azure SQL Databases
				- MySQL Databases
				- PostgreSQL
				- Azure Storage
				- IoT devices
				- AKS
				- Azure Container Registry
				- Azure Key Vault
			- Additional Features
				- Advanced Threat Detection
				- Analysis from Microsoft Threat Intelligence
				- Ability to Manage Regulatory Compliance of Azure Resources
			- Billing
				- Billed hourly
	- 3 Primary Areas of Coverage
		- Policy & Compliance
			- Secure Score and Overall Score show the security of your resources
			- Covers compliance with regulatory standards
			- Information provided by the service being protected
		- Resources Security Hygiene
			- High-level overview of health of your resources from a security perspective
			- Security Issue Categories
				- High Severity
				- Medium Severity
				- Low Severity
			- Information provided by the service being protected
		- Threat Protection
			- Shows active or past attacks or threats on resources
			- Information analyzed is from network traffic and the behavior of users of your resources
		- Suspicious activity is reported to the Security Center
	- Microsoft Threat Intelligence - identify security threats
		- Uses Microsoft historical data and ML to identify possible threats
		- Threats
			- Hacker attempting to gain access
			- User suspicious activity
	- Quick Fix Badge - provides action to allow to fix immediately
	- Just-in-Time (JIT) Access - protects VMs from attacks on management ports
		- Access with 'Just in time VM access' link under 'ADAVANCED CLOUD DEFENSE' section of left menu
		- Click 'Recommend' tab to see VMs without JIT enabled
		- Select a VM to enable
		- Choose which ports to protect
		- Choose which protocols and IPs are allowed over the port
			- 'Per Request' option - user requesting access will have to specify IP address or CIDR block
			- Or you can specify CIDR block yourself to allow access from a specific IP address range
		- Specify max hours a user has access for
			- 1 - 24 hrs
			- Default = 3 hrs
		- Users will then request access from Security Center
			- Click 'Just-in-Time VM Access'
			- Select the VM
			- Click 'Request Access'
			- Specify ports to open
				- Allowed IP Addresses if they weren't setup initially
				- How long access is needed (up to maximum time configured - 24 hours)
- Key Vault (Encryption)
	- Encrypts secrets, keys and certificates for secure storage
	- Common security risk
		- E.g. Storing db usernames and passwords in connection strings in plain text files
	- Stored items
		- Apply security policies that define users and apps that have access to the item
		- Microsoft cannot see the encryption keys or encrypted data
	- Creating Key Vaults in Azure Portal
	- Pricing Tiers
		- Standard Tier
		- Premium Tier - keys stored in hardware security modules (HSMs)
			- HSM - separate piece of hardware designed for securely storing encrypted content and specialized for processing cryptographic data
	- Common Key Vault Uses
		- Generating security keys
		- Store encryption keys for Azure VMs
	- Exam Tip - Keeping encryption keys in an HSM boundary is required for Federal Information Processing Standard (FIPS) 140-2, so companies that need to maintain compliance with FIPS 140-2 can do so by using the Premium tier of Key Vault.
	- Key Vault can generate or users can import keys, secret or certificate into Key Vault
	- Example Keys that can be created
		- 4,096-bit security key
		- 4,096-bit RSA key
	- Generating Keys
		- Click 'Keys' under 'Settings' in left menu
		- Click 'Generate/Import'
		-  Fill out 'Create a key' form
	- Reviewing Keys
		- Get the key identifier - URL can be used by authorized users or applications to retrieve the key
		- Cannot review the key because it's encrypted and not available except through key identifier
	- Exam Tip - A key stored in Azure Key Vault would typically be accessed programmatically by an application. To protect the key, application developers can retrieve the key each time it’s needed instead of retrieving it once and storing it in memory. This ensures that the key remains secure.
	- Encryption Keys for VMs
		- Security Center recommends encrypting VM disks
		- VM disks stored as VHD files - when VHD files are encrypted, host OS that runs the VM must gain access to the security key in order to decrypt the VHD and run the VM
	- Using Key Vault for Disk Encryption Keys
		- Access policies must be configured to allow the vault for disk encryption
			- Can be configured before or after creation
	- Azure Disk Encryption
		- Enabled on VMs with Azure PowerShell, Azure CLI or ARM template
		- Keys and VMs must be in the same subscription and same Azure region
- Azure Sentinel
	- Watches resources for threats and responds to them
	- Common Security Frameworks
		- SOAR - Security Orchestration, Automation and Response (SOAR)
		- SIEM - Security Information and Event Management (SIEM)
	- Azure Sentinel makes implementing SOAR and SIEM easy
	- Exam Tips
		- Not only for Azure
		- Can report threats and analysis for on-premises resources and resources in other clouds
	- Azure Sentinel sits on top of Log Analytics and watches information it collects
	- Using Azure Sentinel
		- Create a Sentinel Workspace
		- Click 'Connect Workspace' button to create an instance of Azure Log Analytics and add it to the workspace or add existing Azure Log Analytics instance
		- Login and connect data sources to Sentinel using connectors using the 'Connect' button
			- Microsoft, Azure and 3rd-party connectors
			- When added, prerequisites are shown for the connector
		- Click 'Next' to finish complete adding the connector
		- Save connector configuration in Azure Monitor Workbook
	- Azure Monitor Workbook - easily aggregate data so it's easier to consume
	- Sentinel also searches for specific security threats
		- Hunting - allows you to use a query to run against resources
	- Responding to Threats
		- Sentinel can respond using a Playbook
			- Playbook - workflow that runs in response to an alert in Sentinel
		- Creating  a Playbook
			- Click 'Playbooks' in the left menu
			- Click 'Add Playbook' at the top
			- Create a new Logic App
				- Used for the workflows
			- Click 'Blank Logic App'
			- Enter sentinel in search box
			- Click 'When a response to an Azure Sentinel Alert is Triggered'
			- Build workflow
			- Add actions to perform when the alert is triggered