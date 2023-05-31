The whole idea of this deployment is to use terraform local_exec provisioner to execute, ansible-playbook command at launch of our virtual_machine to install nginx to our server


NB: Make sure that you set the ( ANSIBLE_HOST_KEY_CHECKING=False ) The reason is beacause we don't want ansible going to grab or make any checks, so it doesn't error out.


Running an ansible-playbook to install nginx means we have to feed ansible with with the credentials of our server, like the public_ip_address of the server. But we dont know that at launch thus this ${self.public_ip_address}. Telling ansible to grab and use the public_ip_address of the vm


#########################################################################################################################################
#################### In Ansible-Role ###################################

I started by creating a new directory called ansible-role. We use this command (ansible-galaxy init docker) which automatically creates a docker directory with sub-directories in it. Repeated same command for nginx.


Went to docker website and browsed how to install docker on ubuntu https://docs.docker.com/engine/install/ubuntu/ and start building our code from there.


Also created a simple html file, wrote a play in the task of nginx, for ansible to copy default_site.html to our server. The idea is  to bypass the default nginx homepage. To display the content of our default_site.html


Made a new directory (infrastructure) created up a server, so we can run our ansible-roles to install docker and nginx to the server <<< ansible-playbook main.yml -i inventory.yml -u adminuser --private-key /home/devopslab/.ssh/ansiblekeylocalexec -vvv >>>
