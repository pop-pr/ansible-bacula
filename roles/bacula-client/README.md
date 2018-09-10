Bacula-client
=========

This role aims to configure Open-bacula Backup Software file-daemon in any client machine with apt and then send a conf file with a default job and client definitions to the Bacula-Director's machine.

Steps:

- Installs packages from bacula-client (Bacula File Daemon).
- Creates password's file.
- Generates a random password for the daemons to communicate.
- Writes the generated password in /etc/bacula/passwords
- Sends bacula-fd.conf template
- Sends client.conf template to Director's machine.

Requirements
------------

Client machine with apt package manager.

Client machine with sudo.

Role Variables
--------------

__ansible_hostname__ and  __ansible_default_ipv4.address__ are defined during the run based on host target.

__director_name__: Name of the director-machine

__director_address__: IPV4 address of the director-machine.

Obs: Director's vars are defined in vars/main.yml file.

__unique_password__: Password dinamically generated during the first run of the role. It is used to communicate between bacula-daemons.

All vars are used in bacula-fd.conf and client.conf jinja2 template files, to dynamically configure clients.

Dependencies
------------

- ansible-configure
- bacula-director installed and configured in another machine.

Example Playbook
----------------

ansible-playbook playbooks/bacula-client --limit __{{hosts}}__

    - hosts: vms
      gather_facts: yes
      become: yes
      become_method: sudo
      roles:
        - bacula-client

License
-------

BSD

Additional Information
------------------

* [Frequently Asked Questions](http://www.bacula.org/7.4.x-manuals/en/problems/Bacula_Frequently_Asked_Que.html "FAQ")
* [Docs](http://www.bacula.org/5.2.x-manuals/en/main/main/index.html "Docs")