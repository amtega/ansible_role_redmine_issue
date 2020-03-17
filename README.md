# Ansible redmine_issue role

This is an [Ansible](http://www.ansible.com) role to create a nissue in Redmine via REST API.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

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
        redmine_isssue_create_request:
          issue:
            parent_issue_id: 100
            category_id: 150
            assigned_to_id: 250
            subject: "[Ansible] Sunject test"
            description: "Description text"

```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

To run test you need provide the variables defined in `defaults/main.yml`. One way to provide this information is calling the testing playbook passing an additional plus the default one provided for testing, as it's show in this example:

```shell
$ cd amtega.redmine_issue/tests -i inventory -i ~/mycustominventory.yml --vault-id myvault@prompt
$ ansible-playbook main.yml
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
