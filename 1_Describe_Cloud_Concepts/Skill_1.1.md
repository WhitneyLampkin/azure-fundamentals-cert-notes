# Skill 1.1: Identify the Benefits and Considerations of using Cloud services

##  High availability

  - Service-level agreements (SLAs)
    - Microsoft offers a service-level agreement (SLA) that guarantees a certain level of availability as a percentage
    - Uptime of close to 100%
  - Causes of unavailability
    - Network outages
      - Causes: Failed connections between backend systems, other apps (i.e. APIs), etc.
      - Solution: Fault tolerance, proper planning
    - Application failures
      - Causes: Software bugs or application design
      - Solution:  Azure Insights gives detailed info about performance and reliability of app. It also points developers to the source of bugs.
    - System outages (e.g. VM outage)
      - Causes: Computer (VMs in the cloud) running a system becomes unavailable (e.g. database server)
      - Solution: Tenant or Provider may manage VMs depending on the chosen cloud service. Provider monitors health of VMs.
    - Power outages
      - Causes: Loss of electricity long term or short flickers that cause reboots
      - Solution: Cloud providers invest heavily in battery-operated powered backups and can also offer to run apps in different regions not affected
    - Problem with a reliant system (e.g. external database)
      - Causes: Non-cloud based systems become unavailable
      - Solution: Host all reliant systems in the cloud

## Scalability, elasticity and agility

  - Scaling - adding additional resources or power for your application
    - Horizontal - (scaling out) - adding more VMs identical to what you have to handle more load
    - Vertical - (scaling up) - move to a more powerful VM with more CPU power, memory and solid-state disk drives
  - Elasticity - auto scaling
    - Azure Auto-Scale: Azure service that automatically scales apps based on usage patterns, resource utilization, time of day and more.
  - Agility - Speed and flexibility in the cloud to be able to scale VMs within seconds

## Fault tolerance and disaster recovery

  - Fault tolerant - Systems put in place to monitor the health of cloud resources and take action when a resource is unhealthy
  - Fault tolerant IS NOT scaling
    - Scaling is initiated by you and assumes all VMs are healthy
    - Fault tolerance happens automatically when you need to be moved from an unhealthy to a healthy system
    - Cloud providers design infrastructure to ensure fault tolerance (e.g. Microsoft ensures VMs are unlikely to be affected by system failures)
    - Small scale failures
  - Disaster Recovery
    - Disaster Recovery - Reliable backups and replication of application resources
    - Aka Business Continuity and Disaster Recovery (BCDR) plans
    - Required based on certain types of data stored
    - Microsoft complies with laws such as HIPAA

## Economic benefits of the cloud
  - On-premises model
    - Physical computer hardware
    - Capital expenses - large amounts of money tied up in capital expenses limit the daily funds (operating expenses) available to run the business
    - Drawbacks
      - Hardware outdated long before it makes financial sense to replace it
      - Not an agile approach - takes months to requisition and configure new hardware
  - Cloud model
    - No physical hardware (rent hardware from the cloud provider)
    - Move capital expenses to operating expenses
    - Operating expenses are easier to track and adjust on a monthly basis
    - Reduced costs
      - Principle of Economies of Scale - savings due to purchases on a large scale that cloud providers pass on to consumers
      - Consumption-based model -  pay-per-use (i.e. Serverless computing)
