nextcloud_client
================
[![Ansible Lint](https://github.com/oxivanisher/role-nextcloud_client/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-nextcloud_client/actions/workflows/ansible-lint.yml)

Configures the [nextcloud ppa](https://launchpad.net/~nextcloud-devs/+archive/ubuntu/client) repository and installs the client.

Role Variables
--------------

None

Example Playbook
----------------
``yaml
- name: Install Nextcloud client
  hosts: client
  collections:
    - oxivanisher.linux_desktop
  roles:
    - role: oxivanisher.linux_desktop.nextcloud_client
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.linux_desktop](https://galaxy.ansible.com/ui/repo/published/oxivanisher/linux_desktop/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-linux_desktop).
