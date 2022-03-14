# Skill 1.2: Describe the differences between Infrastructure-as-a-Service (IaaS), Platform-as-a-Service (PaaS), and Software-as-a-Service (SaaS)

## Shared Responsibility Model

- Shared Responsibility Model - the concept of each service type having a different level of responsibility for the tenant
- Whitney Study Tip - Remember SPI (spy)

## Infrastructure-as-a-Service (IaaS)

- Infrastructure-as-a-Service (IaaS) - Virtualized infrastructure offered by a cloud provider
  - Provider
    - Allocates a VM (hardware)
  - Tenant
    - Responsible for OS, middleware components and the application
      - Install other necessary services for the application
      - Responsible for patch and version updates and troubleshooting OS
    - More control
    - Remote access to IaaS VMs unlike PaaS and SaaS
  - Either
    - Provider or tenant may install OS
  - IaaS services
    - Azure Security Center - security of IaaS VMs
    - Azure Backup - makes backing up data easy
    - Azure Log Analytics - troubleshooting
  - Uses
    - Dev testing
    - Temporary use (analyzing large amounts of data for a project)
  - Benefits
    - Scaling and elasticity
    - Always know what's currently installed since provider doesn't touch the VM
    - Only pay when VM is running
  - Drawbacks
    - Maintenance burden

## Platform-as-a-Service (PaaS)

- Platform-as-a-Service (PaaS) - Provider provides virtualized infrastructure, OS and middleware (software installed to help connect to databases and network systems
  - Provider
    - Allocates VM
    - Manages and controls the underlying systems
  - Tenant
    - No access to VM unlike IaaS
    - Publish code or Docker image
      - Docker is automatically installed on all App Service VMs
      - Docker is a technology that makes it easy to package your application and its required components into an image that can be deployed and run on another computer in another environment
  - PaaS services
    - Azure Application Insights
    - Azure CDN
    - Azure CosmosDB
    - Azure SQL DB
    - Azure Database for MySQL
    - Azure Storage
    - Azure Synapse Analytics
  - Benefits
    - Numerous application frameworks available with different versions (PHP, Node.js , ASP.NET, .NET Core, Java, Python, and more)
    - No complex configurations
    - Lift-and-shift - move applications from on-premises to cloud environment by simply deploying to the cloud
    - Specialized capabilities offered by Provider
      - e.g. Log-in feature to allow users to log in with Google, Facebook or Microsoft
    - Fault tolerance, elasticity, scaling, backup and disaster recovery features
      - Provider installs customized software for backups and restorations
    - Add app features without complex code
  - Drawbacks
    - Lose flexibility and control of deciding when to update the VM
      - Provider controls patches and updates

## Software-as-a-Service (SaaS)

- Software-as-a-Service (SaaS) - software provided by a cloud provider that's installed on infrastructure completely controlled by the hosting provider.
  - Provider
    - Full control
  - Tenant
    - Rents software from service provider
    - Provides data
  - SaaS services
    - Microsoft 365
      - Not just available for enterprises. Email services for personal accounts are SaaS services too.
    - Xbox Live
    - OneDrive
    - Power Automate (previously Microsoft Flow)
  - Benefits
    - Web-based software works on most devices
      - Connectivity and productivity for field staff using their own personal devices
    - Provider maintains and configures the application
    - Flexible, reliable cloud
  - Drawbacks

## Comparing service types

- IaaS
   - Greatest flexibility
   - Reduce operational costs
   - Pay only when VMs are running
   - But higher costs of installing and maintaining VMs might offset the savings
- PaaS
    - Moderate flexibility
    - No need to manage infrastructure
    - Only responsible for the application installed on the cloud
    - Popular when moving on-premises solutions to the cloud
    - More features from cloud provider since they install their own software and features on the platform
    - Application could negatively be affected by updates and version changes
    - Increased costs associated with testing an application before the cloud provider rolls out changes
- SaaS
    - Completely managed and maintained by the cloud provider
    - Cannot install own software
    - Removes IT burden from company
    - Employees access software on their own personal devices from anywhere
    - Data backups
    - Not a good option when customization is required
