# ansible-bacula
Dynamically configure bacula instances (Clients, Storages and Directors) using [Ansible](https://www.ansible.com/ "Ansible Project") 2+.


Você pode ler este documento em português [aqui](https://github.com/PoP-PR/ansible-bacula/blob/master/README.md "Leia-me!").
## Introduction
The purpose of this project is to use Ansible to automate the installation, configuration and communication process between Bacula daemons.


This project is intrinsically related to the [Bacula as a micro-service] (https://hub.docker.com/r/popprrnp/bacula-dir/ "Bacula on Dockerhub") project, which is provided by PoP-PR and is based on the configurations of this project for automation.
## What can I do with this project?
- Set up new Directors.
- Set up Storages and communicate them with the directors.
- Configure Clients and communicate them with the directors.
## Additional Settings
Roles can run on a virtual machine (by installing and configuring packages) or on a Docker Container Host machine (by orchestrating only the configuration of new features).

All configuration-related variables are inside the /vars/ subdirs.
## Requirements
Ansible 2+
## Running
```bash
ansible-playbook playbooks/<playbook_name> --limit <host>
```
## Example Playbook
```yml
---
- hosts: srv
  gather_facts: yes
  become: yes
  become_method: sudo
  roles:
    - bacula-storage-docker
```
## License
GLP V3
## Support
The entire project is distributed free of charge and has no warranty or support. However, feel free to contribute to the project and improve it!
## Contribute!
- Make a Fork of our project
- Create a branch with your new feature (git checkout -b - my-new-feature)
- Commit your changes (git commit -am 'Add some feature')
- Push to branch (git push origin my-new-feature)
- Create a new Pull Request
## Authors
Team of the Ponto de Presença da RNP no Paraná (POP-PR RNP)
