# HDP ANSIBLE API

This Projects aims at installing [HDP](https://docs.hortonworks.com/) clusters
managed by [Apache Ambari](https://ambari.apache.org/) using [Ansible](https://www.ansible.com/).

It uses Ambari's REST API to populate the database and install HDP Stack.

## Version Supports

- Ambari
  *  2.6.2.2
  *  2.6.2.0
  *  2.6.1.5
  *  2.6.1.0


- HDP Stacks

It's supports all HDP Stack than Ambari 2.6.x version supports.

You should use [Hortonworks Support Matrix](https://supportmatrix.hortonworks.com/).

You should adjust your VDF file to match the stack you need.
Look at an example on [HDP 2.6 repositories VDF definitions](https://docs.hortonworks.com/HDPDocuments/Ambari-2.6.2.2/bk_ambari-installation/content/hdp_26_repositories.html).


## Hosts - Cluster definition - Playbook file

Check the folder examples

Each services in "cluster_services" needs specific groups in your cluster file. Check examples/cluster.yaml

## Run

Bare metal:

`ansible-playbook -i hosts playbook.yml -u root -k myRootPassword`

Vagrant:

`ansible-playbook -i hosts playbook.yml -u vagrant -b`

## Requirements

- Ansible on your deployment machine
- JDK 1.8 installed on your hosts
- Ambari-server and Ambari-agent installed
- Mysql/MariaDB or PostgreSQL Database installed for Ambari Server Backend
- NTPD Installed
- Network Resolution
- Certificates in keystore/truststore jks if you want to enable SSL

## WIP
[The original repo](https://github.com/yyounes75/hdp-ansible) is being migrated to this one
to add all the other role like JAVA, mysql , Kerberos, Openldap to have a full deployment
support.

## TODO

- List of components by services
- ~~Auto create system user~~
- ~~Config groups~~
- Refactoring
- ~~Kerberos role~~
- Auto load correct VDF file
- Autogenerate certs with default keystore
- HDP 3.1
