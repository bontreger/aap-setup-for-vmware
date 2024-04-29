# aap-setup-for-vmware
A repository that sets up an AAP instance using config-as-code to create an inventory of VMs from VMWare.

# Dependencies
If you run the ansible playbook from the command line, you will need the following collections and python plugins.
`pip install awxkit`
`ansible-galaxy collection install infra.controller_configuration awx.awx`
These can also be made available in an execution environment.

# Usage
Fill out the vault.example.yml file with the specifics of your environment.
Fill out the inventory.example.yml file with your inventory (remove any unused sections). This is the inventory of the AAP instance, as that's what we are automating.

Rename your vault.example.yml file to vault.yml, it is recommended to encrypt this file as it has plaintext passwords

Then you can run the playbook from anywhere
`ansible-playbook -i inventory.yml playbooks/controller_config.yml`