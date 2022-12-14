ansible-rocky-9-post-install
==============================
[![Actively Maintained](https://img.shields.io/badge/Maintenance%20Level-Actively%20Maintained-green.svg)](https://gist.github.com/cheerfulstoic/d107229326a01ff0f333a1d3476e068d)

Installs some essential packages and applies some basic configurations.

Requirements
------------
Requires Ansible 2.10 or later. This role has only been tested on Rocky Linux 9 (Blue Onyx).

Role Variables
--------------
A list of packages for installation are defined in `defaults/main.yml`.

Dependencies
------------
None

Example Playbook
----------------
    - hosts: all
      become: yes
      become_method: sudo
      roles:
        - ansible-rocky-9-post-install

Example Inventory
-----------------
*The `machine_hostname` variable is created for consistency when no DNS record exists*

*inventory.ini*

    [servers]
    192.168.0.11 ansible_ssh_user=rocky machine_hostname=server01
    192.168.0.12 ansible_ssh_user=rocky machine_hostname=server02
    192.168.0.13 ansible_ssh_user=rocky machine_hostname=server03

*inventory.yml*

    ---
    all:
      hosts:
        192.168.0.11:
        192.168.0.12:
        192.168.0.13:
      vars:
        ansible_ssh_user: rocky
        machine_hostname: server01


License
-------
GPL-3.0 License

Author Information
------------------
This role was created by Dan Kir
