wildfly with mysql drivers
====

This repository contains a set of Ansible based roles and playbooks to demonstrate the integration between a [Wildfly](https://wildfly.org/) cluster with a mysql database

## Set up

The following sections describe the steps necessary to prepare your machine for execution

### JCliff Integration

First of all, you'll need to install the [JCliff Ansible collection](https://github.com/middleware_automation/ansible_collections_jcliff):

    $ ansible-galaxy collection install -r collections/requirements.yml

### Ansible Inventory

Ansible groups are used to define the Wildfly instances. Configure these groups in the [hosts](inventory/hosts) file similar to the following:

```
[demo]

[wildfly]
192.168.22.4


[demo:children]
wildfly
```

## Execution

That's all! You can now run the playbook to set up the demo:

    $ ansible-playbook -i inventory/ playbooks/demo.yml -Kk

