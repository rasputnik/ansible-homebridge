Raspberry Pi
=============

Sets up homebridge on a Raspberry pi 3.

## base OS

I'm using Debian Jessie 8.0 on a Rpi v3.

## setup

* install Ansible (2.x) on your host machine
* if you've renamed your pi, set correct hostname(s) in 'hosts'
* if you're not using the stock 'pi' user, set ansible_ssh_user' in 'hosts'
* setup passwordless SSH as ansible_ssh_user (i.e. copy up a pubkey to the pi by hand)

## time for Ansible

You can verify connectivity by running:

    ansible -i hosts all -m ping

and you should see lots of lovely facts about your pi flowing back.

Run the main play with:

    ansible-playbook -i hosts site.yml

## vars

* role-specific vars live in $rolename/defaults/main.yml
* 'globals' _(e.g. ansible_ssh_user)_ live in 'hosts'

### BUGS

Oh, I expect so. Log an issue / PR if you notice any.
