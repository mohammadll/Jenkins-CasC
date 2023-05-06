# Jenkins-CasC

### Introduction


Setting up Jenkins is a complex process, as both Jenkins and its plugins require some tuning and configuration, with dozens of parameters to set within the web UI manage section.

Jenkins Configuration as Code provides the ability to define this whole configuration as a simple, human-friendly, plain text yaml syntax. Without any manual steps, this configuration can be validated and applied to a Jenkins controller in a fully reproducible way. With JCasC, setting up a new Jenkins controller will become a no-brainer event.


----------

### What do we want to do ?

- we are going to Provision a jenkins server on virtualbox platform with Terraform (you can also use other platforms like aws):
   - we used ubuntu vagrant box
- we have an ansible directory that is responsible to do some tasks:
   - Install Docker and Docker-compose on jenkins server
   - Run jenkins docker-compose to have its docker container up and running
   
----------
#### One of the most important files that we have in this project is << casc.yml >> that is reponsible to define the whole jenkins configuration as a simple, human-friendly, plain text yaml syntax
#### For this project , We defined multiple elements in casc.yml to show the power of JCasC
#### The root elements that we used:
- jenkins: basic jenkins configuration
- credentials: credentials of installed plugins
- unclassified: Setting up installed plugins
- tool: the location of installed tools like jdk, git, maven ....

#### what we did in casc.yml:
 - setting up jenkins basic configuration like system_message , num executors , jenkins url
 - Creating a local user : admin
 - Creating two credentials with different types (string , usernamePassword) for SonarQube and Jira plugins
 - Setting up Jira and SonarQube Plugins
 - Setting up the home location of jdk, maven, git tools

----------
### Now We have a jenkins server with Pre-defind configuration
