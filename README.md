Ansible-Role-Jetty
=========

Installs the latest version of Jetty Servlet Engine from archive.

How to install
--------------

```
ansible-galaxy install janesmae.jetty
```

Actions role
------------

- Downloads Jetty's distribution to `{{jetty_dest}}`
- Unpacks distribution to `{{jetty_dest}}` and creates symlink to `{{jetty_dest}}/jetty`
- Creates user/group and sets permissions if enabled
- Removes downloaded archive if enabled

Role Variables
--------------

```
# default options
jetty_version: 9.4.9.v20180320                                                          # Download latest version
jetty_checksum: 8c8245b3ec9fa92c41619dff81105cc5f6d3c68344162e9f397563bcae95a0c1        # Validate package with checksum
jetty_dest: /opt                                                                        # Destination folder

# default options for jetty user and group
jetty_user_create: true                                                                 # Set true to create user for Jetty
jetty_user_name: jetty                                                                  # User name for the created user
jetty_user_home: /opt/jetty                                                             # User home directory (will not be created)

jetty_group_create: true                                                                # Set true to create group for Jetty
jetty_group_name: jetty                                                                 # Group name for the created user

# default option to cleanup the zip archive
jetty_cleanup_archive: true                                                            # Set true to remove the downloaded .zip file

```

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: janesmae.jetty }

License
-------

[MIT](LICENSE)
