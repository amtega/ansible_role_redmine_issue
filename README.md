# Ansible redmine_issue role

This is an [Ansible](http://www.ansible.com) role to setup a issue in Redmine.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`. The role setups the following facts:

- `redmine_issue_result`: result of the issue management

## Usage

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.redmine_issue
      vars:
        redmine_issue_server_url: https://redmine.acme.com
        redmine_issue_project_name: oneproject
        redmine_issue_api_password: apipassword
        redmine_issue_validate_certs: no       
        redmine_isssue_fields:
          parent_issue_id: 100
          category_id: 150
          assigned_to_id: 250
          subject: "[Ansible] Sunject test"
          description: "Description text"
        redmine_issue_state: present

```

## Testing

Tests are based on [molecule with docker containers](https://molecule.readthedocs.io/en/latest/installation.html).

To run test you need provide the variables defined in `defaults/main.yml`. One way to provide this information is calling the testing playbook passing an additional inventory using the following environment variables:

- `ANSIBLE_INVENTORY`: path to an inventory
- `ANSIBLE_VAULT_PASSWORD_FILE`: path to the file containing the vault password required for the previous inventory

```shell
cd amtega.redmine_issue

ANSIBLE_INVENTORY=~/myinventory ANSIBLE_VAULT_PASSWORD_FILE=~/myvaultpassword molecule test --all
```

## License

Copyright (C) 2022 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
- Juan Antonio Valiño García
