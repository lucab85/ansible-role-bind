# Ansible Role: DNS

[![CI](https://github.com/lucab85/ansible-role-bind/workflows/CI/badge.svg?event=push)](https://github.com/lucab85/ansible-role-bind/actions?query=workflow%3ACI)

Installs and configures DNS server on Fedora/RHEL/CentOS servers.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: dns
      roles:
        - role: dns
          become: yes

## Role Variables

Available variables are listed along with default values in `defaults/main.yml`.

## Dependencies

None.

## Example Playbook

    - hosts: dns
      become: yes
      vars_files:
        - vars/main.yml
      roles:
        - ansible-role-dns

*Inside `vars/main.yml`*:

    bind_zones_entries:
      - {name: "example.com", type: "master", file: "example.com.zone", template: db}
      - {name: "1.0.10.in-addr.arpa", type: "master", file: "example.com.rr.zone", template: rev}

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Luca Berton](https://www.lucaberton.it/).
