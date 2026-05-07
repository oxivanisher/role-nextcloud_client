nextcloud_client
================
[![Ansible Lint](https://github.com/oxivanisher/role-nextcloud_client/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-nextcloud_client/actions/workflows/ansible-lint.yml)

Configures the [nextcloud ppa](https://launchpad.net/~nextcloud-devs/+archive/ubuntu/client) repository and installs the client.

Notes
-----

The GPG key is fetched from `keyserver.ubuntu.com` using `get_url` and then converted to a binary keyring with `gpg --dearmor`. This two-step approach is necessary because the Hockeypuck keyserver randomizes the order of ASCII armor headers (`Comment:` / `Version:`) between requests, causing raw checksum comparisons to always differ and marking the task as changed on every run. Converting to binary format strips these headers and produces deterministic output.

Once keyserver.ubuntu.com upgrades to Hockeypuck 2.4 (which adds a stable binary export API), this workaround can be replaced with a direct `get_url` download of the binary key.

Role Variables
--------------

None

Example Playbook
----------------
```yaml
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
