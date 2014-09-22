Role Name
========

ansible-openmrs

Role Variables
--------------
```
# Version of OpenMRS to install.
openmrs_version: 1.9.8
# Determines whether to install dependencies needed all on the same box.  JRE, Tomcat, MySQL.  Turning this off will assume you already have these in place.
openmrs_install_deps: true
openmrs_config_dir: "{{usr_tomcat}}/.OpenMRS"

# Directory war will be downloaded to
tomcat_webapps: "{{var_tomcat}}/webapps"
# Will try to set based on OS in vars/
tomcat_user: tomcat

# DB settings
# Please change passwords below
openmrs_db_name: openmrs
openmrs_db_user: openmrs_user
openmrs_db_user_password: openmrs_user
# Dont change this unless you already have mysql setup
openmrs_db_login_user: root
openmrs_db_login_password: root

```

Example Playbook
-------------------------
### playbook.yml

```

---
- hosts: all
  roles:
  - ansible-openmrs

  vars:
    openmrs_db_user_password: secret
    openmrs_db_login_password: supersecret


```

License
-------

Apache 2.0

Author Information
------------------

Ryan Yates
