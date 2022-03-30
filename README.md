[comment]: # "Auto-generated SOAR connector documentation"
# FireMon Security Manager

Publisher: Splunk Community  
Connector Version: 1\.1\.0  
Product Vendor: FireMon  
Product Name: Security Manager  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 5\.1\.0  

This App exposes various FireMon Security Manager API endpoints as actions

[comment]: # " File: README.md"
[comment]: # "  Copyright (c) 2022 Splunk Inc."
[comment]: # ""
[comment]: # "Licensed under the Apache License, Version 2.0 (the 'License');"
[comment]: # "you may not use this file except in compliance with the License."
[comment]: # "You may obtain a copy of the License at"
[comment]: # ""
[comment]: # "    http://www.apache.org/licenses/LICENSE-2.0"
[comment]: # ""
[comment]: # "Unless required by applicable law or agreed to in writing, software distributed under"
[comment]: # "the License is distributed on an 'AS IS' BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,"
[comment]: # "either express or implied. See the License for the specific language governing permissions"
[comment]: # "and limitations under the License."
[comment]: # ""
The app uses HTTP/ HTTPS protocol for communicating with the Firemon Security Manager. Below are the
default ports used by Splunk SOAR.

|         Service Name | Transport Protocol | Port |
|----------------------|--------------------|------|
|         http         | tcp                | 80   |
|         https        | tcp                | 443  |


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Security Manager asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | API endpoint \(e\.g\., https\://host/securitymanager/api\)
**username** |  required  | string | Username
**password** |  required  | password | Password
**verify\_server\_cert** |  optional  | boolean | Verify server certificate

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[assign device group](#action-assign-device-group) - Assign a Device to a DeviceGroup  
[remove device group](#action-remove-device-group) - Remove a Device from a DeviceGroup  
[get device group](#action-get-device-group) - Get a DeviceGroup by ID  
[get domain](#action-get-domain) - Get a domain by ID  
[update device](#action-update-device) - Update a device  
[get device](#action-get-device) - Get a Device by ID  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

The Firemon API version endpoint is used for the test connectivity action\.

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'assign device group'
Assign a Device to a DeviceGroup

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 
**firemon\_device\_group\_id** |  required  | DeviceGroup ID | numeric | 
**firemon\_device\_id** |  required  | Device ID | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.message | string | 
action\_result\.summary\.\*\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.parameter\.firemon\_device\_group\_id | numeric | 
action\_result\.parameter\.firemon\_device\_id | numeric | 
action\_result\.status | string | 
action\_result\.data\.\*\.message | string |   

## action: 'remove device group'
Remove a Device from a DeviceGroup

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 
**firemon\_device\_group\_id** |  required  | DeviceGroup ID | numeric | 
**firemon\_device\_id** |  required  | Device ID | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.message | string | 
action\_result\.summary\.\*\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.parameter\.firemon\_device\_group\_id | numeric | 
action\_result\.parameter\.firemon\_device\_id | numeric | 
action\_result\.status | string | 
action\_result\.data\.\*\.message | string |   

## action: 'get device group'
Get a DeviceGroup by ID

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 
**firemon\_device\_group\_id** |  required  | DeviceGroup ID | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.parameter\.firemon\_device\_group\_id | numeric | 
action\_result\.message | string | 
action\_result\.summary\.\*\.id | numeric | 
action\_result\.summary\.\*\.domainId | string | 
action\_result\.summary\.\*\.name | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.data\.\*\.id | string | 
action\_result\.data\.\*\.domainId | string | 
action\_result\.data\.\*\.name | string | 
action\_result\.data\.\*\.securityConcernIndex | string | 
action\_result\.data\.\*\.analysis | string | 
action\_result\.data\.\*\.childDeviceGroups | string | 
action\_result\.data\.\*\.childDevices | string | 
action\_result\.status | string |   

## action: 'get domain'
Get a domain by ID

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.summary\.\*\.id | numeric | 
action\_result\.summary\.\*\.name | string | 
action\_result\.data\.\*\.id | string | 
action\_result\.data\.\*\.name | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.status | string |   

## action: 'update device'
Update a device

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 
**firemon\_device\_id** |  required  | Device ID | numeric | 
**firemon\_device\_json** |  required  | Device fields json for update | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.message | string | 
action\_result\.summary\.\*\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.parameter\.firemon\_device\_id | numeric | 
action\_result\.parameter\.firemon\_device\_json | string | 
action\_result\.status | string | 
action\_result\.data\.\*\.message | string |   

## action: 'get device'
Get a Device by ID

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon\_domain\_id** |  required  | Domain ID | numeric | 
**firemon\_device\_id** |  required  | Device ID | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.firemon\_domain\_id | numeric | 
action\_result\.parameter\.firemon\_device\_id | numeric | 
action\_result\.message | string | 
action\_result\.summary\.\*\.id | numeric | 
action\_result\.summary\.\*\.domainId | numeric | 
action\_result\.summary\.\*\.name | string | 
action\_result\.summary\.\*\.description | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.data\.\*\.id | string | 
action\_result\.data\.\*\.domainId | string | 
action\_result\.data\.\*\.name | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.status | string | 