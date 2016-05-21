Role Name
=========

Ansible role to deploy [Sentry](http://getsentry.com).


Requirements
------------

Ubuntu 14.04LTS

Redis and PostgreSQL instances are required, but are not installed by this
role.  For Redis I've had good experience with
[`jpnewman.redis`](https://github.com/jpnewman/ansible-role-redis).  For
PostgreSQL you can install locally with APT.  Or if you're on
[AWS](https://en.wikipedia.org/wiki/Amazon_Web_Services) you should use
[RDS](https://aws.amazon.com/rds/)


Role Variables
--------------

### Cryptographic keys

You *must* define several cryptographic key variables with long, *unique*
strings.  Do not reuse these keys, it is a security risk.  

```yaml
# Do not use these keys - generate your own!
sentry_secret_key: ahrujiepheeTh6aex1jiyaejuxageyei
sentry_client_public_key: VaiQueughaisha5phael1eet
sentry_client_secret_key: faiphedev4ievei9haiMie5oW8eek6az
```

The `pwgen` utility (`sudo apt-get install pwgen`) can be used to generate a
strong secret key.


### Other variables

All variables have defaults:

```yaml
# Sentry will run as this user
sentry_user: sentry

# 
# Database
#
sentry_db_engine: sentry.db.postgres
sentry_db_name: sentry
sentry_db_user: sentry
sentry_db_password:
sentry_db_host:
sentry_db_port:

#
# Email Sending
#
sentry_mail_backend: 'smtp'  # Use dummy if you want to disable email entirely
sentry_mail_host: 'localhost'
sentry_mail_port: 25
sentry_mail_username: ''
sentry_mail_password: ''
sentry_mail_use_tls: false
# The email address to send on behalf of
sentry_mail_from: 'root@localhost'

#
# Redis
# 
sentry_redis_host: 127.0.0.1
sentry_redis_port: 6379

# 
# Web
#
sentry_web_host: '0.0.0.0'
sentry_port: 9000

#
# Bootstrap
#
sentry_org_name: Sentry
sentry_team_name: Sentry
sentry_project_name: "My Project"
```


Dependencies
------------

- [gotansible.runit](https://github.com/gotansible/runit/)


Installation
------------

```bash
ansible-galaxy install jmcvetta.sentry
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: monitor
  roles:
	- jmcvetta.sentry
```


License
-------

This is Free Software, released under the terms of the MIT license.  See file
`LICENSE` for more details.  Resist intellectual serfdom - the ownership of
ideas is akin to slavery.


Author Information
------------------

[Jason McVetta](mailto:jason.mcvetta@gmail.com)

Paid support and consulting services are available from [Silicon
Heavy](http://siliconheavy.com).
