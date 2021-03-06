## What is ansible-sshd?

It is an [ansible](http://www.ansible.com/home) role to install openssh-server and configure it.

### What problem does it solve and why is it useful?

Often times you want to disable root logins and password based logins. This role sets those options by default but it also exposes every config value found in the default ubuntu 14.04 `sshd_config` file.

## Role variables

Below is a list of default values along with a description of what they do.

```
# To view what these commands do, check out:
# http://www.openssh.com/cgi-bin/man.cgi?query=sshd_config

sshd_port: "22"
sshd_listen_address: "0.0.0.0"
sshd_protocol: "2"
sshd_host_rsa_key: "/etc/ssh/ssh_host_rsa_key"
sshd_host_dsa_key: "/etc/ssh/ssh_host_dsa_key"
sshd_host_ecdsa_key: "/etc/ssh/ssh_host_ecdsa_key"
sshd_use_privilege_separation: "yes"
sshd_key_regeneration_interval: "3600"
sshd_server_key_bits: "768"
sshd_syslog_facility: "AUTH"
sshd_log_level: "INFO"
sshd_login_grace_time: "120"
sshd_permit_root_login: "no"
sshd_strict_modes: "yes"
sshd_rsa_authentication: "yes"
sshd_pubkey_authentication: "yes"
sshd_authorized_keys_file: "%h/.ssh/authorized_keys"
sshd_ignore_rhosts: "yes"
sshd_rhosts_rsa_authentication: "no"
sshd_host_based_authentication: "no"
sshd_ignore_user_known_hosts: "no"
sshd_permit_empty_passwords: "no"
sshd_challenge_response_authentication: "no"
sshd_password_authentication: "no"
sshd_gss_api_authentication: "no"
sshd_gss_api_cleanup_credentials: "yes"
sshd_x11_forwarding: "yes"
sshd_x11_display_offset: "10"
sshd_print_motd: "no"
sshd_print_last_log: "yes"
sshd_tcp_keep_alive: "yes"
sshd_max_startups: "10:30:100"
sshd_banner: "none"
sshd_accept_env: "LANG LC_*"
sshd_subsystem: "sftp /usr/lib/openssh/sftp-server"
sshd_use_pam: "yes"
```

## Attribution

Many thanks to [nickjj](https://github.com/nickjj/) for creating the [original version](https://github.com/nickjj/ansible-sshd/) of this role.
