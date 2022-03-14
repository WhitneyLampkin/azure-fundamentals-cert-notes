# Thought Experiment

- ContosoPharm is creating a new customer portal to integrate with social media accounts.
	- IT director concerned about a 3rd-party consultant having access to usernames and passwords for the company's social media accounts. 3rd-party consultant needs access to social media accounts without the password and immediately lose the access when he's no longer needed
		- Solution:
			-  Azure Active Directory as guest user 
			- Azure AD business-to-business (B2B) to add enterprise applications with the desired social media platforms and give the user access using Azure AD B2B
			- Remove the user from Azure AD when they leave
	- Contractor needs access to a few Azure resources. No one else should be able to gain access if they find the contractor's username and password. Should only be accessible when logging into a Windows computer and not mobile devices.
		- Solution: Multifactor Authentication with Conditional Access Policy for guest users
	- Contractor needs read-only access to Azure services
		- Solution: RBAC Reader Role
	- VMs only need to be created in Central US region and no one should be able to delete the caching component
		- Solution: Azure Policies
	- CEO wants breakdown of expenses for both departments billed for VMs.
		- Solution: Add Tags on the VMs and export to Microsoft Excel
	- Easily recreate a complex step in an Azure deployment
		- Solution: Azure Blueprint