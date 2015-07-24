# Ansible Role: Sculpin

Installs the [Sculpin](https://sculpin.io) executable on RedHat/CentOS and Debian/Ubuntu servers.

## Requirements

Sculpin requires some PHP packages to be installed. `php-cli` and `php-xml` on RedHat/CentOS, and `php5-cli` on Ubuntu/Debian.

These are installed as part of role.

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

    sculpin_version: master

The version of Sculpin to be installed. (examples: `master` for the latest development code, or a release tag such as `v2.0.0`).

    sculpin_install_path: /usr/local/share/sculpin

The location of the entire Sculpin installation (includes all the supporting files, as well as the Sculpin executable file.

    sculpin_path: /usr/bin/sculpin

Where Sculpin will be installed. This should be somewhere that's declared as part of `$PATH` so that the command is available.

## Dependencies

* geerlingguy.git (Installs Git).
* geerlingguy.php (Installs PHP).
* geerlingguy.composer (Installs Composer).

## Example Playbook

    - hosts: all
      vars:
        sculpin_version: v2.0.0
        php_packages: [ 'php-cli', 'php-xml' ]
        php_enable_webserver: 'false'
      roles:
        - opdavies.sculpin

## Licence

BSD

## Author Information

[Oliver Davies](http://www.oliverdavies.co.uk).
