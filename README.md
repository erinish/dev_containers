Dev Containers
=========

Create arbitrary containers [centos6,7 ubuntu14,16] for further configuration / testing via Ansible.

Requirements
------------

Requires running and working LXC, and LXC library for Python.

CentOS containers on Ubuntu need yum.

Ubuntu containers on CentOS need debootstrap.


Role Variables
--------------

```YAML
containers:
  - thing1:
    name: containername
    base: <centos6|centos7|ubuntu14|ubuntu16>
user: "username"
lxc_template: "templatename"
lxc_dir: "/path/to/dir"
auth_key: "/path/to/pubkey"
```

Example Playbook
----------------
```YAML
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
```

License
-------

GPL 3.0
