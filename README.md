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
  - thing1:
    name: containername
    base: <centos6|centos7|ubuntu14|ubuntu16>
user: "username"
lxc_template: "templatename"
lxc_dir: "/path/to/dir"
auth_key: "/path/to/pubkey"


Example Playbook
----------------
---
- name: Setup a test env
  hosts: localhost
  roles:
    - role: erinish.dev_containers
      user: devops
      auth_key: "/home/devops/.ssh/id_rsa.pub"
      containers:
        - thing1:
          name: bojack
          base: centos7
        - thing2:
          name: mrpeanutbutter
          base: ubuntu14
        - thing3:
          name: princesscarolyn
          base: centos6
        - thing4:
          name: diane
          base: ubuntu16

License
-------

GPL 3.0
