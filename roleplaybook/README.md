# Role playbook

>This documents converting the *intermediate playbook* in the basic playbook folder into the *roleplaybook* and adding roles to it to make it more readable.



## Combining Roles 
In this example we have a webserver role then we have a role for installing the flask web application. <br/>
These are seperate roles that are combined to get the website running. <br/>
We could even have a role for installing an sql database ect.<br/>

## ogr
- In the web application role a templates folder needed to be created. So that the apache config file could be placed in there=.

- When breaking tasks down into multiple yml files you must use the include statement in the main.yml file so that the root playbook is aware of the extra tasks in the files.