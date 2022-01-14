Wildfly with mysql drivers
====

This repository contains a set of Ansible based roles and playbooks to demonstrate the deployment of a [Wildfly](https://wildfly.org/) cluster, mysql database, mysql drivers, and kitchensink application configured to connect to mysql.

## Set up

The following sections describe the steps necessary to prepare your machine for execution

### JCliff Integration

First of all, you'll need to install the [JCliff Ansible collection](https://github.com/middleware_automation/ansible_collections_jcliff):

    $ ansible-galaxy collection install -r collections/requirements.yml

### Ansible Inventory

Ansible groups are used to define the Wildfly instances. Configure these groups in the [hosts](inventory/hosts) file similar to the following:

```
# Placeholder Group
[demo]

# Wildfly Group
[wildfly]
192.168.122.11
192.168.122.125

# Mysql database Group
[mysql]
192.168.122.84

[demo:children]
wildfly
mysql
```

## Execution

That's all! You can now run the playbook to set up the demo:

    $ ansible-playbook -i inventory/hosts playbooks/demo.yml 

## Cleanup

To remove the demo, run the following:

    $ ansible-playbook -i inventory/hosts playbooks/demo_cleanup.yml



