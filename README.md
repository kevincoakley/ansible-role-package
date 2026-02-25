ansible-role-package
====================

![](https://github.com/kevincoakley/ansible-role-package/workflows/Molecule%20Test/badge.svg)

Manage packages for CentOS and Ubuntu

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

Install Ansible on CentOS:

    - name: The Ansible role for CentOS systems
      hosts: package
      become: yes
      become_method: sudo
    
      vars:
        - pre_package:
          - name: epel-release
        - package:
          - name: ansible
    
      roles:
        - ansible-role-package

Install Ansible on Ubuntu:

    - name: The Ansible role for Ubuntu systems
      hosts: package
      become: yes
      become_method: sudo
    
      vars:
        - apt_repository:
          - repo: ppa:ansible/ansible
        - package:
          - name: ansible
    
      roles:
        - ansible-role-package

Workaround for Docker Desktop on Mac
----------------------------------

    export DOCKER_HOST="unix://${HOME}/.docker/run/docker.sock"

License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)
