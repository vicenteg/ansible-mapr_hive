mapr-hive
========

Installs the mapr-hive package, and performs some configuration.

Requirements
------------

This role configures MySQL databases, so it's assumed that there is a running instance of MySQL available.

Role Variables
--------------

The defaults will look something like this:

```
proxy_env: { }

mysql_root_user: root
mysql_root_password: mapr

hive_db: metastore
hive_db_user: hive
hive_db_pass: mapr
hive_metastore_host: '{{groups["hiveserver"][0]}}'

hive_version: "1.0*"

hive_authentication_type: maprsasl
hive_pam_services: login,sudo,sshd

hiveserver2_thrift_port: 10000
hivemeta_thrift_port: 9083
```

Modify as you see fit. The metastore host will also be the MySQL database host as well. The mysql_root_user and mysql_root_password variables will be used to authenticate to MySQL to create the metastore database.

Dependencies
------------


Example Playbook
-------------------------

The example below assumes that an inventory file has been created with certain groups that can be used to identify the nodes in the cluster having certain roles.

```

```
- hosts: hiveserver
  roles:
    - { role: mapr_hive }
```

License
-------

MIT

Author Information
------------------

Vince Gonzalez
