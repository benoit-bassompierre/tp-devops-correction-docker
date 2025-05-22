# TP DevOps Correction Docker

Following questions:

3-1 Document your inventory and base commands
This inventory defines a production host with SSH access using a private key and user "admin". It groups the host under "prod" for easier targeting in Ansible commands like ansible all -m ping or ansible-playbook -i inventory playbook.yml

3-2 Document your playbook
This playbook runs on all hosts with root privileges, gathers system info, and executes roles in order to set up Docker, create a network, and launch the database, app, and proxy containers.

3-3 Document your docker_container tasks configuration.
This file installs Docker and its dependencies, sets up Python and pip, and prepares a virtual environment with the Docker SDK. These steps ensure Ansible can manage Docker containers using the docker_container module in later roles like launch-database or launch-app

3-4 Is it really safe to deploy automatically every new image on the hub ? explain. What can I do to make it more secure? 
Automatically deploying on every new image push is convenient but not fully safe because a faulty or compromised image could break or expose our app. To improve security, we should add automated tests before deployment or implement manual approval steps in our CI/CD pipeline.
