ansible-role-package
====================

[![Build Status](https://travis-ci.org/kevincoakley/ansible-role-package.svg?branch=master)](https://travis-ci.org/kevincoakley/ansible-role-package)

Manage packages for CentOS 7, Ubuntu 14.04 and Ubuntu 16.04

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


License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)
