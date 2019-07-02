# Ansible-Role-Jetty

Installs the latest version of Jetty Servlet Engine from archive.

## Table of content

* [How to install](#how-to-install)
* [Actions role](#actions-role)
* [Role variables](#role-variables)
* [Example playbook](#example-playbook)
* [Support](#support)
* [Contributing](#contributing)
* [License](#license)

## How to install

```
ansible-galaxy install janesmae.jetty
```

## Actions role

- Downloads Jetty's distribution to `{{jetty_dest}}`
- Unpacks distribution to `{{jetty_dest}}` and creates symlink to `{{jetty_dest}}/jetty`
- Creates user/group and sets permissions if enabled
- Removes downloaded archive if enabled

## Role variables

```
# default options
jetty_version: 9.4.19.v20190610                                                         # Download latest version
jetty_checksum: 141be2f8738ce3bdf3210df02d85a7c2289603883bf2b72252aa55b5f39c0f00        # Validate package with checksum
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

## Example playbook

    - hosts: all
      roles:
         - { role: janesmae.jetty }

## Support

Please open an issue to receive support for this project.

## Contributing

Please read [CONTRIBUTING.md][contributing] for details on our code of conduct.

The process for submitting pull requests:.

* Fork it!
* Create your feature branch: `git checkout -b my-new-feature`
* Commit your changes: `git commit -am 'Add some feature'`
* Push to the branch: `git push origin my-new-feature`
* Submit a pull request

## License

The content of this repository is **&copy; Jaan Janesmae** and released under the **MIT License**.<br>
You can find a copy of this license in [LICENSE][license] file
or [https://opensource.org/licenses/MIT][license_web].

[contributing]:		./CONTRIBUTING.md
[license]:			./LICENSE
[license_web]:		https://opensource.org/licenses/MIT

