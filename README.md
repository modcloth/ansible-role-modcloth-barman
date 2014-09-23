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

TODO

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: modcloth.barman, x: 42 }

License
-------

MIT

Author Information
------------------
ModCloth Inc.
