Description
=================

This module will uses a Vagranffile to create a **ubuntu/bionic64** box. Your ssh public key that is in **~/.ssh/id_rsa.pub** will be copied into the authorized_key for the user **vagrant**, allowing you to ssh into the box and will be used by ansible to ssh and configure the box when the playbook is ran.

Once the box is vagrant box is up an running, use the ansible playbook to install postgres on the machine and create a user named **bigboy**. It's password, **hellofriends**, is stored in the vault file located in the **/roles/postgres/vars directory**.

Usage
=================

1. Install virtualBox, vagrant, ansible on your machine.
2. Clone this repo onto your machine.
3. Navigate to the sample-ansible folder on your terminal.
4. Type `vagrant up` to start up the vagrant box.
5. Type `ansible-playbook postgres.yml --ask-vault-pass`, you will be prompted to enter the vault password which is **hifriends**.

Verification
=================

You can verify postgres is installed and the user is created by ssh into the vagrant box at it's IP, **192.168.33.10**, like below.

`ssh vagrant@192.168.33.10`

Run the below command to run psql as postgres.

`sudo -u postgres psql`

On the postgres command line type `\du` which wil list all created users.

Requirements
=================

VirtualBox
Vagrant
Ansible