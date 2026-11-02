# Ansible Role for SSHD Hardening
**Author/Maintainer:** Josh Murphy

## Overview

This Ansible role hardens the SSHD Config by doing the below:
```yaml
- Creates SSH Users
- Adds to Sudo/Wheel if desired.
- Sets SSH Allowed Users
- Copys SSH PubKeys
Copies openssh-hardening.conf template to cover the following settings:
- Allowed SSH Ciphers
- Allow/Deny Root SSH Login
- Allow/Deny Empty Passwords
- Allow/Deny Password Authentication
- Allow/Deny Pubkey Authentication
- Allow/Deny X11Forwarding
- Inactivity Timeout on SSH Sessions
- Allow/Deny HostBasedAuthentication
- Allow/Deny IgnoreRhosts
- SSH LogLevel
- MaxAuthTries
- MaxSessions
- MaxStartups
- PrintMotd

It will then restarts when any of the above has changed to apply settings.

Removal of the template from /etc/ssh/sshd_config.d/ and a subsequent restart of the sshd service will clear any settings changed by this role.
```

## Dependencies
- ansible.posix

## Supported Platforms and Derivatives
The files changed should exist on every RedHat and Debian Distro. Below are the explicitly tested Distros.
```yaml
# RedHat
Rocky 10,9
Fedora 44,43
Oracle 10,9

# Debian
Ubuntu 26.04,24.04
Debian 13,12

# Other
AmazonLinux 2027,2023
OpenSuse Leap 15
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
