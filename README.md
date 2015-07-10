# yauh.msmtp
Ansible role for setting up msmtp mail transport agent

## Requirements
SMTP server that msmtp may use for sending emails

## Role Variables
All emails sent via the `sendmail` or `mail` commands will be delivered to `msmtp_default_recipient`. The sender address is `msmtp_from`. SMTP credentials are configured using the `msmtp_hub_*` variables.

TLS certificate checks are enabled using `msmtp_tls_certcheck` and the trust file is configured via `msmtp_tls_trust_file`.

This role may send a testmail unless `msmtp_send_testmail` is set to `false`.

```
msmtp_default_recipient: admin@example.org
msmtp_from: tester@example.org
msmtp_hub_pass: test
msmtp_hub_port: 587
msmtp_hub_server: smtp.gmail.com
msmtp_hub_user: test@gmail.com
msmtp_tls_certcheck: 'on'
msmtp_tls_trust_file: /etc/ssl/certs/ca-certificates.crt
msmtp_send_testmail: yes
```

## Dependencies
None

## Example Playbook
In order to specify the SMTP credentials it is advisable to either use a local variable file or possibly even [Ansible vault](http://docs.ansible.com/playbooks_vault.html).

``` `

- hosts: all
- roles:
  - { role: yauh.msmtp, msmtp_send_testmail: false }
```

## License
BSD

## Author Information
Stephan Hochhaus stephan@yauh.de

[https://github.com/yauh](https://github.com/yauh)
