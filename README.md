ca_truster
==========

An Ansible role to trust one or more third-party CAs.

Role Variables
--------------

This role takes a list called ca_certs that it expects to be a list of
dictionaries, where each dictionary is a name (directory name semantics) and a
filename that is the CA certificate to trust.

```
ca_certs:
    - name: platina
      filename: platina-root-CA.crt
```

The actual file referred to in the variable ought to be able to be present in
any of the paths searched by Ansible for files.

Example Playbook
----------------

Assuming that the abovementioned ca_certs variable is set (group_vars, host_vars
 etc), the following should suffice:

```
    - hosts: servers
      roles:
         - mattgeddes.ca_truster
```

License
-------

GPL-2.0


Still To Do
----------

 * Doesn't yet support removal of old CA certificates

