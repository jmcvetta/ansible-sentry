Role Name
=========

Ansible role to deploy [Sentry](http://getsentry.com).


Requirements
------------

Ubuntu 14.04LTS


Role Variables
--------------

## Cryptographic keys

You *must* define several cryptographic key variables with long, *unique*
strings.  Do not reuse these keys, it is a security risk.  

'''yaml
# Do not use these keys - generate your own!
sentry_secret_key: ahrujiepheeTh6aex1jiyaejuxageyei
sentry_client_public_key: VaiQueughaisha5phael1eet
sentry_client_secret_key: faiphedev4ievei9haiMie5oW8eek6az
'''

The `pwgen` utility (`sudo apt-get install pwgen`) can be used to generate a
strong secret key.


## Other variables

Other variables have defaults:

```yaml
```


Dependencies
------------

- [gotansible.runit](https://github.com/gotansible/runit/)


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
