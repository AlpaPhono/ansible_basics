# Introduction

Notes on how the the basic playbook was converted into the intermediate_playbook.yml 

# Handlers 
- For Tasks used frequently within a play, they are turned into handlers to reduce repetition
- only run when notified

In this example we converted the restart apache task into a handler as it was used twice in the basic playbook 

# Variables 
- removing the hard coded file paths and replaced them with variables.
- created a variables section in the play

# Templates 
They use templates on the apache config file however this is just for demonstration and so does not currently reflect the full changes.<br/>
