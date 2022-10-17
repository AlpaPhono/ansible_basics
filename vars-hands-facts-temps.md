# Overview 
Tools to streamline playbooks and make them more efficient<br/>

## Variables 
- A placeholder for an alternative value.
- changing the values of variables can change the outcome of the task in playbook.

### Scope 
Ansible has three primary scopes.<br/>
- Global - Set by the config, environment variables and command line
- Playbook - Play and contained structures, role defualts and cvars 
- Hosts - Variables associated with a host, inventory, facts or registered task outputs

### Vars Syntax

**Playbook**
> "{{ <VARIABLE_NAME>}}"<br/>

**CLI**
> ansible-playbook playbook.yaml -e <VARIABLE_NAME>=<VARIABLE_VALUE><br/>

variables can be specified in the cli when we run a playbook.<br/>

**Default variable**
Good for playbook templates fit for a specific purpose but for a different but similar outcome.<br/>

**Example**
---
- hosts: all
  remote_user: ubuntu
  become: true

  vars:
    app_repo: https//github.com/somerepo.git

Wherever app_repo variable is used in playbook. If not specifically defined the default will be as above<br/>

## Handlers
Tasks that are going to be run multiple times in one playbook can be made a *handler*<br/>
Handlers only run when notified.<br/>

- handlers are formatted exactly the same as how the task would be
- notify key is used as an argument under other tasks with the name of the handler to call the task to be ran.

## Facts 
> Variables that are predefined and are mostly about the Ansible host
- All standard Ansible facts can be viewed by running *ansible localhost -m setup*

## Hostvars 
> Facts but specific to external hosts.


