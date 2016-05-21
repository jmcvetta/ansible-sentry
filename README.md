Role Name
=========

Ansible role to deploy [Sentry](http://getsentry.com).


Requirements
------------

Ubuntu 14.04LTS


Role Variables
--------------

You *must* define a variable `sentry_secret_key` with a long random string.
The `pwgen` utility (`sudo apt-get install pwgen`) can be used to generate
a strong secret key.  E.G.

'''yaml
# Do not use this key - generate your own!
sentry_secret_key: ahrujiepheeTh6aex1jiyaejuxageyei
'''

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
