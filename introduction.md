# Ansible
> Open-sourced software provisioning, configuration, application deployment tool <br/>
>YAML language<br/>

## Architecture 
Powerful, can spin thousands of nodes at any given time.<br/>
- agentless

## Usage
- Ad-hoc Commands - one off configurations (CLI)
- Playbooks - declarative way of defining tasks
- Ansible Tower

## Installation 

### Using Apt
sudo apt update<br/>
sudo apt install software-properties-common<br/>
sudo apt-add-repository --yes --update ppa:ansible/ansible <br/>
sudo apt install ansible <br/>

### Using Pip 
- Ansible requires Python to be installed to run on any machine.
- With pyhton installed you can use the Pop package manager to install Ansible on any machine consistently 

<!--make sure ~/.local/bin exists and is on your PATH-->
mkdir -p ~/.local/bin <br/>
echo 'PATH=$PATH:~/.local/bin' >> ~/.bashrc <br/>
source ~/.bashrc <br/>
<!--install pip3-->
sudo apt install python3-pip -y <br/>
<!--install ansible with pip3-->
pip3 install --user ansible <br/>
<!--check that ansible has been installed-->
ansible --version <br/>

### Configure a playbook to install a Web Server
<!-- Command to install NGINX-->
ansible 127.0.0.1 -m apt -a "name=nginx state=present update_cache=true" --become <br/>

*-m apt* lets Ansible know to use the apt module and the *-a* defines any arguments to pass to that module. *--become* is giving sudo privileges for this play. <br/>
Ansible returns a JSON object, showing you that is has completed the task.