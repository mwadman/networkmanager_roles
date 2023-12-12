nmcli Role
=========

Manages network devices on systems using NetworkManager nmcli.

Requirements
------------

Requires the [Community General Collection](https://galaxy.ansible.com/ui/repo/published/community/general/) be installed.

Role Variables
--------------

This role takes a list named `nmcli_connections` as input.  
Each item in the list can have parameters set according to the [community.general.nmcli module](https://docs.ansible.com/ansible/latest/collections/community/general/nmcli_module.html) documentation.

For example:

```yaml
nmcli_connections:
# Creates an ethernet interface
    conn_name: "em1"
    type: ethernet
    ip4: "192.168.0.10/24"
    gw4: "192.168.0.1"
# Deletes an ethernet interface
    conn_name: "em1"
    state: "absent"
```

Example Playbook
----------------

To configure network devices

```yaml
---
- hosts: localhost
  connection: local
  roles:
    - mwadman.nmcli
```
