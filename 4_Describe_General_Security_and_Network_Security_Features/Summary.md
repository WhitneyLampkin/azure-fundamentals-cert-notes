# Summary

- Azure Security Center - analyzes best practices for Azure resources and on-premises resources
- Security Center  (TODO: Make sure this isn't Trust Center)- covers policy and compliance, resource security hygiene and threat protection
- Just-In-Time VM - restrict VM remote desktop access to certain networks and certain times of day
- Azure Key Vault - provides secure way to store secrets, keys and certificates
- Azure Key Vault Premium - stores keys in hardware security modules (HSMs) making it FIPS 140-2-compliant
- Azure Sentinel - implements SOAR and SIEM in an environment
	- Watches for security threats in Azure, other clouds and on-premises
	- Take an action on a security alert using Playbooks which are built on top of Azure Logic Apps
- Defense in Depth - castle approach to a multi-layered security strategies
- Network Security Groups (NSGs) - rules that allow filtering of traffic on a network and control that traffic
	- Priority between 100 - 4096
- Azure Firewall - denies all traffic in specific subnets unless a rule is configured to allow that traffic
	- Stateful firewall that remembers the state of connections allows recognizing malicious traffic that would have otherwise looked normal
- Azure DDoS Protection - has 2 tiers
	- Basic - free option to protect from DDoS attacks
	- Standard - used alongside Azure Application Gateway

## Resources

- Disk Encryption Requirements