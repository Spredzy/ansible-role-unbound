# Ansible Role: Unbound

This role installs the recursive DNS server [Unbound](https://unbound.net/) from [NLnet Labs](https://www.nlnetlabs.nl/).
This role aims to configure every aspect of an unbound installation. If you have to do anything by hand, please [report it](https://github.com/Spredzy/ansible-role-unbound/issues/new).

## Example playbook

```
- name: DNS recursive server
  hosts: unbound
  roles:
    - { role: Spredzy.unbound }
```

## Role variables

The role variables follow a common pattern. Unbound file configuration have 5 sections :

  * server
  * python
  * remote-control
  * stub-zone
  * forward-zone

The naming convention is `unbound_sectionname_variablename` with every '-' replaced by '\_'

Find below the list of currently supported variables, please feel free to submit a pull request for inclusion of new ones.

| Variable name                                 | Section        | Variable          | Type                            |
|-----------------------------------------------|----------------|-------------------|---------------------------------|
| unbound\_server\_interface                    | server         | interface         | array                           |
| unbound\_server\_access\_control              | server         | access\_control   | array                           |
| unbound\_server\_hide\_identity               | server         | hide-identity     | string (Available: 'yes', 'no') |
| unbound\_server\_hide\_version                | server         | hide-version      | string (Available: 'yes', 'no') |
| unbound\_remote\_control\_control\_enable     | remote-control | control-enable    | string (Available: 'yes', 'no') |
| unbound\_remote\_control\_control\_interface  | remote-control | control-interface | array                           |
| unbound\_remote\_control\_control\_port       | remote-control | control-port      | integer                         |
| unbound\_remote\_control\_server\_key\_file   | remote-control | server-key-file   | string                          |
| unbound\_remote\_control\_server\_cert\_file  | remote-control | server-cert-file  | string                          |
| unbound\_remote\_control\_control\_key\_file  | remote-control | control-key-file  | string                          |
| unbound\_remote\_control\_control\_cert\_file | remote-control | control-cert-file | string                          |
| unbound\_python\_python\_script | python      | python         | python-script     | string                          |
| unbound\_forward\_zones                       | forward-zone   | forward-zone      | array of hash                   |
| unbound\_stub\_zones                          | stub-zone      | stub-zone         | array of hash                   |


## Dependencies

None.

## License

Apache 2.0

## Author

Yanis Guenane  <yanis+ansible@ guenane.org>
