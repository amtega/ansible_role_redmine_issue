# Ansible <!-- this role name --> role

This is an [Ansible](http://www.ansible.com) role which create a issue in Redmine via rest api.

## Requirements

[Ansible 2.7+](http://docs.ansible.com/ansible/latest/intro_installation.html)

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
        redmine_issue_server_url: "<Your redmine url>"
        redmine_issue_project_name: "<Redmine project name>"
        redmine_issue_api_password: < api password for the api, supplied by Redmine >
        redmine_issue_validate_certs: < yes/no >        
        redmine_issue_json_request_file: /tmp/request.json
        redmine_isssue_create_request:
          issue:
            parent_issue_id: < int >
            category_id: < int >
            assigned_to_id: < int >
            subject: "[Ansible] Sunject test"
            description: "Description text"

```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.redmine_issue/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) <!-- YEAR --> AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
