# Vagrant - Big Sur VM setup for testing
The following vagrant setup is being used to test Ansible Macvbook setup playbooks:

To bring down the macos Big Sur Vagrant box you will need to run the following - 
`vagrant box add andreiborisov/macos-bigsur-intel `

Install Guest Additions to help fix screen sizing issues   # TODO - Not verified working
`vagrant plugin install vagrant-vbguest`

To run the vm you can run the following -
`vagrant up`

To stop the vm you can run the following -
`vagrant halt`

To provision the vm you can run the following -
`vagrant provision`

To destroy the vm you can run the following -
`vagrant destroy`

## Using the VM
To use the VM  open up VirtualBox and select the macos Big Sur box. This will open a new window in which MacOs will be running.

If you want to run ansible playbooks in the VM you will need to install Ansible on the VM. I have used this to test the following ansible playbook and can be used as reference - [MacBook-Setup-Stripped](https://github.com/devunderslash/mac-setup-stripped)