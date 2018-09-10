Bacula-director
=========

This role aims to install and configure Open-bacula Backup Software director-daemon with my-sql support, file-daemon, storage-daemon and Bacula-console in any machine with apt.

Steps:

- Installs bacula-director's packages.
- Creates clientdefs sub-directory.
- Sends template files to configure bacula-director's machine.
- Start the server.

Requirements
------------

- Client machine with apt package manager.
- Client machine with sudo.

Role Variables
--------------
Both are used in bacula-fd.conf and client.conf jinja2 template files, to dynamically configure the director.
- "ansible_hostname"
- "ansible_default_ipv4.address"

Dependencies
------------

- ansible-configure


Example Playbook
----------------

ansible-playbook playbooks/bacula-director --limit __{{hosts}}__

    - hosts: vms
      gather_facts: yes
      become: yes
      become_method: sudo
      roles:
        - bacula-director

License
-------

BSD

Additional Information
------------------

* [Frequently Asked Questions](http://www.bacula.org/7.4.x-manuals/en/problems/Bacula_Frequently_Asked_Que.html "FAQ")
* [Docs](http://www.bacula.org/5.2.x-manuals/en/main/main/index.html "Docs")
* [Configuring the director](http://www.bacula.org/5.2.x-manuals/en/main/main/Configuring_Director.html "Director-Docs")
* [Storage Daemon](http://www.bacula.org/5.1.x-manuals/fr/main/main/Storage_Daemon_Configuratio.html "SD-Docs")
* [Volume-Utilities](http://www.bacula.org/5.0.x-manuals/de/utility/utility/Volume_Utility_Tools.html "Volume-utiliies")
