# Ansible Role for SSHD Hardening
**Author/Maintainer:** Josh Murphy

## Overview

This Ansible role hardens the SSHD Config by doing the below:
```yaml
- Sets Allowed SSH Ciphers
- Creates SSH Users
- Adds to Sudo/Wheel if desired.
- Sets SSH Allowed Users
- Copys SSH PubKeys
- Sets Allow/Deny Root SSH Login
- Sets Allow/Deny Empty Passwords
- Sets Allow/Deny Password Authentication
- Sets Allow/Deny Pubkey Authentication
- Sets Allow/Deny X11Forwarding
- Sets an Inactivity Timeout on SSH Sessions
- Sets Allow/Deny HostBasedAuthentication
- Sets Allow/Deny IgnoreRhosts
- Sets SSH LogLevel
- Sets MaxAuthTries
- Sets MaxSessions
- Sets MaxStartups
- Sets PrintMotd
- Restarts when any of the above has changed to apply settings.
Backups of the SSHD config are taken when any changes happen so you can revert easily if needed.
```

## Dependencies
- ansible.posix

## Supported Platforms and Derivatives
The files changed should exist on every RedHat and Debian Distro. Below are the explicitly tested Distros.
```yaml
# RedHat
Rocky 10/9
CentOS 10/9
Fedora 43/42
Oracle 10

  # Debian
Ubuntu 24.04/22.04
Debian 13
Alma 10
Mint 22
```

## Example Playbook

```yaml
- hosts: all
  become: yes

  roles:
    - role: openssh_hardening
```

### From Ansible Galaxy

```bash
ansible-galaxy install crowjm64.openssh_hardening
```

This role was created and is maintained by **[CrowJM64](https://github.com/CrowJM64)**.
