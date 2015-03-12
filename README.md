Stouts.apt
==========

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.apt.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.apt)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.apt-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/852)

Ansible role apt which help you with:

* updating the apt-cache
* control if you want recommended packages
* control if you want suggested packages
* optionally add additional sources
* optionally install build-essential packages
* optionally install default packages
* optionally install additional packages

#### Variables

```yaml
apt_enabled: yes                  # Enable the role
apt_cache_valid_time: 3600        # Time (in seconds) the apt cache stays valid
apt_upgrade: no                   # Perfoms aptupgrade. Values are (safe, full, dist)
apt_install_recommends: no        # Install the "recommended" packages
apt_install_suggests: no          # Install the "suggested" packages
apt_sources_reset: no             # Mute original APT sources (it is intended to use a mirror directly)
apt_repositories: []              # List of sources which be added
apt_default_packages_install: no  # Install some packages (see list bellow)
apt_default_packages:             # List of packages which will be installed
  - command-not-found
  - curl
  - git
  - htop
  - iftop
  - iotop
  - mercurial
  - nmap
  - pciutils
  - screen
  - sysstat
  - vim
  - wget
```


#### Usage

Add `Stouts.apt` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.apt

  vars:
    apt_install_recommends: yes
    apt_install_packages: yes
    apt_repositories:
      - ppa:fkrull/deadsnakes
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.apt/issues)!
