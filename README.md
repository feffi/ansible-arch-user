# ansible-arch-user

Ansible role to configure/add a user.

[![Build Status](https://img.shields.io/travis/feffi/ansible-arch-user.svg)](https://travis-ci.org/feffi/ansible-arch-user) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-arch-user/total.svg)](https://github.com/feffi/ansible-arch-user) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-arch-user.svg?style=social&label=Fork)](https://github.com/feffi/ansible-arch-user) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-arch-user.svg?style=social&label=Star)](https://github.com/feffi/ansible-arch-user) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-arch-user.svg?style=social&label=Watch)](https://github.com/feffi/ansible-arch-user) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-arch-user/blob/master/LICENSE)

## Requirements

- Ansible 2.7.1

### ansible.cfg

```yaml
hash_behaviour = merge
```

## Install

Just add the role to your ``requirements.yml`` file:

```yaml
- src: https://github.com/feffi/ansible-arch-user.git
  name: ansible-arch-user
```

## Role Defaults Variables

```yaml
ansible_arch_user: {
  # The username/login to set
  name: "feffi",
  # The password in cleartext to set
  password: "SOMEPASSWORD",
  # The primary group of the new user
  group: "feffi",
  # Additional groups the new user belongs to
  groups: [
    "uucp",
    "wheel",
    "games",
    "rfkill"
  ],
  # The login shell of the user
  shell: "/usr/bin/zsh"
}

```

Example:

```yaml
- hosts: all
  vars:
    ansible_arch_user:
      # The username/login to set
      name: "feffi"
      # The password in cleartext to set
      password: "SOMEPASSWORD"
      # The primary group of the new user
      group: "feffi"
      # Additional groups the new user belongs to
      groups:
        - "uucp"
        - "wheel"
        - "games"
        - "rfkill"
      # The login shell of the user
      shell: "/usr/bin/zsh"
  roles:
    - { role: ansible-arch-user }
```
