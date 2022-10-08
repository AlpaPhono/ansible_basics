# inventory 

- Used for defining **hosts** for your infrastructure to connect with and configure.
- default location located in /etc/ansible/hosts file
    - alternatice inventory file can be specified using *-i* opion on command line 

    **example**<br/>
    <!-- specify an inventory file -->
     <br/>
    anible-playbook -i my_inventory.yaml playbook.yaml<br/>
    <!--specify a list of hosts -->
    <br/>
    ansible-playbook -i '192.168.1.123,192.168.1.124' playbook.yaml<br/>

    - Another reason for making a seperate inventory file is for running tasks on different environments. (development, testing, deployment)<br/>
        **example**
        ansible-playbook -i staging.yaml playbook.yaml<br/>
        ansible-playbook -i development.yaml playbook.yaml<br/>

- hosts can be grouped so that the playbook can perform tasks on multiple machines at once.
- child groups are multiple groups that constituents of a bigger group.

**Group syntax examples**
![Group1](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/cloudgroup.png)
![Group2](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/comunitygroup.png)

**Child group syntax examples**
![Nested](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/nestedgroup.png)
![Child](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/childgroup.png)


## Configuration Overview
- Configured in yaml:
### All

## Variable Files 
Variables can be stored in the inventory file but should be stored in thier own variable file. <br/>
- store group and host specific vaiables in their own files 
- hosts files in /etc/ansible/host_vars folder
- groups in /etc/ansible/group_vars folder
- Name of variable file should match the host or group name


## Connectiing to Remote Hosts
- ssh for linux
- WinR (Windows Remote Management) for Windows
- Ansible allows specific connection settings per group and per host. 
- if all hosts share connection settings you can use the ansible.cfg



# Dynamic Inventory 
>For connecting to servers that are frequently created and destroyed.
- Allows you to use an executable to get inventory from some location (cloud platform.)
<br/>
Dynamic inventory scripts have been created for common cloud platforms that need to be downloaded and slightly edited<br/>

