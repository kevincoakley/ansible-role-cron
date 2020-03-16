ansible-role-cron
=================

![](https://github.com/kevincoakley/ansible-role-cron/workflows/Molecule%20Test/badge.svg)

Manage cron for CentOS 7, 8 and Ubuntu 18.04

Requirements
------------

None

Role Variables
--------------

See defaults/main.yml

Dependencies
------------

None

Example Playbook
----------------

    - name: Test the Cron role for CentOS and Ubuntu systems
      hosts: user
      become: yes
      become_method: sudo
    
      vars:
        - cron:
            - name: Once Every Day
              hour: "0"
              job: /bin/ls -al /
            - name: Delete Entry
              hour: "1"
              job: /bin/ps -aux 
              state: absent
      roles:
        - ansible-role-cron

License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)