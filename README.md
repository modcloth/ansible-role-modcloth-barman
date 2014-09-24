Modcloth Barman
=========

This role installs and configures Barman to do backup and replication of postgres servers

Requirements
------------

Upstream server should be configured to send WAL archives to this server. This can be done with the following:

```
wal_level = 'archive'
archive_mode = on
archive_command = 'rsync -a %p {{barman_user}}@{{this host}}:{{barman_home}}/{{name}}/%f'
```

Role Variables
--------------

See `defaults/main.yml`

Dependencies
------------

None

Example Playbook
----------------

- hosts: postgres-master.prod.example.com
  roles:
  - role: modcloth.barman
    barman_upstreams:
      - name: "postgres-master"
        hostname: "postgres-master.prod.example.com"
           

License
-------

MIT

Author Information
------------------
ModCloth Inc.
