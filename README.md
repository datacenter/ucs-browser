## UCS Health Check and Inventory Script (ported from UCS Communities)

### Pre-requisites

**Windows**
- Powershell 3.0 or higher
- UCS PowerTool 2.5.1 or higher
- .NET 4.5 or higher

**Linux**
- [Powershell 6.1.1](https://github.com/PowerShell/PowerShell/releases/tag/v6.1.1)
- [Cisco UCS PowerTool Core](https://community.cisco.com/t5/cisco-developed-ucs-integrations/cisco-ucs-powertool-core-suite-for-powershell-core-modules-for/ta-p/3643354)

---

### Cloning a specific Version
Always checkout a specific version of this repo and **AVOID** using master.<br />
`git clone https://github.com/datacenter/ucs-browser.git && cd ucs-browser && git checkout 2.7`

### Running the Script
Before generating the report select option `1)` from the root menu and connect to one or more target UCS Domains.  Select option `2)` from the connection menu to cache the domain credentials and speed up future executions.<br />

**Notes for Powertool Core:**<br/><br />
The save file dialog relies on .NET and therefore doesn't work on linux based systems.  To get around this limitation connect to and cache ucs doman credentials as mentioned above and then exit the script.  Next, relaunch the script using the `-RunReport`, `-UseCached` and `-Silent` flags


Ex: .\UCS_Health_Check.ps1 -UseCached -RunReport -Silent -Email user@domain.com

---
### Parameters
**[Vars]**
- `Email`     - emails the generated health check report to the specified email address


**[Switches]**
- `UseCached` - connects to all domains in the local cache credential file
- `RunReport` - automatically kicks off a health check report
- `Silent`    - auto-names the report file and exits the script after completing the report
