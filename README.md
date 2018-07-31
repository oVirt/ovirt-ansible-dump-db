oVirt Engine dump
=================

This role gets oVirt engine and DWH DB dump.

- get DB variables (database, user, password, ...)
- get dump of engine and dwh database

Target systems
--------------

* engine

Requirements
------------

Preinstalled engine with local DB.

Role Variables
--------------

```yaml
---
ovirt_engine_db_dump: [True, False] Dump engine database (default: True)
ovirt_engine_db_dump_dwh: [True, False] Dump DWH database (default: False)
ovirt_engine_db_dump_start_services: [True, False] Start engine and DWH service after dump (default: True)
ovirt_engine_db_dump_local_dir: directory on local machine where to store files (default: engine_dump in playbook directory)  
ovirt_engine_version: oVirt engine X.Y version
```

Dependencies
------------

None

Example Playbook
----------------

```yaml
---
- hosts: engine
  vars:
    ovirt_engine_db_dump_dwh: True
    ovirt_engine_version: "4.2"
  roles:
    - ansible-role-ovirt-dump-db
```

Author Information
------------------

Lucie Leistnerova
lucie.leistnerova@gmail.com
