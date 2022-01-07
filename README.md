[comment]: # "Auto-generated SOAR connector documentation"
# F5 BIG\-IP

Publisher: World Wide Technology  
Connector Version: 2\.3\.1  
Product Vendor: F5  
Product Name: F5 BIG\-IP  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.190  

This app supports containment actions like 'block ip' or 'unblock ip' on an F5 BIG\-IP appliance\. There must be a firewall policy \(Security››Network Firewall\:Policies\) configured on the BIG\-IP and the name of the policy must be specified in the Action Parameters\. The rule name can be the source IP address appended to a keyword string, e\.g\. 'Phantom' \+ ip

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a F5 BIG\-IP asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**device** |  required  | string | F5 Device IP/Hostname
**username** |  required  | string | username
**password** |  required  | password | password

### Supported Actions  
[block ip](#action-block-ip) - Blocks an IP address  
[unblock ip](#action-unblock-ip) - Deletes the rule which blocks an IP address  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity  

## action: 'block ip'
Blocks an IP address

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**source** |  required  | packet source address | string |  `ip` 
**policy** |  required  | Firewall policy name | string | 
**partition** |  required  | Partition or path of the firewall policy | string | 
**rule name** |  required  | Rule name | string | 
**action** |  required  | Rule action | string | 

#### Action Output
No Output  

## action: 'unblock ip'
Deletes the rule which blocks an IP address

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**policy** |  required  | Firewall policy name | string | 
**partition** |  required  | Partition or path of the firewall policy | string | 
**rule name** |  required  | Rule name | string | 

#### Action Output
No Output  

## action: 'test connectivity'
Validate the asset configuration for connectivity

Type: **test**  
Read only: **True**

This action logs into the F5 device using a REST API call to check validate the asset configuration

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output