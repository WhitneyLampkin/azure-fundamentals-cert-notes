Skill 3.2: Describe Azure management tools

- Azure Portal
	- Today's portal is the 3rd major iteration of Azure Portal
		- Came when Microsoft moved to ARM
	- Azure Portal calls ARM on the backend
	- Home - default view in Azure Portal
		- Shows icons for various services
			- Clicking the icon shows resources for the service type that you've created
		- Settings button  shows left sidebar menu with same icons and more called the Azure Portal Menu
			- Menu can be re-ordered
			- App Service Plan - shows all App Service Plans
				- Can click a resource in the plan
		- Shows recently accessed resources
		- Azure Cloud Shell button to the right of the search bar
		- Filter button to the right of the Azure Cloud Shell button - used to show resources in a certain Azure subscription or AAD
		- Notifications Button - Azure related notifications
		- Settings button 
			- Change default view
			- Choose docked or flying menu
			- Change theme
			- Disable toast notifications
			- Restore default settings
			- Export settings
			- Delete all settings and dashboards
		- Click profile icon
			- Log out
			- Change AAD
	- Opening Resources from App Service Plans page
		- Shows left menu specific to that resource
		- Main window shows different items based on resource
			- Referred to as blades in Azure Portal
	- Blades
		- Overview Blade - Common to most Azure resources
		- Diagnose and Solve Problems Blade 
		- Blades may be different per resources because each resource has its own team and they design based on what they feel their features needs
	- Customizing the Dashboard
		- Click Dashboard in Azure Portal Menu
		- Click pencil edit icon
		- Make Changes
			- Rename dashboard
			- Add tiles to the dashboard by choosing from the gallery
			- Delete existing tiles
		- Click 'Done' to finalize
	- Create new dashboards for specific purposes
		- i.e. Web Apps Only Dashboard
- Azure PowerShell
	- Azure PowerShell AZ Module - offers cross-platform support for Windows, Linux or macOS
		- Uses .NET Standard Library for functionality
		- Runs PowerShell v5,6,7
			- v6 & 7 are cross-platform and run on Linux, Mac or Windows
		- When running Windows 7 or later with PowerShell v5, install .NET Framework 4.7.2
		- Has to be installed before use
			- Run PowerShell elevated
				- Windows - run as admin
				- Linux, MacOS - run with superuser privileges using Sudo
				- Installation Command: 'Install-Module -Name Az -AllowClobber'
					- If PowerShell finds the command name already exists, the installation fails
					- 'AllowClobber' - tells PowerShell it's ok to precedence for any commands that exist in another module
				- If running in admin mode (elevated) is not an option install for your ID only with
					- Personal Installation Command - 'Install-Module -Name Az -AllowClobber -Scope CurrentUser'
			- After installation, sign in with Azure account with 'Connect-AzAccount'
				- Azure Sign-in Command: 'Connect-AzAccount'
					- Rerun command after closing to authenticate another session
				- This command shows token in the PowerShell Window
				- Enter token at Authenticate PowerShell Session to authenticate the PowerShell Session
			- Set Active Subscription Command: 'Set-AzContext -Subscription "subscription_id"'
	- Azure PowerShell Az module commands
		- Start with verb and an object
			- Verb - New, Get, Move or Remove
			- Object - What you want the verb to affect
				- E.g. New-AzResourceGroup -Name MyRG - Location "South Central US"
				- E.g. Remove-AzResourceGroup -Name MyRG
					- Type 'y' to confirm deletion
	- PowerShell Command Scripts - perform a number of operations at once
		- Cannot type 'y' to confirm so use -Force parameter to bypass the prompt
			- E.g. Remove-AzResourceGroup -Name MyRG -Force
	- PowerShell commands used to use AzureRm module
		- Commands are the same but the module has a new name
