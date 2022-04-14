# The Drupal Phase

[![GitHub Issues](https://img.shields.io/github/issues/acch/ansible-boilerplate.svg)](https://github.com/acch/ansible-boilerplate/issues) [![GitHub Stars](https://img.shields.io/github/stars/acch/ansible-boilerplate.svg?label=github%20%E2%98%85)](https://github.com/acch/ansible-boilerplate/) [![License](https://img.shields.io/github/license/acch/ansible-boilerplate.svg)](LICENSE)

### The Purpose

The purpose of this project was to be able to pull a docker image on one Virtual Machine and push it to another through an Ansible script


### Software Block Diagram
![alt text](https://www.tutorialandexample.com/wp-content/uploads/2020/12/image-83.png)


### Playbooks

Playbooks associate hosts (groups) with roles. Define a separate playbook for each of your groups, and then import all playbooks in the main `site.yml` playbook.

File | Description
---- | -----------
`site.yml` | Main playbook - runs all tasks on all servers
`anygroup.yml` | Group playbook - runs all tasks on servers in group *anygroup*

### Roles

The group playbooks (e.g. `anygroup.yml`) simply associate hosts with roles. Actual tasks are defined in these roles:

```
roles/
├── common/             Applied to all servers
│   ├── handlers/
│   ├── tasks/
│   │   └ main.yml      Tasks for all servers
│   └── templates/
└── anyrole/            Applied to servers in specific group(s)
    ├── handlers/
    ├── tasks/
    │   └ main.yml      Tasks for specific group(s)
    └── templates/
```

Consider adding separate roles for different applications (e.g. webservers, dbservers, hypervisors, etc.), or for different responsibilities which servers fulfill (e.g. infra_server vs. infra_client).

### Tags

Use the following command to show a list of available tags:

```
ansible-playbook site.yml --list-tags
```

Consider adding tags for individual components (e.g. DNS, NTP, HTTP, etc.).

Role | Tags
--- | ---
Common | all,check

## Copyright and license

Copyright 2017 Achim Christ, released under the [MIT license](LICENSE)
