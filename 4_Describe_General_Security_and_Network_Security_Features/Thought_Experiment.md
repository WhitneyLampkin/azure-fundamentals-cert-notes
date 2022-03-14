# Thought Experiment

- ContosoPharm needs to:
	- New app with large number of new resources that deals with sensitive data
		- Need to comply with best practices for  security
		- Some servers for the app are on-premises and also need to be secured
		- Solution - Azure Security Center
	- IT director wants to make sure only company computers can remote desktop to the Azure VMs
		- Solution - just-in-time VM access feature
	- The app also uses certificates for authentication that need to be stored securely with encrypted keys so they comply with FIPS 140-2
		- Solution - Azure Key Vault
	- IT Director told staff to implement SOAR and SIEM in the environment for Azure resources and AWS without spending a lot of money on consulting.
		- Solution - Azure Sentinel
	- The app is multitiered. CTO wants to ensure traffic rules are applied to different layers of the app and reject outside traffic.
		- Solution - NSGs
	- Want to prevent DDoS attacks
		- Solution - Azure DDoS Standard Tier