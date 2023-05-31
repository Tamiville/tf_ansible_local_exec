The whole idea of this deployment is to use terraform local_exec provisioner to execute, ansible-playbook command at launch of our virtual_machine to install nginx to our server


NB: Make sure that you set the ( ANSIBLE_HOST_KEY_CHECKING=False ) The reason is beacause we don't want ansible going to grab or make any checks, so it doesn't error out.


Running an ansible-playbook to install nginx means we have to feed ansible with with the credentials of our server, like the public_ip_address of the server. But we dont know that at launch thus this ${self.public_ip_address}. Telling ansible to grab and use the public_ip_address of the vm