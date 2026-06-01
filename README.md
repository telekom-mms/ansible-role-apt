<!-- BEGIN_ANSIBLE_DOCS -->

[![Linting](https://github.com/telekom-mms/ansible-apt/workflows/linting/badge.svg)](https://github.com/telekom-mms/ansible-apt/actions?query=workflow%3Alinting)
[![Molecule](https://github.com/telekom-mms/ansible-apt/workflows/molecule/badge.svg)](https://github.com/telekom-mms/ansible-apt/actions?query=workflow%3Amolecule)

# Ansible role telekom_mms.apt

Thankfully forked from [weareinteractive.apt](https://github.com/weareinteractive/ansible-apt).

Ansible role to manage apt packages and repositories on Debian-based systems.

## Supported Operating Systems
- Ubuntu
  - all
- Debian
  - all

## Role Variables

- `apt_aptitude_solution_cost`
  - Default: `[]`
  - Description: Aptitude solution cost settings.
  - Type: list of 'str'
  - Required: no
- `apt_auto_clean_interval`
  - Default: `0`
  - Description: Run apt autoclean every n days, where 0 disables it.
  - Type: int
  - Required: no
- `apt_autoclean`
  - Default: `True`
  - Description: Remove package files that can no longer be downloaded.
  - Type: bool
  - Required: no
- `apt_autoremove`
  - Default: `True`
  - Description: Remove packages no longer needed as dependencies.
  - Type: bool
  - Required: no
- `apt_cache_valid_time`
  - Default: `3600`
  - Description: Time in seconds before apt cache is considered stale.
  - Type: int
  - Required: no
- `apt_deb_packages`
  - Default: `[]`
  - Description: Local .deb package files to install.
  - Type: list of 'str'
  - Required: no
- `apt_dependencies`
  - Default: `['aptitude', 'python3-apt', 'python3-pycurl']`
  - Description: Dependencies required to manage apt packages.
  - Type: list of 'str'
  - Required: no
- `apt_download_upgradeable_packages`
  - Default: `0`
  - Description: Download upgradeable packages every n days, where 0 disables it.
  - Type: int
  - Required: no
- `apt_http_pipeline_depth`
  - Default: ``
  - Description: Optional apt HTTP pipeline depth value.
  - Type: int
  - Required: no
- `apt_http_proxy_address`
  - Default: ``
  - Description: Optional HTTP proxy address used by apt.
  - Type: str
  - Required: no
- `apt_install_recommends`
  - Default: `False`
  - Description: Whether recommended packages should be installed.
  - Type: bool
  - Required: no
- `apt_install_suggests`
  - Default: `False`
  - Description: Whether suggested packages should be installed.
  - Type: bool
  - Required: no
- `apt_keys`
  - Default: `[]`
  - Description: GPG keys to register for external repositories.
  - Type: list of 'dict'
  - Required: no
- `apt_mails`
  - Default: `[]`
  - Description: Email recipients for unattended-upgrades notifications.
  - Type: list of 'str'
  - Required: no
- `apt_package_state`
  - Default: `present`
  - Description: Default package state for managed packages.
  - Type: str
  - Required: no
- `apt_packages`
  - Default: `[]`
  - Description: Packages to ensure are installed or managed.
  - Type: list of 'str'
  - Required: no
- `apt_periodic`
  - Default: `True`
  - Description: Enable periodic apt update and upgrade behavior.
  - Type: bool
  - Required: no
- `apt_policy`
  - Default: `101`
  - Description: Value used for policy-rc.d while installing packages.
  - Type: int
  - Required: no
- `apt_preferences`
  - Default: `[]`
  - Description: Apt pinning preferences to manage.
  - Type: list of 'dict'
  - Required: no
- `apt_remount_filesystems`
  - Default: `[]`
  - Description: File systems to remount before running apt tasks.
  - Type: list of 'str'
  - Required: no
- `apt_remove_purge`
  - Default: `False`
  - Description: Purge package configuration files when removing packages.
  - Type: bool
  - Required: no
- `apt_remove_recommends`
  - Default: `False`
  - Description: Allow autoremove to remove recommended packages.
  - Type: bool
  - Required: no
- `apt_remove_suggests`
  - Default: `False`
  - Description: Allow autoremove to remove suggested packages.
  - Type: bool
  - Required: no
- `apt_repositories`
  - Default: `[]`
  - Description: Repositories to manage.
  - Type: list of 'dict'
  - Required: no
- `apt_repositories_use_deb822`
  - Default: `True`
  - Description: Use deb822_repository format for apt repositories.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades`
  - Default: `True`
  - Description: Enable unattended-upgrades.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_allowed`
  - Default: `['${distro_id}:${distro_codename}-security']`
  - Description: Allowed origins for unattended upgrades.
  - Type: list of 'str'
  - Required: no
- `apt_unattended_upgrades_automatic_reboot`
  - Default: `False`
  - Description: Reboot automatically when required after unattended upgrades.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_automatic_reboot_time`
  - Default: `now`
  - Description: Reboot time used when automatic reboot is enabled.
  - Type: str
  - Required: no
- `apt_unattended_upgrades_automatic_reboot_with_users`
  - Default: `False`
  - Description: Reboot automatically even if users are currently logged in.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_autoremove`
  - Default: `True`
  - Description: Auto-remove unused dependencies after unattended upgrades.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_blacklist`
  - Default: `[]`
  - Description: Packages excluded from unattended upgrades.
  - Type: list of 'str'
  - Required: no
- `apt_unattended_upgrades_download_timer_override`
  - Default: ``
  - Description: Override settings for apt-daily download timer.
  - Type: dict
  - Required: no
- `apt_unattended_upgrades_minimal_steps`
  - Default: `False`
  - Description: Split upgrades into small chunks to support interruption.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_notify_error_only`
  - Default: `True`
  - Description: Send email notifications only when errors occur.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_origins`
  - Default: `[]`
  - Description: Origins patterns to control package upgrade sources.
  - Type: list of 'str'
  - Required: no
- `apt_unattended_upgrades_syslog_enable`
  - Default: `False`
  - Description: Enable logging unattended-upgrades events to syslog.
  - Type: bool
  - Required: no
- `apt_unattended_upgrades_syslog_facility`
  - Default: `daemon`
  - Description: Syslog facility to use for unattended-upgrades logs.
  - Type: str
  - Required: no
- `apt_unattended_upgrades_upgrade_timer_override`
  - Default: ``
  - Description: Override settings for apt-daily-upgrade timer.
  - Type: dict
  - Required: no
- `apt_update_package_lists`
  - Default: `1`
  - Description: Run apt-get update every n days, where 0 disables it.
  - Type: int
  - Required: no
- `apt_upgrade`
  - Default: `False`
  - Description: Upgrade mode (safe, full, dist) or false to disable upgrades.
  - Type: raw
  - Required: no

## Dependencies

None.

## Example Playbook

```
- hosts: all
  vars:
    apt_cache_valid_time: 7200
    apt_packages:
      - vim
      - tree
      - name: ca-certificates
        state: latest
        hold: true
      - name: zsh
        state: absent
        purge: true
    apt_deb_packages:
      - "https://releases.hashicorp.com/vagrant/2.1.5/vagrant_2.1.5_x86_64.deb"
    apt_mails:
      - root
    apt_preferences:
      - file: perl
        package: perl
        pin: "version 5.20*"
        priority: 1001
    apt_unattended_upgrades_notify_error_only: false
    apt_remove_recommends: true
    apt_remove_suggests: true
    apt_remove_purge: true
  roles:
    - telekom_mms.apt

```

# License

MIT

<!-- END_ANSIBLE_DOCS -->
