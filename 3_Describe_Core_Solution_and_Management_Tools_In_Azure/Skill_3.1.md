# Skill 3.1: Describe core solutions available in Azure

- Azure IoT Hub
	- Manage, monitor and communicate (individual or in groups) with IoT devices
	- Add up to 1 million devices to IoT Hub
	- Connecting new IoT devices
		- New connection string is created
		- Uses shared access key for authentication
			- Prevents unauthorized access to IoT Hub
	- Sending messages
		- To devices: cloud-to-device (C2D messaging)
		- From devices: device-to-cloud (D2C messaging)
		- Route messages to Event Hub, Azure Storage,Service Bus and other endpoints based on the message's content
			- 'Add a route' screen in Message routing tab of Azure
		- Messages are encrypted
	- Sending files to devices
		- Easily update firmware on devices securely by copying the firmware to the device
		- Devices will detect the change, reboot and flash the new firmware to the device
	- Device Twin - logical representation of the physical device stored as JSON in the IoT Hub
		- Has metadata for additional categorization stored as tags in JSON
			- The physical device isn't aware of the metadata
			- Remove previously used tags by setting them to 'null'
		- Contains properties for IoT device
			- 2 copies of every property
				- Reported property
				- Desired property
			- 2 copies of properties are needed because IoT Hub doesn't always have connection to the devices - they can sync when the device is back online
	- IoT Hub Device Provisioning Service (DPS) - uses enrollment groups to add large number of devices to the IoT Hub
		- Device Ids - certificates or trusted platform module chips
		- Enrollment group
			- Tells DPS which IoT Hub to add the device to
			- Provides initial configuration for the device twin
		- Provides device with connection information
		- $0.123 per 1,000 operations
	- Pricing Tiers for IoT Hub
		- Basic 
			- B1 - $10/month - 400,000 messages/day
			- B2 - $50/month - 6,000,000 messages/day
			- B3 - $500/month - 300,000,000 messages/day
		- Standard
			- Free - Free - 8,000 message/day
			- S1 - $25/month - 400,000 messages/day
			- S2 - $250/month - 6,000,000 messages/day
			- S3 - $2,500/month - 300,000,000 messages/day
		- Pricing for scale
			- Most enterprises will choose a standard tier for minimum messaging needs and scale to more hubs instead of moving up to the next tier
			- e.g. Start with S2 when average 5M messages and add another S2 when 8M messages are coming in for $500/month vs. going to S3 for all messaging for $2,500/month
			- Switching between basic and standard is not allowed
		- Standard Tier ONLY Features
			- Device Streams
			- Cloud-to-device messaging
			- Device management, device twin and module twin
			- IoT Edge for handling IoT devices at the edge of the network where they reside
- IoT Central (SaaS)
	- IoT device monitoring without complex configuration that Azure Stream Analytics + Power BI would require
	- SaaS offering for IoT devices
	- Doesn't require Azure resources (unlike IoT Hub), just create the app here using a template or custom app
		- Template categories
			- Retail
			- Energy
			- Government
			- Healthcare
	- Unlike IoT Hub, IoT Central let's you create simulated devices
	- 3 Built-in Roles
		- Admin - Full access; edit pages and add new users
			- Uses 'Administration' link under App Settings in sidebar
		- Builder - Edit pages but no admin tasks
		- Operator - Use the app but no edit rights
		- Custom roles can be added
	- Configure rules to monitor devices and perform an action when the rule is activated
		- e.g. Configuring a rule that will activate when the humidity of a device is above 60 degrees
		- Email notifications can be sent when rules are triggered
		- Web hooks can be triggered to call an Azure Function, run a workflow in Azure Logic App or Microsoft Power Automate or do something specific in a custom app
	- Device groupings
		- Take actions on many devices at once
		- Use 'Device Groups' link in left sidebar
		- Specify condition for each device being added to the group
		- Create a job to take action device groups 
			- Click 'Jobs' in left menu
			- Modify properties
			- Change settings
			- Send commands to devices
	- Perform analytics
		- Export data from devices to Azure Blob Storage, Azure Event Hubs or Azure Service Bus
