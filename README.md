# FireMon Security Manager
Publisher: Splunk Community
App Version: 1.0.0
Product Vendor: FireMon
Product Name: Security Manager
Product Version Supported (regex): ".*"

This App exposes various FireMon Security Manager API endpoints as actions

The template files created by the Splunk Phantom/SOAR (version 4.10.3.51237, unprivileged installation) App Wizard and Firemon Security Manager API (version 9.4.2) were used to develop this App.

### Configuration Variables

The below configuration variables are required for this App to operate on <b>Security Manager</b>. These are specified when configuring an asset in Phantom.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base_url** | required | string | API endpoint (e.g., https://host/securitymanager/api) |
**password** | required | password | Password |
**username** | required | string | Username |
**verify_server_cert** | required | boolean | Verify server certificate |

### Supported Actions
[get domain](#action-get-domain) - Get a domain by ID
[get devicegroup](#action-get-devicegroup) - Get a DeviceGroup by ID
[remove devicegroup](#action-remove-devicegroup) - Remove a Device from a DeviceGroup
[assign devicegroup](#action-assign-devicegroup) - Assign a Device to a DeviceGroup
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration

## action: 'get domain'
Get a domain by ID
Type: **investigate**
Read only: **True**
Get a domain by ID

### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon_domain_id** | required | Domain ID | numeric |  |

### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------
action_result.parameter.firemon_domain_id | numeric |  |  |
action_result.status | string |  |  |
action_result.message | string |  |  |
summary.total_objects | numeric |  |  |
summary.total_objects_successful | numeric |  |  |
action_result.summary.*.id | numeric |  |  |
action_result.summary.*.name | string |  |  |
action_result.data.*.id | string |  |  |
action_result.data.*.name | string |  |  |
action_result.data.*.description | string |  |  |

## action: 'get devicegroup'
Get a DeviceGroup by ID
Type: **investigate**
Read only: **True**
Get a DeviceGroup by ID

### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon_domain_id** | required | Domain ID | numeric |  |
**firemon_device_group_id** | required | DeviceGroup ID | numeric |  |

### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------
action_result.parameter.firemon_domain_id | numeric |  |  |
action_result.parameter.firemon_device_group_id | numeric |  |  |
action_result.status | string |  |  |
action_result.message | string |  |  |
action_result.summary.*.id | numeric |  |  |
action_result.summary.*.domainId | string |  |  |
action_result.summary.*.name | string |  |  |
summary.total_objects | numeric |  |  |
summary.total_objects_successful | numeric |  |  |
action_result.data.*.id | string |  |  |
action_result.data.*.domainId | string |  |  |
action_result.data.*.name | string |  |  |
action_result.data.*.securityConcernIndex | string |  |  |
action_result.data.*.analysis | string |  |  |
action_result.data.*.childDeviceGroups | string |  |  |
action_result.data.*.childDevices | string |  |  |

## action: 'remove devicegroup'
Remove a Device from a DeviceGroup
Type: **generic**
Read only: **False**
Remove a Device from a DeviceGroup

### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon_device_id** | required | Device ID | numeric |  |
**firemon_domain_id** | required | Domain ID | numeric |  |
**firemon_device_group_id** | required | DeviceGroup ID | numeric |  |

### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------
action_result.parameter.firemon_domain_id | numeric |  |  |
action_result.parameter.firemon_device_group_id | numeric |  |  |
action_result.parameter.firemon_device_id | numeric |  |  |
action_result.status | string |  |  |
action_result.message | string |  |  |
action_result.summary.*.message | string |  |  |
action_result.data.*.message | string |  |  |
summary.total_objects | numeric |  |  |
summary.total_objects_successful | numeric |  |  |

## action: 'assign devicegroup'
Assign a Device to a DeviceGroup
Type: **generic**
Read only: **False**
Assign a Device to a DeviceGroup

### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**firemon_device_id** | required | Device ID | numeric |  |
**firemon_domain_id** | required | Domain ID | numeric |  |
**firemon_device_group_id** | required | DeviceGroup ID | numeric |  |

### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------
action_result.parameter.firemon_domain_id | numeric |  |  |
action_result.parameter.firemon_device_group_id | numeric |  |  |
action_result.parameter.firemon_device_id | numeric |  |  |
action_result.status | string |  |  |
action_result.message | string |  |  |
action_result.summary.*.message | string |  |  |
action_result.data.*.message | string |  |  |
summary.total_objects | numeric |  |  |
summary.total_objects_successful | numeric |  |  |

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration
Type: **test**
Read only: **True**
The Firemon API version endpoint is used for the test connectivity action

### Action Parameters
No parameters are required for this action

### Action Output
No Output

