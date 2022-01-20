# Anbible role for Satellite Registration Command

This Ansible role gets a Registration Command via Satellite API.


## Description:

Registration Command feature is available from Satellite 6.10 and replaces the deprecated bootstrap.py.
This functionality generates a bash command to register a host when run in your shell.
This Ansible role requests via the Satellite API the generation of this command for later execution on the hosts that need to be registered in the Satellite.


## Variables:

### Satellite connection variables :

| Role variables | Type | Mandatory? | Default |
|--|--|--|--|
| satellite_registration_command_url| String | Yes |  |
| satellite_registration_command_username | String | Yes |  |
| satellite_registration_command_password | String | Yes |  |
| satellite_registration_command_force_basic_auth | Boolean | No | true |
| satellite_registration_command_validate_certs | Boolean | No | false |

### Registration Command variables:

| Registration Command fields | Role variables | Type | Mandatory? | Default |
|--|--|--|--|--|
| Organization | satellite_registration_command_organization OR satellite_registration_command_organization_id | String | Yes |  |
| Location | satellite_registration_command_location OR satellite_registration_command_location_id | String | Yes |  |
| Host group | satellite_registration_command_hostgroup OR satellite_registration_command_hostgroup_id | String | Yes |  |
| Activation Keys | satellite_registration_command_activation_keys | Array | Yes if not present in the chosen host group configuration |  |
| Setup Insights | satellite_registration_command_setup_insights | Boolean | No | true |
| Setup Remote Execution | satellite_registration_command_setup_remote_execution | Boolean | No | true |
| Insecure | satellite_registration_command_insecure | Boolean | No | true |
| Token Life Time | satellite_registration_command_token_life_time | Integer | No | 4 |
| Update Packages | satellite_registration_command_update_packages | Boolean | No | false |
| Force | satellite_registration_command_force | Boolean | No | false |
| Ignore errors | satellite_registration_command_ignore_subman_errors | Boolean | No | false |

## References:

##### Satellite documentation - Managing Hosts
https://access.redhat.com/documentation/en-us/red_hat_satellite/6.10/html-single/managing_hosts/index#registering-a-host_managing-hosts

##### Satellite documentation - API Guide
https://access.redhat.com/documentation/en-us/red_hat_satellite/6.10/html-single/api_guide

##### Satellite documentation - APIDOC
https://\<your-satellite-server\>/apidoc/v2/registration_commands/create.html
