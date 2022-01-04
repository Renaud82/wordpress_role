![CI](icones/icone.jpeg)

Ansible Role:  Wordpress for training
=========

An Ansible Role that deploy Wordpress and MySQL on Linux.

Requirements
------------

Environments: Linux
Requires: 
 - Docker
 - Python-pip
 - Ansible Docker Container (docker-py)

Role Variables
--------------

BDD parameters to manage the database:

    bdd_name: sql_bdd
    user_name: ubuntu
    user_pwd: unbuntu
    root_pwd: rootpwd
    
Docker parameters to manage name and external port:

    docker_network_name: wordpressnet
    wordpress_container_name: wordpress
    mysql_container_name: mysql
    extrenal_port: 8600
    
Choose the persistente volume to save BDD

    bdd_volume: "/tmp/mysql/"

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: client
  become: true
  vars_files:
    - files/secrets/credentials.yml
    - files/parameters.yml
  roles:
    - install_docker
    - wordpress_role
```

Author Information
------------------

This role was created in 2022 by Renaud SAUTOUR