- Azure CLI
	- Scripting for those who don't know PowerShell
	- aka Azure Command-Line interface
	- Can be scripted using shell scripts in various languages like Python, Ruby, etc.
	- Cross-platform: Windows, Linux, MacOS with v2 or later
	- Installation Steps
	- After installation
		- Login to AZ command: 'az login'
			- Opens browser automatically
		- Set default subscription command: 'az account set --subscription "subscription_id"'
		- Get list of commands command: 'az resource create --help'
		- Use --force parameter to disable prompts
			- Must be included with CLI and PowerShell scripting  or it won't work
		- Interactive Mode - easy way to learn CLI: 'az interactive'
			- Autocomplete
			- Scoping of commands
			- And more
			- CLI will install the feature
			- Press right arrow key to enter the suggested command when typing
		- All CLI Extensions command: 'az extension list-available --output table'
			- Shows all available extensions and what you have installed
		- Installing Extensions command: 'az extension add --name extension_name'
	- Note - PS uses 1 dash (-) and CLI uses 2 (--)
- Azure Cloud Shell
	- Web-based command shell to interact with Azure from the command line in the cloud
	- Create resources and more
	- Used by the 'Try It' button in Portal
	- Cloud Shell button is directly to the right of the search bar
		- Choose environment the first time: Bash or PowerShell
		- Create Azure Storage Account 
			- Because Cloud Shell persists everything installed and user settings
		- Cloud Shell menu bar
			- Environment DDL selector
			- Power Button - restart session
			- Help
			- Settings
			- Upload/Download Files
			- Open new session of Cloud Shell in new browser tab
			- Open Editor Button - opens an instance of the Monaco Editor for editing scripts and other files (even code files) in the browser
				- To exit, right-click and click 'Quit'
			- Web Preview Button - run web applications using the files in the current folder
				- Can use when developing apps with Cloud Shell
				- Why would someone want to preview an app in Cloud Shell instead of just debugging it locally? Many developers write applications that interact with other Azure services, and they might want to debug these applications while they’re running in Azure. For command line developers, this technique in Cloud Shell is a powerful way to enable that.
- Azure Mobile App
	- Download to Android or iOS devices to manage Azure resources on the go
		- Also available on mobile web
	- Doesn't provide the full functionality of the Azure Portal
	- To connect to a VM, must also install the Microsoft Remote Desktop app
	- Access to Cloud Shell
- Azure Advisor
	- Notifies of issues in configurations to avoid problems
	- Offers advice about
		- High Availability
		- Security
		- Performance 
		- Cost
	- Access with the Azure Advisor link in the left Azure Menu
	- Provides recommendations; not requirements
		- Can dismiss or postpone alerts
	- Can download recommendations as a comma-separated file or PDF with 'Download as CSV' or 'Download as PDF'
- Azure Monitor
	- Aggregates metrics for Azure services and exposes them to a single interface
	- Create alerts to notify of concerns
	- Click Monitor in Azure Portal to display the blade
	- Totally customizable
		- Select resource and metrics to see data
		- For multiple metrics make sure they have common units of measurements
	- Charts show data for past 24 hours by default and real time values are at the right of the charts
		- This is also customizable
	- Pin charts that are helpful
	- Azure Monitor Alerts - can do the following when a condition is met
		- Can notify with email or SMS messages
		- Run a Logic App flow
		- Call Function apps
		- Make webhook requests
		- Alerts based on user specified rules and actions
			- Base rules on metric already being monitored or create from scratch
		- Adding a new rule
			- Click 'Alert' in left menu
			- Click 'New alert rule' in the top menu bar
			- To start it, click 'Select' for the resource you want to configure the alert for
			- Specific condition for the alert with 'Add Condition' and select the signal you want to monitor for the alert
		- Action Group - used to specify the action to perform in response to an alert being triggered
			- Use 'Create' under 'Actions Groups' to create a new action group
			- Contain several actions that are executed by an alert being triggered
- Azure Service Health
	- Health view for a specific resource
	- Different than the generic Azure Status web page that may give too much info
	- Service Health Blade - shows the health and status of the resources
		- Shows small status dot for the health of Azure regions where resources are deployed
		- Clicking the dot gives quick reference of Azure health
		- Planned Maintenance Link -View upcoming planned maintenance
		- Health Advisors link - see health info that might be related to your configuration and not a problem with Azure
		- Service Issues
			- See details in Azure Service Health
			- See Link for details on the incident
			- Download PDF with official Microsoft notice of the incident
	- Azure Monitor vs. Azure Service Health
		- Both important for overall view of Azure resources
		- Monitor
			- Monitor cost and performance
			- Alert when conditions are triggered
		- Service Health
			- Single-point-of-truth for info on health of Azure itself
			- How Azure incidents affect your resources
