# Playbooks

Used for the most of the configuration in Ansible. They can  be used to manage configurations and deployments on remote machines.<br/>
- Written in YAML language .ylm<br/>
- whitespace sensitive

# Configuration
Play books contain a lsit of *Plays* <br/>
Each play has various properties including the *tasks* to run and the *hosts* to run those tasks on <br/>

## Hosts 
The hosts property sets which machines Ansible will be running these plays on.<br/>
This can be a list of IP addresses and domain names or groups pulled in from the inventory<br/>

The inventory is a YAML file that has a list of all the hosts that plays can be run on

## Tasks & Modules
Tasks are parts of the play that actually get executed on the remote machine.<br/>
A task is a wrapper around modules which consists of metadata that Ansible ses to execute the module in the way you want.<br/>

**Modules**
Modules are wrapprs around code designed for a specific purpose. <br/>
- copy module allows copying from one place to another 
- Git module allows interaction with Git services
- Ping module allows you to pig services

Most modules accept arguments as key=value pairs<br/>
<br/>
Ansible has information on its modules in its documentation letting the user know which keys are required and which are optional.<br/>

### Custom Modules 
- Custom modules can be created with any language that can write JSON to STDOUT
    - pyhton
    - powershell
    - bash
    - ruby

The language the custom module is written in needs to be on the host as ansible copies the code over to the host and executes the code.<br/>
**Example**
- Use ansible test module as a template for your own.
- Download ansible source code to get it
![sourcecode install](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/ansiblesourcecode.png)
<br/>
- run a script so that environment variables are configured for development
![sourcecode install](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/ansibleenvironmentset.png)

**Tasks**
Modules are called from tasks.<br/>
- Tasks consist of a module and some metadata
    - Name 
    - Handler notifications 
    - ignore errors
    - conditionals
    - loops
<br/>

![Tasks](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/tasks.png)

# Plays
- Plays consist of tasks, hosts variables and additional settings
- Playbooks can have multiple plays

![Tasks](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/play.png)

