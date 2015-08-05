Role Name
=========

Deploy a FusionInventory agent and configure it

Requirements
------------

None

Role Variables
--------------

    - fusioninventory_server: The inventory server
    - fusioninventory_cert:   The path to store you self-signed certificate

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      pre_tasks:
        - name: Deploy your self-signed cert
          copy: src=mycert.pem dest="{{fusioninventory_cert}}"
      roles:
        - role: enalean.fusioninventory-agent
      vars:
        - fusioninventory_server: https://glpi.example.com/plugins/fusioninventory/
        - fusioninventory_cert: /etc/ssl/mycert.pem

License
-------

GPLv2

Author Information
------------------

Thomas Cottier (thomas.cottier@enalean.com)
