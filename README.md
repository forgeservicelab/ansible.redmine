Redmine
=======

This is a playbook to provision the Support node for FORGE Service Lab.

It installs the following components:

- Redmine
- Redmine plugins
- Openfire (XMPP)

The different components are tagged to enable fine targeting of component installation

Extra Variables
===============

While most variables are distributed with the playbook, the target hosts are identified by the `target` variable, expected as an extra var.

Example Runs
============

###Full installation
```
$ ansible-playbook -i inventory --ask-vault-pass --extra-vars 'target=testing' redmine.yml
```

###Just install Redmine core
```
$ ansible-playbook -i inventory --ask-vault-pass --extra-vars 'target=testing' --tags=core redmine.yml
```

###Just install Openfire
```
$ ansible-playbook -i inventory --ask-vault-pass --extra-vars 'target=testing' --tags=xmpp redmine.yml
```

###Do not install plugins
```
$ ansible-playbook -i inventory --ask-vault-pass --extra-vars 'target=testing' --skip-tags=plugins redmine.yml
```

###Install a specific plugin only
```
$ ansible-playbook -i inventory --ask-vault-pass --extra-vars 'target=testing' --tags=backlogs redmine.yml
```
