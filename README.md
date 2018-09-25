# cyf-ansible

Ansible playbook to provision Code Your Future laptops, based on Linux Ubuntu.

- Patch and upgrade the system 
- Git
- Chrome and Postman
- Node.JS and npm (install global modules under ~/.npm-global)
- ZSH and Oh my ZSH
- Slack
- Visual Studio Code (with prettier, python and babel extensions)
- PostgreSQL (connect with `sudo -u postgres psql`)
- MongoDB 

## Prerequisities

- Ansible (install it with `sudo apt-get install ansible` on Linux Ubuntu)

## Usage

### Run from a unique Ansible machine

- Edit the file `inventory` which describes the machines which you want to run this playbook onto.
- These machines need be reachable over SSH. You need to have one line per machine in the `inventory` file with the machine IP, the username and SSH password to connect. These machines need to be reachable from the computer which will execute the Ansible playbook (same network).
- Run `ansible-playbook -i inventory playbook.yml` which will run the Ansible playbook on each machine described in the `inventory` file.

### Run Ansible on each machine 

- If for some reason machines cannot be reached by SSH, we can still run the Ansible playbook on each individual machine. 
- `git clone` this repo on each machine
- Edit the file `inventory` and just mention `localhost ansible_connection=local`
- Run `ansible-playbook -i inventory playbook.yml` on each machine.

## Testing

You can test this playbook on a VM. You will need Vagrant and VirtualBox installed. 
Then run `vagrant up` to bring up the VM and `vagrant up --provision` to rerun Ansible.