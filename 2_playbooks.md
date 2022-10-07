# Playbooks

Used for the most of the configuration in Ansible. They can  be used to manage configurations and deployments on remote machines.<br/>

# Configuration
Play books contain a lsit of *Plays* <br/>
Each play has various properties including the *tasks* to run and the *hosts* to run those tasks on <br/>

## Hosts 
The hosts property sets which machines Ansible will be running these plays on.<br/>
This can be a list of IP addresses and domain names or groups pulled in from the inventory<br/>

The inventory is a YAML file that has a list of all the hosts that plays can be run on

## Tasks & Modules
Tasks are parts of the play that actually get executed on the remote machine.<br/>
Tasks utilise **modules** to carry out particular tasks.<br/>

**Modules**
Modules are wrapprs around code designed for a specific purpose. <br/>
- copy module allows copying from one place to another 
- Git module allows interaction with Git services
- Ping module allows you to pig services

**Tasks**
Modules are called from tasks.<br/>
- Tasks consist of a module and some metadata
    - Name 
    - Handler notifications 
    - ignore errors
    - conditionals
    - loops
![Tasks](https://github.com/AlpaPhono/ansible_basics/blob/main/tasks.png)
