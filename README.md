# Ansible Role: Sculpin

Installs the [Sculpin](https://sculpin.io) executable on RedHat/CentOS and Debian/Ubuntu servers.

The intended use case for this is to make compiling Sculpin sites available to a continuous integration server such as [Jenkins](http://jenkins-ci.org) to automate the build process, rather than installing it on your production server and have it compiling your site in real-time.

## Requirements

Sculpin requires some PHP packages to be installed. `php-cli` and `php-xml` on RedHat/CentOS, and `php5-cli` on Ubuntu/Debian.

These are installed as part of role.

## Role Variables

    sculpin_version: latest
    sculpin_version: 2.0.0

The version of Sculpin to be installed. This can either be `latest` or a version number such as `2.0.0`.

    sculpin_path: /usr/bin/sculpin

Where Sculpin will be installed. This should be somewhere that's declared as part of `$PATH` so that the command is available.

## Dependencies

None.

## Example Playbook

    - hosts: all
      vars_files:
        - vars/main.yml
      roles:
        - opdavies.sculpin

*Inside `vars/main.yml`*:

    sculpin_path: /usr/local/bin/sculpin
    sculpin_version: 2.0.0

## Licence

BSD

## Author Information

[Oliver Davies](http://www.oliverdavies.co.uk).