- Azure Sphere
	- Entire ecosystem for IoT device security
		- Microprocessor unit (MCU)
		- Azure Sphere MCU with security components embedded in the chip
		- Azure Sphere OS
		- Azure Sphere Security Service
			- Ensures MCUs are secured
			- Update embedded Azure Sphere OS and apps running on MCUs
			- Enables reporting for crashes and other analytics
	- Benefits
		- Patch bugs in embedded chips that would otherwise cause security concerns
		- Provides secure environment for running embedded code
		- Enforces secure communications between devices
			- e.g. Strong authentication between home devices
	- Only 1 Azure Sphere certified MCU available
		- MediaTek MT3620 AN - $8.65/unit
	- Azure Sphere Development Kits 
		- Low cost
		- Includes hardware ready for Azure Sphere and Azure Sphere Software Developer's kit (SDK) for VS
	- Azure Sphere has to be purchased from a Microsoft distributor
		- Distributors sell packages
			- Azure Sphere certified MCU
			- License for Azure Sphere Security Service
			- License for Azure Sphere OS
	- Pricing for Azure Sphere includes the OS and Azure Sphere Security Service updates through July 2031
- Azure Synapse Analytics (PaaS)
	- Powerful system for handling big data - (think data warehouse)
		- Stores data
		- Querying data in multiple ways
		- Execute large queries
		- Security
	- Big data - more data than can be analyzed through conventional means within the desired timeframe
	- Azure Synapse Analytics is a new version of SQL Data Warehouse with more functionality
	- 4 Components - Runs in an Azure Synapse cluster with 4 components
		- Synapse SQL - data warehousing portion of Azure Synapse
			- Run powerful queries for big data on compute nodes in parallel
			- Compute nodes run components called Data Movement Service (DMS) that moves data between the nodes
			- Queries run on compute nodes to separate from data storage
			- Scale compute nodes easily  for more power
		- Apache Spark integration
			- 3rd-party big data processing engine
			- Spark features are automatically incorporated into Azure Synapse when the cluster is created
		-  Azure Data Lake Storage
			- Used to integrate Apache Spark
			- Stores large amounts of data for analyzing
			- For wide array of data instead of relational data
			- Data stored in containers
				- Containers store related data
			- Generic Terms
				- Data Lake - repository of unordered data
				- Data Warehouse - repository of ordered data
		- Web-based user interface called Azure Synapse Studio
			- Used to analyze and manage data
			- Launches with the click of a button
	- External Notes
		- Azure Data Warehouse (now known as Azure Synapse Analytics) is a PaaS offering from Microsoft. As with all PaaS services from Microsoft, SQL Data Warehouse offers an availability SLA of 99.9%. Microsoft can offer 99.9% availability because it has high availability features built into the platform.
		- You can use Power BI to analyze and visualize data stored in Azure Data Lake and Azure SQL Data Warehouse.
		- Azure Data Lake includes all of the capabilities required to make it easy for developers, data scientists and analysts to store data of any size and shape and at any speed, and do all types of processing and analytics across platforms and languages. It removes the complexities of ingesting and storing all your data while making it faster to get up and running with batch, streaming and interactive analytics. It also integrates seamlessly with operational stores and data warehouses so that you can extend current data applications.
