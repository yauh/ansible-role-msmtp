MSMTP
=====

This role installs and configures the leightweight smtp client msmtp. It can be used to replace sendmail and use an SMTP server such as GMail to send mails directly instead of requiring you to create a mail server on your machine with e.g. smarthosts.

It also sends a test mail to the defined from_address.

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows.

Remember that you **must change** these variables or else msmtp will not be able to send mails!

	mail:
	  host: smtp.gmail.com              # smtp host to be used
	  port: 587                         # smtp port to be used - e.g. 25 or 587
	  user: youraddress@gmail.com       # smtp account name 
	  password: password                # smtp password
	  from_address: server@example.org  # sender address and used as recipient for test mail

Examples
========

Set up mailing functionality on all servers

	- hosts: all
	  sudo: True
	  roles:
	     - { role: role-msmtp, tags: msmtp}


Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Stephan Hochhaus <stephan@yauh.de>

[yauh.de](http://yauh.de)


