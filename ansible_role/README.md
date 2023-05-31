To start with creating our ansible-role. We use this command (ansible-galaxy init docker) which automatically creates a docker directory with sub-directories in it. And repeat same command for nginx.


Went to docker website and browsed how to install docker on ubuntu https://docs.docker.com/engine/install/ubuntu/ and start building our code from there.


Also created a simple html file, wrote a play in the task of nginx, for ansible to copy default_site.html to our server. The idea is  to bypass the default nginx homepage. To display the content of our default_site.html


Made a new directory (infrastructure) created up a server, so we can run our ansible-roles to install docker and nginx to the server <<< ansible-playbook main.yml -i inventory.yml -u adminuser --private-key /home/devopslab/.ssh/ansiblekeylocalexec -vvv >>>