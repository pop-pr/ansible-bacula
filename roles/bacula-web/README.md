Bacula Web Dashboard
=========

This role aims to install and configure the bacula-web dashboard in a bacula-director machine that uses sqlite3 support.

Steps:

- Installs needed packages
- Creates web-bacula directory in var/www/html
- Sends bacula-web-tar and decompress it
- Copies config files to remote host
- Changes folder and files ownership recursively
- Changes bacula-db group ownership

Requirements
------------

- Apt package manager.
- bacula-director-sqlite3 installed and configured.
- Bacula working directory in /var/lib/bacula.

Role Variables
--------------

There is no settable variables for this role.

Dependencies
------------

- ansible-configure
- bacula-director

Example Playbook
----------------

ansible-playbook playbooks/bacula-web --limit {{host}}

    - hosts: srv
        gather_facts: yes
        become: yes
        become_method: sudo
        roles:
            - bacula-web


License
-------

BSD

Additional Information
------------------

[Bacula-web documentation](http://docs.bacula-web.org "Docs bacula web")

