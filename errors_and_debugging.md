# Errors

- Ansible stops a playbook when it hits an error 
- you can choose to ignore some errors using the ignore errors property so that the play continues.

## The show must go on

The file errors.yml demonstrates the power of ignore_errors: property.
<br/>
The playbook has one task whos objective is to fail.<br/>
It uses the command module to call the false command. This a linux native command that returns a 0 for true and a 1 for false.<br/>
Ansible will read this false command as an error and stop the play.
<br/>
- using ignore_errors: true 
    - ansible will acknowledge the error but ignore it and continue with the play.

### Some errors some not

> For situations where a command throws multiple errors but some can be ignored and others can't.
<br/>

- failed_when 
    - tells ansible what a failure is in this context
    - first use register statement to store the output of the failed varialbe
    - followed by failed_when statement which searches for a word within the registered output of failed park
        - if the word is in the output it will fail, if not it will not fail.
<br/>

** example**
tasks:
  - name: Cause error
    command: '/bin/testerror exists'
    register: command_error
    failed_when: "'connect' in command_error.stderr'
    

# Debugging