- HDInsight (Computer Clusters)
	- Easily create and manage clusters of computers
	- Computer cluster - A computer cluster is a set of computers that work together so that they can be viewed as a single system. Unlike grid computers, computer clusters have each node set to perform the same task, controlled and scheduled by software.
	- Common framework
	- Perform distributed processing of big data
	- Microsoft's version of Hadoop but supports other cluster types
	- All supported cluster types
		- Hadoop - large-scale data processing (supports Hive (SQL-like queries), Pig (scripting languages) and Oozie (workflow scheduling system)
		- HBase - super fast, scalable NoSQL DB
		- Storm - fast & reliable processing of unbounded streams of data in real time
		- Spark - super fast analytics using in-memory cache across multiple operations in parallel
		- Interactive Query - in-memory analytics using Hive and LLAP (processes that execute fragments of Hive queries)
		- R Server - enterprise-level analytics using R, a language that specialized for big data analytics
		- Kafka - super fast processing of huge numbers of synchronous data streams, often from IoT devices
	- Advantages
		- No building - Don't have to build your own complex clusters
		- Secure environment 
		- Easily scalable
	- HDInsight clusters perform analytics by breaking up large data blocks into segments that are passed on to nodes within the cluster
		- Nodes reduce it down to a result set
		- Happens in parallel
		- Increase power and speed by adding more nodes
	- Create of Hadoop clusters may take up to 20 mins to complete
		- When finished data analysis can be performed by writing queries
	- Billing
		- Billed per hour
		- Price increases as power increases
- Azure Databricks
	- Accumulate and format data (data modeling) to be used for machine learning models
	- Databricks Workspace - web-based portal for interacting with data accessible via Azure Portal
	- Databricks - also name of company that developed Apache Spark
	- Azure Databricks Entities
		- Workspaces
		- Tables
		- Jobs
	- Databricks relies on clusters to do its work
	- Notebooks - present and interact with related data
		- Contains data, visualizations and docs to help understand data
		- Run commands against ML frameworks to build ML models inside the notebook
		- Notebooks have cells
		- Notebook docs written in markdown that starts with %md
	- Python, Scala & R are programming languages commonly used to program machine learning models
	- Azure Databricks Datasets - automatic access to data with the path /databricks-datasets/
	- Running commands in Databricks creates a job that runs on compute resources allocated to your cluster
		- They are deallocated when not in use
		- Databricks uses serverless model of computing
	- Azure Databricks includes the Databricks Runtime for ML (Databricks Runtime ML)
		- Databricks can be used for training ML algorithms
		- Includes ML libraries: Keras, PyTorch, TensorFlow and XGBoost
		- Horovod - used for distributed deep-learning algorithms
		- All of these are open-sourced and can be used without Databricks but Databricks takes away the installation and configuring hassle
		- Exam Tip - Databricks works with 3rd-party ML frameworks to allow you to build machine learning models
		- Must specific a ML runtime (they have ML after the version #)
		- Not limited to ML libraries included with Databricks
		- Exam Tip - Databricks is based on Apache Spark
		- Productionalizing - exporting ML models from Databricks to external ML system for use
			- MLeap
				- Execute ML model and make predictions based on your model
				- Export into an MLeap bundle
				- Use bundle in MLeap to run the model against new data
			- Databricks ML Model Export
				- Export ML models and pipeline to be used by other ML platforms
				- For exporting Apache Spark-based ML models and pipelines
- Azure Machine Learning
	- Service for artificial intelligence (AI)
	- Artificial Intelligence (AI)
		- Artificial Narrow Intelligence aka weak AI - AI that performs 1 specific task more efficiently than a human (all current AI falls into this category)
			- e.g. Siri, Alexa, Cortana, etc.
		- Artificial General Intelligence aka strong AI - typical AI shown in movies (not currently available)
		- AI is based in mathematics
			- Computer engineers have to give computers the ability to 'learn' like humans
		- Human Brain
			- Neural network - all of the neurons in the human brain
			- Neurons - communicate with other neurons in the brain
			- Synapses
			- Information travels just under the speed of sound
		- AI
			- Digital Neural Network
			- Natural Language Understanding -  AI designed to understand human speech
				- Cognitive Services - Azure offering for natural language understanding
			- Machine Learning - uses a digital neural network to accomplish a task
				- e.g. Image recognition (like in iPhotos)
				- Uses learning algorithm that is the basis of AI
				- Later test data is fed to it
				- Based on test data, algorithm may be tweaked and retested
				- Algorithm is then deployed to environment with vast array of compute resources allocated to it
				- Feed large amounts of data for processing
				- The algorithm can improve itself by recognizing patterns
			- Information travels at the speed of light
				- Processes 20,000 years of human-level learning in 1 week
		- Machine Learning  in Azure
			- Makes ML approachable to everyone
			- SDKs for Python and R programming languages
			- Drag & Drop Environment
			- Automated mode for creating and training ML models
			- Two Editions
				- Basic 
					- Access to ML SDKs and notebooks
				- Enterprise - Basic edition plus...
					- Additional features such as Visual Designers
			- Microsoft has a standalone ML Studio in its own portal
				- Being replaced with Azure Machine Learning which also has a studio
			- To use Azure ML 
				- Create an Azure ML Workspace
				- Build and train models, run experiments, etc. which is all mostly done in Azure ML studio for most operations
				- Clicking 'Launch Now' button launches the studio to build ML models or load samples
			- Pricing
				- Based on usage
				- Billed for VM that runs Azure ML assets
				- Billed a ML surcharge and small amount per hour for usage
				- Reserve usage for 1 year to reduce cost or 3 years for higher savings
- Cognitive Services (SaaS)
	- APIs with pre-built ML models from Microsoft
	- Serverless Azure offering
	- Computer Vision - API to extract info from images
		- Recognize objects or a scene
		- Recognize inappropriate content
	- Video Indexer API - analyze video content and extract info from the content
		- Easily add closed captioning in multiple languages
		- Recognize people and objects
		- Search videos for specific words, people or emotions
	- Speech APIs
		- Speech Translation APIs - language translation in real-time to Speaker Recognition
		- Speaker Recognition API - analyze speech and identify speakers
	- Language APIs - understand typed commands (can be used for chatbots)
		- Text Analytics - understand user sentiment
	- Decision APIs - allow you to moderate content in images, text or video
	- Personalizer API - offer users a personalized experience
	- Pricing
		- Transactional
		- Pay a small amount for transactions processed through the service
- Azure Bot Service (PaaS)
	- Build AI conversational experiences
	- Runs on Azure App Service
		- Has all of the Azure App Service features
		- Scaling
		- Simple configurations
		- Charged for an Azure App Service plan
	- Create with Web App Bot template in Azure portal
	- Uses C# or Node.js for the SDK languages
	- Different bot templates for different needs
	- Once the service is created, its code can be downloaded for customization
	- Bot Framework
		- Edit source code
		- Building source code
		- Viewing analytics
	- Test with 'Test in Web Chat' link in left menu
	- Connect to other services (known as channels)
		- Slack
		- Facebook Messenger
		- Microsoft Teams
	- Microsoft's channels are standard channels
	- Direct Line - connect bots to your own application or website
		- Premium channel
		- Costs a small amount for messages used
- Serverless Computing (concept ?)
	- Borrow computer for a quick task
	- Only pay when your code runs on the VM
	- Not actually 'serverless'
		- Only means that the VM isn't allocated to a particular user
	- Consumption-based plan that allows you to run code on the surplus VMs
		- Usually come with big discounts
		- Small workloads may be free
	- Providers came up with this to avoid losing money on surplus VMs
	- Serverless Services
		- Cognitive Services
		- Azure Functions for serverless compute
		- Azure Logic Apps for serverless workflows
		- Azure Event Grid for serverless event routing
- Azure Functions
	- Compute component of Azure's serverless offerings
		- Run on Azure App Service
		- Do not get consumption model of paying when created in an App Service plan
	- Write code without worrying about deploying the code or creating VMs to run it
	- Function Apps - Apps using Azure Functions
	- Create with
		- Microsoft Visual Studio
		- Microsoft Visual Studio Code
		- Maven for Java Function Apps
		- Python command line for Python Function Apps
		- Azure command line interface (CLI) on Windows or Linux
		- Azure Portal
	- Can create with Docker container on a Linux VM
	- Runtime stack based on your chosen programming language with Code Option
		- .NET Core
		- Node.Js
		- Python
		- Java
		- PowerShell Core
	- Configure hosting options
		- Linux or Windows as OS
			- Keep in mind that you may be forced to use one based on the stack chosen
		- Plan Types
			- Serverless plan (default) - aka Consumption plan type
			- Run inside of App Service plan
	- Open Function App in portal to create functions when its ready such as...
		- Function - code that runs when something triggers it
		- Proxy - configure multiple endpoints for the Function App and expose them all via a single URL
		- Slot - create a copy of the Function App that isn't public facing
	- Deployment Slots - Write and test code until satisfied and then deploy to production with a click of a button
	- Function App Settings - change settings for the function app
		- Configure daily quota - Azure stops the function app until the next day when it's reached
		- Change runtime version
			- Changing major versions can cause the app to break
			- Microsoft prevents it if you have existing functions so the apps don't break
		- Change to read-only
		- View, revoke and add new host keys
			- Host key - used to control access to the functions
	- Exam Tip
		- Keys help protect access to functions but not complete security
		- Authentication features in App Services protect against unauthorized use
		- Microsoft API Management - adds security requirements to your Function App
	- Configurations link
		- Settings are specific to App Service
		- 32-bit vs. 64-bit
		- HTTP version
		- Accessing files with FTP
	- Platform Features tab
		- Shows all features available in App Service platform
		- Configure
			- SSL certs
			- Custom domain names for your Function App
			- Turn-key authentication
	- Creating a new function
		- Click '+' to the right of the Functions link
		- Choose development environment
			- VS
			- VS Code
			- Azure portal development environment
			- Code editor alongside Azure Functions Core Tools
		- Optional - if anything besides in portal is chosen, select deployment
			- Send function directly to App Service
			- Use App Service Deployment Center
		- Optional - Prerequisite steps before creating function based on development environment
	- How functions work
		- Use trigger-based system
		- Function Proxies - used for complex functions that perform many things
		- Microservices - several functions that work together to complete a task
		- Output Binding - determines what happens after the trigger and code runs
			- Bindings used depend on the type of function
			- HTTP Trigger bindings
				- Azure Queue Storage
				- Azure Blob Storage
				- HTTP
				- Azure Service Bus
				- Azure Table Storage
				- Azure Event Hubs
			- HTTP Trigger can be called as a webhook
				- Webhook - configure a service to make a request to a particular URL in response to events
				- When configured to call Azure function's URL, you can easily add powerful functionality to the workflow
			- Configure multiple outputs for functions
			- Not good for complex workflows - use Logic Apps
			- Logic Apps can be integrated with Azure Functions
- Logic Apps
	- Kicked off with trigger 
		- Only similarity with Azure Functions
		- More complex than Azure Functions
	- Don't write code
	- Power Automate (aka Microsoft Flow) uses Logic Apps as its underlying technology
		- Power Automate designer looks like Logic Apps
	- Workflow - Logic App responds to something happening by performing a series of tasks like
		- Sending an email
		- Transferring data to a DB
		- Defined in JSON files
		- Designer generate JSON code as user configures the app
	- Workflow responses can happen in order or at once
	- Workflow Example 
		- Customer places an order on an ecommerce site
		- Inventory count is updated
		- Invoice generated 
		- Email invoice to customer
		- Sign up customer for newsletter
		- Generate shipping label
	- Logic Apps integrates more than 100 other Microsoft and 3rd-party services
	- 3 Components of Logic Apps
		- Connectors - connect Logic App to something (like Azure service, 3rd-party service, FTP server, etc.)
			- Each connector has 1 or more triggers and actions specific to that connector
			- Common connectors
				- Request
				- Schedule
				- Service Bus
				- Twitter
				- Office 365 Outlook
				- SharePoint
				- FTP
				- Dynamics 365
				- SFTP
				- Salesforce
				- RSS
				- OneDrive
				- Azure Event Grid
				- Azure Queries
		- Triggers - specific action that causes the Logic App to run
			- Common triggers
				- Message received in Service Bus queue
				- New Tweet posted
				- Recurrence
				- New file created on OneDrive
				- HTTP request is received
				- Event Grid resource event occurs
				- New email received in Outlook
				- File added to FTP server
		- Actions - What the Logic App does as an output
			- Common Actions
				- Control
				- HTTP
				- Inline Code
				- Azure Functions
				- Azure API Management
				- Azure App Services
				- Azure Logic Apps
	- Can combine multiple actions for a connector
	- Can combine multiple connectors to create complex and powerful workflows
	- Creating Logic Apps
		- Created in Azure Portal
		- Logic App designer then opens
			- Choose Trigger
	- Exam Tip 
		- OneDrive has many triggers for the same connector
		- Understand connectors vs. triggers
	- Can use Logic App templates or create blank app and start from scratch
	- Logic Apps use HTTP trigger to call Function Apps
		- Make sure Function App is designed to accept the data it receives
	- Monitor Logic Apps with Azure Portal
		- Trigger History - entire history of when trigger was evaluated and fired
- Event Grid
	- Enables an Azure service to trigger an event when something happens and configure another Azure service to listen and respond to that event
	- Both Azure Functions and Logic Apps use Event Grid
	- Azure Resources that can trigger Event Grid Events
	- Using Event Grid
		- Choose resource type
		- Configure event to listen for
			- Events differ based on selected resource type
		- When events occur
			- Take action against Azure resource using the Azure Resource Manager (ARM) connector in Logic Apps
			- Run script that interacts with an Azure resource to do something
	- Benefits
		- Rapid development solutions
		- Reliability with triggering events
			- Event grid retries failed triggers for up to 24 hours
		- Cost effective
			- First 100,000 operations per month are FREE
			- 60 cents for every 1M operations after that
- Azure DevOps
	- Collection of tools to plan, track and manage development projects
	- Includes multiple services
		- Azure Boards - A visual way to manage and track work for your team using tiles displayed in a drag-and-drop interface
		- Azure Repos - Source and version control using either Team Foundation Version Control or Git
			- Use GIT or Team Foundation Version Control (TFVC)
			- TFVC only have 1 version of a file on their machines and everything else on the server
			- GIT all versions on their local machines
		- Azure Pipelines - Manage software releases through build, test, and release automation
			- Continuous integration and deployment
		- Azure Test Plans - Create and track tests to ensure reliable software releases
		- Azure Artifacts - Use popular package feeds from both public and private sources
- Azure DevTest Labs
	- Helps with testing by simplifying VM creation and configurations and reduces cost of testing
		- Devs simply choose a VM and claim it
	- Typical test scenario
		- Dev creates VM to run testing tools and development tools
		- Dev configures the VM with packages the app needs
		- App may require multiple VMs for complex solutions
	- Concerns
		- Manually creating VMs take a lot of time
		- Costs a lot of money
	- Using Azure DevTest Labs
		- Create the DevTest Lab
		- Create VMs inside of the lab using the 'Add' button
			- Select base for the VM using a template or other source, can be VM configured for a project and saved as a custom image
			- Can add additional components with artifact
		- IT departments or lead devs would create the DevTest Labs
		- VMs created in DevTest Lab by default are not claimable change with 'Advance Settings'
	- Exam Tip - CANNOT easily add existing VMs to DevTest Labs
		- Copy VMs VHD image into Azure Storage container used by DevTest lab
		- Create new VM from the custom image
	- Custom images and formulas
		- Custom Image - image based on VHD from existing VM
		- Formula - Based on VHD but contains settings specific to the DevTest Labs like VM size, included artifacts, etc.
			- Uses a custom image as a base
	- Unclaimable VMs used when need to configure with specific settings and then save as a custom image or formulas for others to use
	- Creating Custom Images
		- Configure the VM the way you need
		- Select the VM from the list of VMs in DevTest Lab
		- Click 'Create Custom Image'
		- Click 'Ok'
			- Takes a few minutes for the image to be available
	- Creating Formulas
		- Click 'Formulas'
		- Click 'Add to create a new formula'
		- Select a base for the formula
		- Configure DevTest Lab settings
	- Benefits
		- Auto-shutdown - enabled by default and shuts down VMs after a certain period of time to save money
		- Policies
			- Allow control of VM sizes, number of VMs per user and per lab, etc.