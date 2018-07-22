Role Name
=========

dev_containers

Requirements
------------

Requires running and working LXC, and lxc library for Python.

Currently supports CentOS7 host and containers. More to come.

Role Variables
--------------

containers:
  - "containername-1"
  - "containername-2"
user: "username"
lxc_template: "templatename"
lxc_dir: "/path/to/dir"
auth_key: "/path/to/pubkey"



Example Playbook
----------------

- name: Setup a test env
  hosts: localhost
  roles:
    - role: erinish.dev_containers
      user: "erinish"
      auth_key: "/home/erinish/.ssh/id_rsa.pub"

License
-------

GPL 3.0
