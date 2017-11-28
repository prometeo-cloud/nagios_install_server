# nagios_install_server

## Description:

This role install Nagios Server and generate hosts/checks.

## Behaviour:

Deploying the Nagios Server.

**Feature:** Creates/Installs/Configures a Nagios Server  
- **Given**a Host for Server
- **Given**a repository link for additional packages
- **When** deployment is executed
- **Then** Nagios packages and common plugins are installed  
- **Then** nagios admin and guest user are created
- **Then** Generate and configure the config file 
- **Then** Generate the nagios contact template 
- **Then** Firewall rules are added
- **Then** Nagios and HTTPD Services are restarted


## Configuration:

Variable required upon execution of the role (not in the vars or defauls folders).
Needs to be provided to the role before execution.

| Variable  | Description  | Example  | 
|---|---|---|
| **nagios_username** | The admin username. | nagiosadmin |
| **nagios_password** | The admin password. | abc123ABC |
| **admin_email** | The edmin password. | |
| **nagios_guest_username** | The Nagios guest user. | guest |
| **nagios_guest_password** | The Nagios guest password. |guest |

| Variable  | Description  | Example  | 
|---|---|---|
| **nagios_plugin_path** | The Default Plugin Path | /usr/lib64/nagios/plugins |
| **nagios_create_guest_user** | The creation of Nagios guest user| guest |
| **nagios_http_port** | The Nagios HTTP Port | 80 |
| **nagios_https_port** | The Nagios HTTPS Port |443 |
| **admin_name** | The Nagios Admin Name | Nagios Admin |
| **nrpe_tcp_port** | The nrpe port | 5666 |

## Usage:

How to invoke the role from a playbook:

```yaml
- name: Creates Nagios Server               
  include_role:
    name: nagios_install_server
  vars:
    nagios_username: '?'
    nagios_password: '?'
    admin_email: '?'
    nagios_guest_username: '?'
    nagios_guest_password: '?'

```