# Overview 
> Practical and efficient way of reusing tasks. <br/>

## What is a role?
- A collection of tasks grouped together because they achieve an overall objective (installing docker)
- The group of tasks are found in its own folder structure and can be called by any playbook as long as it has access to that specified folder.

## Directory Structure 
- ansible-galaxy init <name of role> command creates the file structure of the role.
<br/>
![role structure](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/role_structure.png)

## Using Roles 

### Playbook Configuration
- roles are included into plays as an ansible list
- Tasks can be run on a machine based on their role

### Variables
- Can be set in the original playbook under vars
- or can be set main.yml under the vars folder within the role
<br/>
![role vars](https://github.com/AlpaPhono/ansible_basics/blob/main/image_resources/role_vars.png)

